---
title: Čítač hloubky | Simulátor sledování počítačového systému | Microsoft Docs
description: Přehled simulátoru trasování kvantového počítače
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 07f927c794e2c62e53e4e053b5bc683d24bbed8d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820466"
---
# <a name="depth-counter"></a><span data-ttu-id="b663d-103">Čítač hloubky</span><span class="sxs-lookup"><span data-stu-id="b663d-103">Depth Counter</span></span>

<span data-ttu-id="b663d-104">`Depth Counter` je součástí [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)počítačů.</span><span class="sxs-lookup"><span data-stu-id="b663d-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="b663d-105">Používá se k získání počtů hloubky každé operace vyvolané v programu pro práci v poli.</span><span class="sxs-lookup"><span data-stu-id="b663d-105">It is used to gather counts of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="b663d-106">Všechny operace z <xref:microsoft.quantum.intrinsic> se vyjadřují v souvislosti s qubit rotacemi, T branami, qubit Clifford branami, CNOT branami a měřeními v qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="b663d-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="b663d-107">Uživatelé mohou nastavit hloubku pro jednotlivé primitivní operace prostřednictvím pole `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span><span class="sxs-lookup"><span data-stu-id="b663d-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="b663d-108">Ve výchozím nastavení mají všechny operace hloubku 0 s výjimkou brány T s hloubkou 1.</span><span class="sxs-lookup"><span data-stu-id="b663d-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="b663d-109">To znamená, že ve výchozím nastavení je vypočítána pouze hloubka T operací (což je často žádoucí).</span><span class="sxs-lookup"><span data-stu-id="b663d-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="b663d-110">Shromážděné statistiky jsou shrnuty přes všechny hrany grafu volání operací.</span><span class="sxs-lookup"><span data-stu-id="b663d-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="b663d-111">Nyní můžeme vypočítat <xref:microsoft.quantum.intrinsic.t> hloubku operace <xref:microsoft.quantum.intrinsic.ccnot>.</span><span class="sxs-lookup"><span data-stu-id="b663d-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="b663d-112">Budeme používat následující vzorový kód Q #:</span><span class="sxs-lookup"><span data-stu-id="b663d-112">We will use the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="b663d-113">Použití čítače hloubky v C# rámci programu</span><span class="sxs-lookup"><span data-stu-id="b663d-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="b663d-114">Chcete-li ověřit, zda `CCNOT` má `T` hloubku 5 a `ApplySampleWithCCNOT` má `T` hloubku 6 C# , můžeme použít následující kód:</span><span class="sxs-lookup"><span data-stu-id="b663d-114">To check that `CCNOT` has `T` depth 5 and `ApplySampleWithCCNOT` has `T` depth 6 we can use the following C# code:</span></span>

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

<span data-ttu-id="b663d-115">První část programu provede `ApplySampleWithCCNOT`.</span><span class="sxs-lookup"><span data-stu-id="b663d-115">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="b663d-116">V druhé části používáme metodu `QCTraceSimulator.GetMetric` k získání `T` hloubky `CCNOT` a `ApplySampleWithCCNOT`:</span><span class="sxs-lookup"><span data-stu-id="b663d-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="b663d-117">Nakonec můžete pro výstup všech statistik shromážděných službou `Depth Counter` ve formátu CSV použít následující:</span><span class="sxs-lookup"><span data-stu-id="b663d-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="b663d-118">Další informace najdete v tématech</span><span class="sxs-lookup"><span data-stu-id="b663d-118">See also</span></span> ##

- <span data-ttu-id="b663d-119">Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítačů ve službě.</span><span class="sxs-lookup"><span data-stu-id="b663d-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
