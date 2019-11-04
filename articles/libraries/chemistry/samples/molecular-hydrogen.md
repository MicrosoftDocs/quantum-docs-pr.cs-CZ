---
title: Získávání odhadů úrovně energie | Microsoft Docs
description: Získání odhadů úrovně energie dokumentace
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
ms.openlocfilehash: 32f18ea479a2c65eee2b0e16788dc9f0fabd5372
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185541"
---
## <a name="obtaining-energy-level-estimates"></a><span data-ttu-id="9c931-103">Získání odhadů úrovně energie</span><span class="sxs-lookup"><span data-stu-id="9c931-103">Obtaining energy level estimates</span></span>
<span data-ttu-id="9c931-104">Odhad hodnot úrovně energie je jednou z hlavních aplikací chemického pole.</span><span class="sxs-lookup"><span data-stu-id="9c931-104">Estimating the values of energy levels is one of the principal applications of quantum chemistry.</span></span> <span data-ttu-id="9c931-105">Tady je přehled toho, jak to lze provést pro Kanonický příklad molekulové vodíku.</span><span class="sxs-lookup"><span data-stu-id="9c931-105">Here, we outline how this may be performed for the canonical example of molecular Hydrogen.</span></span> <span data-ttu-id="9c931-106">Ukázka, na kterou se odkazuje v této části, je `MolecularHydrogen` v úložišti vzorků chemického kódu.</span><span class="sxs-lookup"><span data-stu-id="9c931-106">The sample referenced in this section is `MolecularHydrogen` in the chemistry samples repository.</span></span> <span data-ttu-id="9c931-107">Dalším vizuálním příkladem, který vykresluje výstup, je `MolecularHydrogenGUI` ukázka.</span><span class="sxs-lookup"><span data-stu-id="9c931-107">A more visual example that plots the output is the `MolecularHydrogenGUI` demo.</span></span>

<span data-ttu-id="9c931-108">Naším prvním krokem je vytvoření Hamiltonian představující molekulovou vodíkovou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="9c931-108">Our first step is to construct the Hamiltonian representing molecular Hydrogen.</span></span> <span data-ttu-id="9c931-109">I když se to dá provést pomocí nástroje NWChem, do této ukázky přidáme ručně Hamiltonianické výrazy pro zkrácení.</span><span class="sxs-lookup"><span data-stu-id="9c931-109">Though this can be constructed through the NWChem tool, we manually add Hamiltonian terms for brevity in this sample.</span></span>

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

<span data-ttu-id="9c931-110">Simulace Hamiltonian vyžaduje, abychom převedli operátory fermion na qubit operátory.</span><span class="sxs-lookup"><span data-stu-id="9c931-110">Simulating the Hamiltonian requires us to convert the fermion operators to qubit operators.</span></span> <span data-ttu-id="9c931-111">Tento převod se provádí pomocí kódování Jordánska-Wigner následujícím způsobem.</span><span class="sxs-lookup"><span data-stu-id="9c931-111">This conversion is performed through the Jordan-Wigner encoding as follows.</span></span>

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

<span data-ttu-id="9c931-112">Nyní předáte `qSharpData` reprezentující Hamiltonian do funkce `TrotterStepOracle` při [simulaci Hamiltonian Dynamics](xref:microsoft.quantum.libraries.standard.algorithms).</span><span class="sxs-lookup"><span data-stu-id="9c931-112">We now pass the `qSharpData` representing the Hamiltonian to the `TrotterStepOracle` function in [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms).</span></span> <span data-ttu-id="9c931-113">`TrotterStepOracle` vrátí operaci s dobou platnosti, která se blíží skutečnému vývoji času Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="9c931-113">`TrotterStepOracle` returns a quantum operation that approximates the real time-evolution of the Hamiltonian.</span></span>

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

<span data-ttu-id="9c931-114">Nyní můžeme použít algoritmy odhadu fáze standardní knihovny k získání informací o spotřebě energie v základní knihovně pomocí výše uvedené simulace.</span><span class="sxs-lookup"><span data-stu-id="9c931-114">We can now use the standard library's phase estimation algorithms to learn the ground state energy using the above simulation.</span></span> <span data-ttu-id="9c931-115">K tomu je potřeba připravit dobrý odhad stavu stavového provozu.</span><span class="sxs-lookup"><span data-stu-id="9c931-115">This requires preparing a good approximation to the quantum ground state.</span></span> <span data-ttu-id="9c931-116">Návrhy těchto sblížení jsou k dispozici ve schématu `Broombridge`, ale některé návrhy neexistují, výchozí přístup přidá množství `hamiltonian.NElectrons` Electrons k greedily minimalizaci diagonálního energiesého termínu.</span><span class="sxs-lookup"><span data-stu-id="9c931-116">Suggestions for such approximations are provided in the `Broombridge` schema, but absent these suggestions, the default approach adds a number of `hamiltonian.NElectrons` electrons to  greedily minimize the diagonal one-electron term energies.</span></span> <span data-ttu-id="9c931-117">Funkce odhadu fáze a operace se nacházejí v [oboru názvů Microsoft. probíhají. charakterizace](xref:microsoft.quantum.characterization in DocFX notation).</span><span class="sxs-lookup"><span data-stu-id="9c931-117">The phase estimation functions and operations are located in the [Microsoft.Quantum.Characterization namespace](xref:microsoft.quantum.characterization in DocFX notation).</span></span>

<span data-ttu-id="9c931-118">Následující fragment kódu ukazuje, jak může být výstup pro vývoj v reálném čase integrací knihovny pro simulaci ve fázi kódu.</span><span class="sxs-lookup"><span data-stu-id="9c931-118">The following snippet shows how the real time-evolution output by the chemistry simulation library may be integrated with quantum phase estimation.</span></span>

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

<span data-ttu-id="9c931-119">Tento kód Q # se teď dá vyvolat z programu ovladače.</span><span class="sxs-lookup"><span data-stu-id="9c931-119">This Q# code may now be invoke from the driver program.</span></span> <span data-ttu-id="9c931-120">V následující části vytvoříme úplný stav simulátoru a spustíme `GetEnergyByTrotterization`, abyste získali stavovou energii.</span><span class="sxs-lookup"><span data-stu-id="9c931-120">In the following, we create a full-state simulator and run `GetEnergyByTrotterization` to obtain the ground state energy.</span></span>

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

<span data-ttu-id="9c931-121">Všimněte si, že jsou vráceny dva parametry.</span><span class="sxs-lookup"><span data-stu-id="9c931-121">Note that two parameters are returned.</span></span> <span data-ttu-id="9c931-122">`energyEst` je odhadem energetické energie a měla by být v průměru `-1.137`.</span><span class="sxs-lookup"><span data-stu-id="9c931-122">`energyEst` is the estimate of the ground state energy, and should be around `-1.137` on average.</span></span> <span data-ttu-id="9c931-123">`phaseEst` je nezpracované fáze vracené algoritmem odhadu fáze a je užitečná pro diagnostiku, když dojde k vytvoření aliasu z důvodu `trotterStep`, která je příliš velká.</span><span class="sxs-lookup"><span data-stu-id="9c931-123">`phaseEst` is the raw phase returned by the phase estimation algorithm, and is useful to diagnose when aliasing occurs due to a `trotterStep` that is too large.</span></span>
