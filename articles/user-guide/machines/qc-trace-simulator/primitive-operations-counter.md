---
title: Čítač primitivních operací
description: Přečtěte si o čítači operací primitivního provozu Microsoft QDK, který sleduje počet primitivních spuštění používaných operacemi v programu za běhu.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274569"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="78d6a-103">Čítač primitivních operací</span><span class="sxs-lookup"><span data-stu-id="78d6a-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="78d6a-104">`Primitive Operations Counter`Je součástí [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)počítačů.</span><span class="sxs-lookup"><span data-stu-id="78d6a-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="78d6a-105">Počítá počet primitivních spuštění používaných každou operací vyvolanou v programu pro řízení.</span><span class="sxs-lookup"><span data-stu-id="78d6a-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="78d6a-106">Všechny operace z `Microsoft.Quantum.Intrinsic` jsou vyjádřeny v rámci jednoduchých qubit rotací, T Branch, qubitch Cliffordch bran, CNOT bran a měření multi-qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="78d6a-106">All operations from `Microsoft.Quantum.Intrinsic` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="78d6a-107">Shromážděné statistiky jsou shrnuty na okrajích grafu volání operací.</span><span class="sxs-lookup"><span data-stu-id="78d6a-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="78d6a-108">Pojďme nám teď počítat, kolik `T` bran je potřeba k implementaci této `CCNOT` operace.</span><span class="sxs-lookup"><span data-stu-id="78d6a-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="78d6a-109">Použití čítače primitivních operací v programu v jazyce C#</span><span class="sxs-lookup"><span data-stu-id="78d6a-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="78d6a-110">Chcete-li ověřit, že `CCNOT` skutečně vyžaduje 7 `T` bran a že se `ApplySampleWithCCNOT` provede 8 `T` bran, můžeme použít následující kód jazyka C#:</span><span class="sxs-lookup"><span data-stu-id="78d6a-110">To check that `CCNOT` indeed requires 7 `T` gates and that `ApplySampleWithCCNOT` executes 8 `T` gates we can use the following C# code:</span></span>

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

<span data-ttu-id="78d6a-111">První část programu se spustí `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="78d6a-111">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="78d6a-112">V druhé části používáme metodu `QCTraceSimulator.GetMetric` k získání počtu T bran, které provedly `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="78d6a-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="78d6a-113">Když `GetMetric` je volána pomocí dvou parametrů typu, vrátí hodnotu metriky související s daným okrajem grafu volání.</span><span class="sxs-lookup"><span data-stu-id="78d6a-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="78d6a-114">V našem příkladu `Primitive.CCNOT` se operace volá v `ApplySampleWithCCNOT` a proto graf volání obsahuje okraje `<Primitive.CCNOT, ApplySampleWithCCNOT>` .</span><span class="sxs-lookup"><span data-stu-id="78d6a-114">In our example operation `Primitive.CCNOT` is called within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="78d6a-115">Pokud chcete získat počet `CNOT` použitých bran, můžeme přidat následující řádek:</span><span class="sxs-lookup"><span data-stu-id="78d6a-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="78d6a-116">Aby bylo možné vystavit výstup všech statistik shromažďovaných čítačem brány ve formátu CSV, můžeme použít následující:</span><span class="sxs-lookup"><span data-stu-id="78d6a-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="78d6a-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="78d6a-117">See also</span></span> ##

- <span data-ttu-id="78d6a-118">Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítačů ve službě.</span><span class="sxs-lookup"><span data-stu-id="78d6a-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
