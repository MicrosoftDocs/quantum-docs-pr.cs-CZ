---
title: Čítač primitivních operací | Simulátor sledování počítačového systému | Microsoft Docs
description: Přehled simulátoru trasování kvantového počítače
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 1f554c0a1b92c8f6b59be3a9d9965e0e25bd074f
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820415"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="79ca5-103">Čítač primitivních operací</span><span class="sxs-lookup"><span data-stu-id="79ca5-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="79ca5-104">`Primitive Operations Counter` je součástí [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)počítačů.</span><span class="sxs-lookup"><span data-stu-id="79ca5-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="79ca5-105">Počítá počet primitivních spuštění používaných každou operací vyvolanou v programu pro řízení.</span><span class="sxs-lookup"><span data-stu-id="79ca5-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="79ca5-106">Všechny operace z `Microsoft.Quantum.Intrinsic` se vyjadřují v souvislosti s qubit rotacemi, T branami, qubit Clifford branami, CNOT branami a měřeními v qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="79ca5-106">All operations from `Microsoft.Quantum.Intrinsic` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="79ca5-107">Shromážděné statistiky jsou shrnuty na okrajích grafu volání operací.</span><span class="sxs-lookup"><span data-stu-id="79ca5-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="79ca5-108">Pojďme nám teď počítat, kolik `T`ch bran je potřeba k implementaci `CCNOT` operace.</span><span class="sxs-lookup"><span data-stu-id="79ca5-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="79ca5-109">Použití čítače primitivních operací v rámci C# programu</span><span class="sxs-lookup"><span data-stu-id="79ca5-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="79ca5-110">Pokud chcete ověřit, že `CCNOT` skutečně vyžaduje 7 `T` a že `ApplySampleWithCCNOT` provádí 8 `T`ch bran, můžeme použít C# následující kód:</span><span class="sxs-lookup"><span data-stu-id="79ca5-110">To check that `CCNOT` indeed requires 7 `T` gates and that `ApplySampleWithCCNOT` executes 8 `T` gates we can use the following C# code:</span></span>

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

<span data-ttu-id="79ca5-111">První část programu provede `ApplySampleWithCCNOT`.</span><span class="sxs-lookup"><span data-stu-id="79ca5-111">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="79ca5-112">V druhé části používáme metodu `QCTraceSimulator.GetMetric` k získání počtu T vyslaných vratů provedených pomocí `ApplySampleWithCCNOT`:</span><span class="sxs-lookup"><span data-stu-id="79ca5-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="79ca5-113">Když je volána `GetMetric` se dvěma parametry typu, vrátí hodnotu metriky přidružené k dané hraně grafu volání.</span><span class="sxs-lookup"><span data-stu-id="79ca5-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="79ca5-114">V našem příkladu je operace `Primitive.CCNOT` volána v rámci `ApplySampleWithCCNOT`, takže graf volání obsahuje hraniční `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span><span class="sxs-lookup"><span data-stu-id="79ca5-114">In our example operation `Primitive.CCNOT` is called within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="79ca5-115">Pokud chcete získat počet `CNOT` používaných bran, můžeme přidat následující řádek:</span><span class="sxs-lookup"><span data-stu-id="79ca5-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="79ca5-116">Aby bylo možné vystavit výstup všech statistik shromažďovaných čítačem brány ve formátu CSV, můžeme použít následující:</span><span class="sxs-lookup"><span data-stu-id="79ca5-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="79ca5-117">Další informace najdete v tématech</span><span class="sxs-lookup"><span data-stu-id="79ca5-117">See also</span></span> ##

- <span data-ttu-id="79ca5-118">Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítačů ve službě.</span><span class="sxs-lookup"><span data-stu-id="79ca5-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
