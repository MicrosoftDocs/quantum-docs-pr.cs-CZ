---
title: Čítač primitivních operací – sada pro vývoj všech procesorů
description: Přečtěte si o čítači operací primitivního provozu Microsoft QDK, který používá simulátor trasování doby provozu ke sledování základních spuštění používaných operacemi v Q# programu.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: ceb70cef6dc0a4530b992b5a529248a8b283c17f
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868232"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a><span data-ttu-id="362ac-103">Simulátor trasování doby provozu: čítač primitivních operací</span><span class="sxs-lookup"><span data-stu-id="362ac-103">Quantum trace simulator: primitive operations counter</span></span>

<span data-ttu-id="362ac-104">Čítač primitivních operací je součástí nástroje pro vývoj provozu po částech [.](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="362ac-104">The primitive operation counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="362ac-105">Počítá počet primitivních spuštění používaných každou operací vyvolanou v programu pro řízení.</span><span class="sxs-lookup"><span data-stu-id="362ac-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> 

<span data-ttu-id="362ac-106">Všechny <xref:microsoft.quantum.intrinsic> operace se vyjadřují v souvislosti s qubit otočeními, T operacemi, qubitmi Clifford operacemi, operacemi CNOT a měřeními multi-qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="362ac-106">All <xref:microsoft.quantum.intrinsic> operations are expressed in terms of single-qubit rotations, T operations, single-qubit Clifford operations, CNOT operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="362ac-107">Čítač primitivních operací agreguje a shromažďuje statistické údaje nad všemi hranami [grafu volání](https://en.wikipedia.org/wiki/Call_graph)operace.</span><span class="sxs-lookup"><span data-stu-id="362ac-107">The Primitive Operations Counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

## <a name="invoking-the-primitive-operation-counter"></a><span data-ttu-id="362ac-108">Vyvolání čítače primitivní operace</span><span class="sxs-lookup"><span data-stu-id="362ac-108">Invoking the primitive operation counter</span></span>

<span data-ttu-id="362ac-109">Chcete-li spustit simulátor trasování doby provozu pomocí čítače primitivních operací, je nutné vytvořit <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instanci, nastavit `UsePrimitiveOperationsCounter` vlastnost na **hodnotu true**a poté vytvořit novou <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instanci s `QCTraceSimulatorConfiguration` parametrem jako.</span><span class="sxs-lookup"><span data-stu-id="362ac-109">To run the quantum trace simulator with the primitive operation counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UsePrimitiveOperationsCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span>

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a><span data-ttu-id="362ac-110">Použití čítače primitivních operací v hostitelském programu C#</span><span class="sxs-lookup"><span data-stu-id="362ac-110">Using the primitive operation counter in a C# host program</span></span>

<span data-ttu-id="362ac-111">Příklad jazyka C#, který následuje v této části, počítá <xref:microsoft.quantum.intrinsic.t> , kolik operací je potřeba k implementaci <xref:microsoft.quantum.intrinsic.ccnot> operace, na základě následujícího Q# ukázkového kódu:</span><span class="sxs-lookup"><span data-stu-id="362ac-111">The C# example that follows in this section counts how many <xref:microsoft.quantum.intrinsic.t> operations are needed to implement the <xref:microsoft.quantum.intrinsic.ccnot> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="362ac-112">Chcete-li ověřit, že `CCNOT` vyžaduje sedm `T` operací a `ApplySampleWithCCNOT` spouští osm `T` operací, použijte následující kód jazyka C#:</span><span class="sxs-lookup"><span data-stu-id="362ac-112">To check that `CCNOT` requires seven `T` operations and that `ApplySampleWithCCNOT` runs eight `T` operations, use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="362ac-113">První část programu se spustí `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="362ac-113">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="362ac-114">Druhá část používá [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metodu k načtení počtu `T` operací spuštěných pomocí `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="362ac-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of `T` operations run by `ApplySampleWithCCNOT`:</span></span> 

<span data-ttu-id="362ac-115">Při volání `GetMetric` pomocí dvou parametrů typu vrátí hodnotu metriky související s daným okrajem grafu volání.</span><span class="sxs-lookup"><span data-stu-id="362ac-115">When you call `GetMetric` with two type parameters, it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="362ac-116">V předchozím příkladu program volá `Primitive.CCNOT` operaci do `ApplySampleWithCCNOT` , a proto graf volání obsahuje hranici `<Primitive.CCNOT, ApplySampleWithCCNOT>` .</span><span class="sxs-lookup"><span data-stu-id="362ac-116">In the preceding example, the program calls the `Primitive.CCNOT` operation  within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="362ac-117">Pokud chcete načíst počet `CNOT` využitých operací, přidejte následující řádek:</span><span class="sxs-lookup"><span data-stu-id="362ac-117">To retrieve the number of `CNOT` operations used, add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="362ac-118">Nakonec můžete výstup všech statistik shromažďovaných pomocí čítače primitivních operací ve formátu CSV pomocí následujících možností:</span><span class="sxs-lookup"><span data-stu-id="362ac-118">Finally, you can output all the statistics collected by the Primitive Operations Counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="362ac-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="362ac-119">See also</span></span>

- <span data-ttu-id="362ac-120">Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) pro všechna ta.</span><span class="sxs-lookup"><span data-stu-id="362ac-120">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="362ac-121"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Reference k rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="362ac-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="362ac-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Reference k rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="362ac-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="362ac-123"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames>Reference k rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="362ac-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> API reference.</span></span>