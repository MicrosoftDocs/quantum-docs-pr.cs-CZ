---
title: Získání počtu prostředků | Microsoft Docs
description: Získání počtu zdrojů dokumentů
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.resourcecounts
ms.openlocfilehash: b28a27c4c1f1e64644fcfb074a731ff7b65cacb6
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184079"
---
## <a name="obtaining-resource-counts"></a><span data-ttu-id="07bd7-103">Získání počtu prostředků</span><span class="sxs-lookup"><span data-stu-id="07bd7-103">Obtaining resource counts</span></span>

<span data-ttu-id="07bd7-104">Náklady na simulaci $n $ qubits v klasických počítačích škálují exponenciálně s $n $.</span><span class="sxs-lookup"><span data-stu-id="07bd7-104">The cost of simulating $n$ qubits on a classical computers scales exponentially with $n$.</span></span> <span data-ttu-id="07bd7-105">Tím se významně omezuje velikost simulační simulace, kterou můžeme provádět s simulátorem s plným stavem.</span><span class="sxs-lookup"><span data-stu-id="07bd7-105">This greatly limits the size of an quantum chemistry simulation we may perform with the full-state simulator.</span></span> <span data-ttu-id="07bd7-106">U velkých instancí chemického programu můžeme Nicméně získat užitečné informace.</span><span class="sxs-lookup"><span data-stu-id="07bd7-106">For large instances of chemistry, we may nevertheless obtain useful information.</span></span> <span data-ttu-id="07bd7-107">Tady zjistíte, jak se náklady na prostředky, jako je třeba počet T-Branch nebo CNOTch bran, pro simulaci chemické látky, získají automatizovaným způsobem pomocí [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="07bd7-107">Here, we examine how resource costs, such as the number of T-gates or CNOT gates, for simulating chemistry may be obtained in an automated fashion using the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="07bd7-108">Tyto informace informují o tom, kdy může být počítač dostatečně velký, aby mohl spouštět tyto chemické algoritmy.</span><span class="sxs-lookup"><span data-stu-id="07bd7-108">Such information informs us of when quantum computers might be large enough to run these quantum chemistry algorithms.</span></span> <span data-ttu-id="07bd7-109">Referenční informace najdete v uvedené ukázce `GetGateCount`.</span><span class="sxs-lookup"><span data-stu-id="07bd7-109">For reference, see the provided `GetGateCount` sample.</span></span>

<span data-ttu-id="07bd7-110">Můžeme předpokládat, že již máme instanci `FermionHamiltonian`, kterou jste načetli ze schématu Broombridge, jak je popsáno v příkladu [načtení-z-souboru](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .</span><span class="sxs-lookup"><span data-stu-id="07bd7-110">Let us assume that we already have a `FermionHamiltonian` instance, say, loaded from the Broombridge schema as discussed in the [loading-from-file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) example.</span></span> 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

<span data-ttu-id="07bd7-111">Syntaxe pro získání odhadů prostředků je téměř totožná se spouštěním algoritmu pro simulátor s plným stavem.</span><span class="sxs-lookup"><span data-stu-id="07bd7-111">The syntax for obtaining resource estimates is almost identical to running the algorithm on the full-state simulator.</span></span> <span data-ttu-id="07bd7-112">Jednoduše si zvolíme jiný cílový počítač.</span><span class="sxs-lookup"><span data-stu-id="07bd7-112">We simply choose a different target machine.</span></span> <span data-ttu-id="07bd7-113">Pro účely odhadu prostředků postačuje, abyste vyhodnotili náklady na jeden Trotter krok, nebo s využitím Qubitization techniky.</span><span class="sxs-lookup"><span data-stu-id="07bd7-113">For the purposes of resource estimates, it suffices to evaluate the cost of a single Trotter step, or a quantum walk created by the Qubitization technique.</span></span> <span data-ttu-id="07bd7-114">Tento často používaný algoritmus pro vyvolání těchto algoritmů je následující.</span><span class="sxs-lookup"><span data-stu-id="07bd7-114">The boilerplate for invoking these algorithms are as follows.</span></span>

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

<span data-ttu-id="07bd7-115">Teď nakonfigurujeme simulátor trasování pro sledování prostředků, které vás zajímá.</span><span class="sxs-lookup"><span data-stu-id="07bd7-115">We now configure the trace simulator to track the resources we are interested in.</span></span> <span data-ttu-id="07bd7-116">V tomto případě je počet primitivních operací na základě nastavení příznaku `usePrimitiveOperationsCounter` `true`.</span><span class="sxs-lookup"><span data-stu-id="07bd7-116">In this case, we count primitive quantum operations by setting the `usePrimitiveOperationsCounter` flag to `true`.</span></span> <span data-ttu-id="07bd7-117">Technický detail `throwOnUnconstraintMeasurement` je nastaven na hodnotu `false`, aby nedocházelo k výjimkám v případech, kdy kód Q # nepracuje správně s probabiltiymi výsledky měření, pokud jsou prováděny.</span><span class="sxs-lookup"><span data-stu-id="07bd7-117">A technical detail `throwOnUnconstraintMeasurement` is set to `false` to avoid exceptions in cases where the Q# code does not correctly assert of probabiltiy of measurement outcomes, if any are performed.</span></span>

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

<span data-ttu-id="07bd7-118">V programu ovladače teď používáme algoritmus pro podoby, jak je znázorněno níže.</span><span class="sxs-lookup"><span data-stu-id="07bd7-118">We now run the quantum algorithm from the driver program as follows.</span></span>

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