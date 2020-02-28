---
title: Čítač primitivních operací
description: Přečtěte si o čítači operací primitivního provozu Microsoft QDK, který sleduje počet primitivních spuštění používaných operacemi v programu za běhu.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77905943"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="0f983-103">Čítač primitivních operací</span><span class="sxs-lookup"><span data-stu-id="0f983-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="0f983-104">`Primitive Operations Counter` je součástí [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)počítačů.</span><span class="sxs-lookup"><span data-stu-id="0f983-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="0f983-105">Počítá počet primitivních spuštění používaných každou operací vyvolanou v programu pro řízení.</span><span class="sxs-lookup"><span data-stu-id="0f983-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="0f983-106">Všechny operace z `Microsoft.Quantum.Intrinsic` se vyjadřují v souvislosti s qubit rotacemi, T branami, qubit Clifford branami, CNOT branami a měřeními v qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="0f983-106">All operations from `Microsoft.Quantum.Intrinsic` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="0f983-107">Shromážděné statistiky jsou shrnuty na okrajích grafu volání operací.</span><span class="sxs-lookup"><span data-stu-id="0f983-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="0f983-108">Pojďme nám teď počítat, kolik `T`ch bran je potřeba k implementaci `CCNOT` operace.</span><span class="sxs-lookup"><span data-stu-id="0f983-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="0f983-109">Použití čítače primitivních operací v rámci C# programu</span><span class="sxs-lookup"><span data-stu-id="0f983-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="0f983-110">Pokud chcete ověřit, že `CCNOT` skutečně vyžaduje 7 `T` a že `ApplySampleWithCCNOT` provádí 8 `T`ch bran, můžeme použít C# následující kód:</span><span class="sxs-lookup"><span data-stu-id="0f983-110">To check that `CCNOT` indeed requires 7 `T` gates and that `ApplySampleWithCCNOT` executes 8 `T` gates we can use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="0f983-111">První část programu provede `ApplySampleWithCCNOT`.</span><span class="sxs-lookup"><span data-stu-id="0f983-111">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="0f983-112">V druhé části používáme metodu `QCTraceSimulator.GetMetric` k získání počtu T vyslaných vratů provedených pomocí `ApplySampleWithCCNOT`:</span><span class="sxs-lookup"><span data-stu-id="0f983-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="0f983-113">Když je volána `GetMetric` se dvěma parametry typu, vrátí hodnotu metriky přidružené k dané hraně grafu volání.</span><span class="sxs-lookup"><span data-stu-id="0f983-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="0f983-114">V našem příkladu je operace `Primitive.CCNOT` volána v rámci `ApplySampleWithCCNOT`, takže graf volání obsahuje hraniční `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span><span class="sxs-lookup"><span data-stu-id="0f983-114">In our example operation `Primitive.CCNOT` is called within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="0f983-115">Pokud chcete získat počet `CNOT` používaných bran, můžeme přidat následující řádek:</span><span class="sxs-lookup"><span data-stu-id="0f983-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="0f983-116">Aby bylo možné vystavit výstup všech statistik shromažďovaných čítačem brány ve formátu CSV, můžeme použít následující:</span><span class="sxs-lookup"><span data-stu-id="0f983-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="0f983-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="0f983-117">See also</span></span> ##

- <span data-ttu-id="0f983-118">Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítačů ve službě.</span><span class="sxs-lookup"><span data-stu-id="0f983-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
