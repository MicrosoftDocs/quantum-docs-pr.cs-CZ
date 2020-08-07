---
title: Získání počtů prostředků
description: Naučte se, jak získat odhady prostředků pomocí simulátoru trasování.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.resourcecounts
no-loc:
- Q#
- $$v
ms.openlocfilehash: 35c16e622a390b730ad7385efcc365c212e981fe
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869320"
---
# <a name="obtaining-resource-counts"></a>Získání počtů prostředků

Náklady na simulaci $n $ qubits v klasických počítačích škálují exponenciálně s $n $. To významně omezuje velikost chemického simulaci pro každé z procesorů, které můžeme provádět s simulátorem s plným stavem. U velkých instancí chemického programu můžeme Nicméně získat užitečné informace. Tady zjistíte, jak se náklady na prostředky, jako je třeba počet T-Branch nebo CNOTch bran, pro simulaci chemické látky, získají automatizovaným způsobem pomocí [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro). Tyto informace informují o tom, kdy může být počítač dostatečně velký, aby mohl spouštět tyto chemické algoritmy. Referenční informace najdete v uvedené `GetGateCount` ukázce.

Můžeme předpokládat, že už máme `FermionHamiltonian` instanci, která je zavedená ze schématu Broombridge, jak je popsáno v příkladu [načtení-z-souboru](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) . 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

Syntaxe pro získání odhadů prostředků je téměř totožná se spouštěním algoritmu pro simulátor s plným stavem. Jednoduše si zvolíme jiný cílový počítač. Pro účely odhadu prostředků postačuje, abyste vyhodnotili náklady na jeden Trotter krok, nebo s využitím Qubitization techniky. Tento často používaný algoritmus pro vyvolání těchto algoritmů je následující.

```qsharp
//////////////////////////////////////////////////////////////////////////
// Using Trotterization //////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single Trotter step.
operation RunTrotterStep (qSharpData: JordanWignerEncodingData) : Unit {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    // The integrator step size does not affect the gate cost of a single step.
    let trotterStepSize = 1.0;
    
    // Order of integrator
    let trotterOrder = 1;
    let (nQubits, (rescaleFactor, oracle)) = TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // We not allocate qubits an run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
}


//////////////////////////////////////////////////////////////////////////
// Using Qubitization ////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single qubitization step.
operation RunQubitizationStep (qSharpData: JordanWignerEncodingData) : Double {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nQubits, (l1Norm, oracle)) = QubitizationOracle(qSharpData);
    
    // We now allocate qubits and run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
    
    return l1Norm;
}
```

Teď nakonfigurujeme simulátor trasování pro sledování prostředků, které vás zajímá. V takovém případě je počet primitivních operací nepočítat nastavením `usePrimitiveOperationsCounter` příznaku na `true` . Technický detail `throwOnUnconstraintMeasurement` je nastaven na `false` , aby nedocházelo k výjimkám v případech Q# , kdy kód nesprávně vyhodnotí pravděpodobnost výsledků měření, pokud jsou provedeny.

```csharp
private static QCTraceSimulator CreateAndConfigureTraceSim()
{
    // Create and configure Trace Simulator
    var config = new QCTraceSimulatorConfiguration()
    {
        usePrimitiveOperationsCounter = true,
        throwOnUnconstraintMeasurement = false
    };

    return new QCTraceSimulator(config);
}
```

V programu ovladače teď používáme algoritmus pro podoby, jak je znázorněno níže.

```csharp
// Instantiate a trace simulator instance
QCTraceSimulator sim = CreateAndConfigureTraceSim();

// Run the quantum algorithm on the trace simulator.
RunQubitizationStep.Run(sim, qSharpData);

// Print all resource counts to file.
var gateStats = sim.ToCSV();
foreach (var x in gateStats)
{
    System.IO.File.WriteAllLines($"QubitizationGateCountEstimates.{x.Key}.csv", new string[] { x.Value });
}
```