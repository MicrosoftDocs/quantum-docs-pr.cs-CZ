---
title: Získání odhadů energetické úrovně
description: Projděte si ukázkový Q# program, který odhadne hodnoty energetické úrovně molekulové vodíky.
author: guanghaolow
ms.author: gulow
ms.date: 07/02/2020
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
no-loc:
- Q#
- $$v
ms.openlocfilehash: 81fba0c52c854d61f9143659795fb4d3c3cee8b9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691532"
---
# <a name="obtaining-energy-level-estimates"></a>Získání odhadů energetické úrovně
Odhad hodnot úrovně energie je jednou z hlavních aplikací chemického pole. Tento článek popisuje, jak to můžete udělat pro Kanonický příklad molekulové vodíkové podsystému. Ukázka, na kterou se odkazuje v této části, je [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) v úložišti vzorků chemie. Ukázková ukázka, který vykresluje výstup, je [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) ukázkou.

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a>Odhad hodnot energie molekulové vodíky

Prvním krokem je vytvoření Hamiltonian představující molekulovou vodíkovou hodnotu. I když to můžete vytvořit pomocí nástroje NWChem pro zkrácení, Tato ukázka přidá výrazy Hamiltonian ručně.

```csharp
    // These orbital integrals are represented using the OrbitalIntegral
    // data structure.
    var energyOffset = 0.713776188; // This is the coulomb repulsion
    var nElectrons = 2; // Molecular hydrogen has two electrons
    var orbitalIntegrals = new OrbitalIntegral[]
    {
        new OrbitalIntegral(new[] { 0,0 }, -1.252477495),
        new OrbitalIntegral(new[] { 1,1 }, -0.475934275),
        new OrbitalIntegral(new[] { 0,0,0,0 }, 0.674493166),
        new OrbitalIntegral(new[] { 0,1,0,1 }, 0.181287518),
        new OrbitalIntegral(new[] { 0,1,1,0 }, 0.663472101),
        new OrbitalIntegral(new[] { 1,1,1,1 }, 0.697398010),
        // This line adds the identity term.
        new OrbitalIntegral(new int[] { }, energyOffset)
    };

    // Initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

Simulace Hamiltonian vyžaduje převod operátorů fermion na qubit operátory. Tento převod se provádí pomocí kódování Jordan-Wigner následujícím způsobem:

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // You also need to create an input quantum state to this Hamiltonian.
    // Use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the Q# operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

Next, Pass `qSharpData` , který představuje Hamiltonian, do `TrotterStepOracle` funkce. `TrotterStepOracle` Vrátí operaci s dobou platnosti, která se blíží vývoji Hamiltonian v reálném čase. Další informace najdete v tématu [simulace Hamiltonian Dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);
```

V tuto chvíli můžete použít [algoritmy odhadu fáze](xref:microsoft.quantum.libraries.characterization) standardní knihovny k získání informací o energii stavu pomocí předchozí simulace. K tomu je potřeba připravit dobrý odhad stavu stavového provozu. Návrhy těchto sblížení jsou uvedeny ve [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schématu. Ale tyto návrhy neexistují, ale výchozí přístup přičítá `hamiltonian.NElectrons` Electrons k greedily minimalizaci diagonálního krátkodobého termínu Energies. Funkce odhadu fáze a operace jsou k dispozici v zápisu DocFX v oboru názvů [Microsoft.](xref:Microsoft.Quantum.Characterization) probíhají.

Následující fragment kódu ukazuje, jak se výstup vývoje v reálném čase integrací knihovny pro simulaci chemického zpracování do fází odhaduje.

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // Using a Product formula, also known as `Trotterization`, to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined here.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // Using the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // Now, obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // Return both the estimated phase and the estimated energy.
    return (estPhase, estEnergy);
}
```

Nyní můžete vyvolat Q# kód z hostitelského programu. Následující kód jazyka C# vytvoří simulátor s plným stavem a spustí `GetEnergyByTrotterization` se, aby se získal stav energie.

```csharp
using (var qsim = new QuantumSimulator())
{
    // Specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // Specify the step size of the simulated time evolution. The step size needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

Operace vrátí dva parametry: 

- `energyEst` je odhad elektrické energie a měl by být `-1.137` v průměru. 
- `phaseEst` je nezpracovaným fází vráceným algoritmem odhadu fáze. To je užitečné pro diagnostiku aliasů, když k nim dojde z důvodu `trotterStep` příliš velké hodnoty.
