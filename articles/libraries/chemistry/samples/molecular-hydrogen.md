---
title: Získání odhadů energetické úrovně
description: 'Projděte si ukázkový program Q #, který odhadne hodnoty energetické úrovně molekulové vodíky.'
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
ms.openlocfilehash: 3242d8c6dc6fad2bd99055027dd7ce4ec3510ff4
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907303"
---
# <a name="obtaining-energy-level-estimates"></a>Získání odhadů energetické úrovně
Odhad hodnot úrovně energie je jednou z hlavních aplikací chemického pole. Tady je přehled toho, jak to lze provést pro Kanonický příklad molekulové vodíku. Ukázka, na kterou se odkazuje v této části, je `MolecularHydrogen` v úložišti vzorků chemického kódu. Dalším vizuálním příkladem, který vykresluje výstup, je `MolecularHydrogenGUI` ukázka.

Naším prvním krokem je vytvoření Hamiltonian představující molekulovou vodíkovou hodnotu. I když se to dá provést pomocí nástroje NWChem, do této ukázky přidáme ručně Hamiltonianické výrazy pro zkrácení.

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

    // We initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

Simulace Hamiltonian vyžaduje, abychom převedli operátory fermion na qubit operátory. Tento převod se provádí pomocí kódování Jordánska-Wigner následujícím způsobem.

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // We also need to create an input quantum state to this Hamiltonian.
    // Let us use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the Q# operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

Nyní předáte `qSharpData` reprezentující Hamiltonian do funkce `TrotterStepOracle` při [simulaci Hamiltonian Dynamics](xref:microsoft.quantum.libraries.standard.algorithms). `TrotterStepOracle` vrátí operaci s dobou platnosti, která se blíží skutečnému vývoji času Hamiltonian.

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);
```

Nyní můžeme použít algoritmy odhadu fáze standardní knihovny k získání informací o spotřebě energie v základní knihovně pomocí výše uvedené simulace. K tomu je potřeba připravit dobrý odhad stavu stavového provozu. Návrhy těchto sblížení jsou k dispozici ve schématu `Broombridge`, ale některé návrhy neexistují, výchozí přístup přidá množství `hamiltonian.NElectrons` Electrons k greedily minimalizaci diagonálního energiesého termínu. Funkce odhadu fáze a operace se nacházejí v [oboru názvů Microsoft. probíhají. charakterizace](xref:microsoft.quantum.characterization in DocFX notation).

Následující fragment kódu ukazuje, jak může být výstup pro vývoj v reálném čase integrací knihovny pro simulaci ve fázi kódu.

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined below.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // We use the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // We obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // We return both the estimated phase, and the estimated energy.
    return (estPhase, estEnergy);
}
```

Tento kód Q # se teď dá vyvolat z programu ovladače. V následující části vytvoříme úplný stav simulátoru a spustíme `GetEnergyByTrotterization`, abyste získali stavovou energii.

```csharp
using (var qsim = new QuantumSimulator())
{
    // We specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // We specify the step-size of the simulated time-evolution. This needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, let us run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular Hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

Všimněte si, že jsou vráceny dva parametry. `energyEst` je odhadem energetické energie a měla by být v průměru `-1.137`. `phaseEst` je nezpracované fáze vracené algoritmem odhadu fáze a je užitečná pro diagnostiku, když dojde k vytvoření aliasu z důvodu `trotterStep`, která je příliš velká.
