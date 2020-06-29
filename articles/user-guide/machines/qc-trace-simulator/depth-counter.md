---
title: Čítač hloubky
description: Přečtěte si o čítači hloubky Microsoft QDK, který shromažďuje počty hloubky každé operace vyvolané v programu
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 0029a00e6a3563dc542daeda2afa7cabf42441fb
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415254"
---
# <a name="depth-counter"></a><span data-ttu-id="c94a3-103">Čítač hloubky</span><span class="sxs-lookup"><span data-stu-id="c94a3-103">Depth Counter</span></span>

<span data-ttu-id="c94a3-104">`Depth Counter`Je součástí [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)počítačů.</span><span class="sxs-lookup"><span data-stu-id="c94a3-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="c94a3-105">Používá se ke shromáždění počtů, které reprezentují spodní hranici hloubky každé operace vyvolané v programu pro práci v poli.</span><span class="sxs-lookup"><span data-stu-id="c94a3-105">It is used to gather counts that represent the lower bound of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="c94a3-106">Všechny operace z <xref:microsoft.quantum.intrinsic> jsou vyjádřeny v rámci jednoduchých qubit rotací, T Branch, qubitch Cliffordch bran, CNOT bran a měření multi-qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="c94a3-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="c94a3-107">Uživatelé mohou nastavit hloubku pro jednotlivé primitivní operace prostřednictvím `gateTimes` pole <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="c94a3-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="c94a3-108">Ve výchozím nastavení mají všechny operace hloubku 0 s výjimkou brány T s hloubkou 1.</span><span class="sxs-lookup"><span data-stu-id="c94a3-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="c94a3-109">To znamená, že ve výchozím nastavení je vypočítána pouze hloubka T operací (což je často žádoucí).</span><span class="sxs-lookup"><span data-stu-id="c94a3-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="c94a3-110">Shromážděné statistiky jsou shrnuty přes všechny hrany grafu volání operací.</span><span class="sxs-lookup"><span data-stu-id="c94a3-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="c94a3-111">Nyní můžeme vypočítat <xref:microsoft.quantum.intrinsic.t> hloubku <xref:microsoft.quantum.intrinsic.ccnot> operace.</span><span class="sxs-lookup"><span data-stu-id="c94a3-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="c94a3-112">Budeme používat následující vzorový kód Q #:</span><span class="sxs-lookup"><span data-stu-id="c94a3-112">We will use the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="c94a3-113">Použití čítače hloubky v rámci programu v jazyce C#</span><span class="sxs-lookup"><span data-stu-id="c94a3-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="c94a3-114">Chcete-li ověřit, zda `CCNOT` má `T` Hloubka 5 a `ApplySampleWithCCNOT` má `T` hloubku 6, můžeme použít následující kód jazyka C#:</span><span class="sxs-lookup"><span data-stu-id="c94a3-114">To check that `CCNOT` has `T` depth 5 and `ApplySampleWithCCNOT` has `T` depth 6 we can use the following C# code:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="c94a3-115">První část programu se spustí `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="c94a3-115">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="c94a3-116">V druhé části používáme metodu `QCTraceSimulator.GetMetric` k získání `T` hloubky `CCNOT` a `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="c94a3-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="c94a3-117">Nakonec můžete pro výstup všech statistik shromážděných `Depth Counter` ve formátu CSV použít následující:</span><span class="sxs-lookup"><span data-stu-id="c94a3-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="c94a3-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="c94a3-118">See also</span></span> ##

- <span data-ttu-id="c94a3-119">Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítačů ve službě.</span><span class="sxs-lookup"><span data-stu-id="c94a3-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
