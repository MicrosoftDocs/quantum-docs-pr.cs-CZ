---
title: Čítač hloubek – sada pro vývoj pro všechna procesory
description: Přečtěte si o čítači hloubky Microsoft QDK, který používá simulátor trasování doby provozu ke shromáždění počtů hloubky každé operace vyvolané v Q# programu.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5c54f6fc479203d30c68c4958329605d4323f9ea
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868317"
---
# <a name="quantum-trace-simulator-depth-counter"></a><span data-ttu-id="83e68-103">Simulátor trasování doby využití: čítač hloubky</span><span class="sxs-lookup"><span data-stu-id="83e68-103">Quantum trace simulator: depth counter</span></span>

<span data-ttu-id="83e68-104">Čítač hloubky je součástí nástroje pro vývoj po [částech.](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="83e68-104">The depth counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="83e68-105">Můžete ji použít ke shromáždění počtů, které reprezentují spodní mez hloubky každé operace vyvolané v programu pro užívání.</span><span class="sxs-lookup"><span data-stu-id="83e68-105">You can use it to gather counts that represent the lower bound of the depth of every operation invoked in a quantum program.</span></span> 

## <a name="depth-values"></a><span data-ttu-id="83e68-106">Hodnoty hloubky</span><span class="sxs-lookup"><span data-stu-id="83e68-106">Depth values</span></span>

<span data-ttu-id="83e68-107">Ve výchozím nastavení mají všechny operace hloubku **0** s výjimkou `T` operace, která má hloubku **1**.</span><span class="sxs-lookup"><span data-stu-id="83e68-107">By default, all operations have a depth of **0** except the `T` operation, which has a depth of **1**.</span></span> <span data-ttu-id="83e68-108">To znamená, že ve výchozím nastavení `T` je vypočítána pouze hloubka operací (což je často žádoucí).</span><span class="sxs-lookup"><span data-stu-id="83e68-108">This means that by default, only the `T` depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="83e68-109">Čítač hloubky agreguje a shromažďuje statistické údaje nad všemi hranami [grafu volání](https://en.wikipedia.org/wiki/Call_graph)operace.</span><span class="sxs-lookup"><span data-stu-id="83e68-109">The depth counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

<span data-ttu-id="83e68-110">Všechny <xref:microsoft.quantum.intrinsic> operace se vyjadřují v souvislosti s qubit rotacemi, <xref:microsoft.quantum.intrinsic.t> operacemi, qubitmi Clifford operacemi, <xref:microsoft.quantum.intrinsic.cnot> operacemi a měřeními Pauli observables s více qubity.</span><span class="sxs-lookup"><span data-stu-id="83e68-110">All <xref:microsoft.quantum.intrinsic> operations are expressed in terms of single-qubit rotations, <xref:microsoft.quantum.intrinsic.t> operations, single-qubit Clifford operations, <xref:microsoft.quantum.intrinsic.cnot> operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="83e68-111">Uživatelé mohou nastavit hloubku pro jednotlivé primitivní operace prostřednictvím `gateTimes` pole <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="83e68-111">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

## <a name="invoking-the-depth-counter"></a><span data-ttu-id="83e68-112">Vyvolání čítače hloubky</span><span class="sxs-lookup"><span data-stu-id="83e68-112">Invoking the depth counter</span></span>

<span data-ttu-id="83e68-113">Chcete-li spustit simulátor trasování doby provozu s čítačem hloubky, je nutné vytvořit <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instanci, nastavit její `UseDepthCounter` vlastnost na **hodnotu true**a poté vytvořit novou <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instanci s `QCTraceSimulatorConfiguration` parametrem.</span><span class="sxs-lookup"><span data-stu-id="83e68-113">To run the quantum trace simulator with the depth counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set its `UseDepthCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a><span data-ttu-id="83e68-114">Použití čítače hloubky v hostitelském programu C#</span><span class="sxs-lookup"><span data-stu-id="83e68-114">Using the depth counter in a C# host program</span></span>

<span data-ttu-id="83e68-115">Příklad v jazyce C#, který následuje v tomto oddílu `T` , počítá hloubku `CCNOT` operace na základě následujícího Q# ukázkového kódu:</span><span class="sxs-lookup"><span data-stu-id="83e68-115">The C# example that follows in this section computes the `T` depth of the `CCNOT` operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="83e68-116">Chcete-li ověřit, zda `CCNOT` má `T` Hloubka **5** a `ApplySampleWithCCNOT` má `T` hloubku **6**, použijte následující kód jazyka C#:</span><span class="sxs-lookup"><span data-stu-id="83e68-116">To check that `CCNOT` has `T` depth **5** and `ApplySampleWithCCNOT` has `T` depth **6**, use the following C# code:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="83e68-117">První část programu se spustí `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="83e68-117">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="83e68-118">Druhá část používá [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metodu pro načtení `T` hloubky `CCNOT` a `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="83e68-118">The second part uses the [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`.</span></span> 

<span data-ttu-id="83e68-119">Nakonec můžete výstup všech statistik shromážděných pomocí čítače hloubky ve formátu CSV použít následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="83e68-119">Finally, you can output all the statistics collected by the depth counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="83e68-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="83e68-120">See also</span></span>

- <span data-ttu-id="83e68-121">Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) pro všechna ta.</span><span class="sxs-lookup"><span data-stu-id="83e68-121">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="83e68-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Reference k rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="83e68-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="83e68-123"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Reference k rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="83e68-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="83e68-124"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter>Reference k rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="83e68-124">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> API reference.</span></span>
