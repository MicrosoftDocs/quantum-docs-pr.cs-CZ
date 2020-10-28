---
title: Čítač hloubek – sada pro vývoj pro všechna procesory
description: 'Přečtěte si o čítači hloubky Microsoft QDK, který používá simulátor trasování doby provozu ke shromáždění počtů hloubky každé operace vyvolané v :::no-loc(Q#)::: programu.'
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 89d8a2c9f2ecd5c5332215cd4307bcf4a6422036
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692109"
---
# <a name="quantum-trace-simulator-depth-counter"></a><span data-ttu-id="009d9-103">Simulátor trasování doby využití: čítač hloubky</span><span class="sxs-lookup"><span data-stu-id="009d9-103">Quantum trace simulator: depth counter</span></span>

<span data-ttu-id="009d9-104">Čítač hloubky je součástí nástroje pro vývoj po [částech.](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="009d9-104">The depth counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="009d9-105">Můžete ji použít ke shromáždění počtů, které reprezentují spodní mez hloubky každé operace vyvolané v programu pro užívání.</span><span class="sxs-lookup"><span data-stu-id="009d9-105">You can use it to gather counts that represent the lower bound of the depth of every operation invoked in a quantum program.</span></span> 

## <a name="depth-values"></a><span data-ttu-id="009d9-106">Hodnoty hloubky</span><span class="sxs-lookup"><span data-stu-id="009d9-106">Depth values</span></span>

<span data-ttu-id="009d9-107">Ve výchozím nastavení mají všechny operace hloubku **0** s výjimkou `T` operace, která má hloubku **1** .</span><span class="sxs-lookup"><span data-stu-id="009d9-107">By default, all operations have a depth of **0** except the `T` operation, which has a depth of **1** .</span></span> <span data-ttu-id="009d9-108">To znamená, že ve výchozím nastavení `T` je vypočítána pouze hloubka operací (což je často žádoucí).</span><span class="sxs-lookup"><span data-stu-id="009d9-108">This means that by default, only the `T` depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="009d9-109">Čítač hloubky agreguje a shromažďuje statistické údaje nad všemi hranami [grafu volání](https://en.wikipedia.org/wiki/Call_graph)operace.</span><span class="sxs-lookup"><span data-stu-id="009d9-109">The depth counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

<span data-ttu-id="009d9-110">Všechny <xref:Microsoft.Quantum.Intrinsic> operace se vyjadřují v souvislosti s qubit rotacemi, <xref:Microsoft.Quantum.Intrinsic.T> operacemi, qubitmi Clifford operacemi, <xref:Microsoft.Quantum.Intrinsic.CNOT> operacemi a měřeními Pauli observables s více qubity.</span><span class="sxs-lookup"><span data-stu-id="009d9-110">All <xref:Microsoft.Quantum.Intrinsic> operations are expressed in terms of single-qubit rotations, <xref:Microsoft.Quantum.Intrinsic.T> operations, single-qubit Clifford operations, <xref:Microsoft.Quantum.Intrinsic.CNOT> operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="009d9-111">Uživatelé mohou nastavit hloubku pro jednotlivé primitivní operace prostřednictvím `gateTimes` pole <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="009d9-111">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

## <a name="invoking-the-depth-counter"></a><span data-ttu-id="009d9-112">Vyvolání čítače hloubky</span><span class="sxs-lookup"><span data-stu-id="009d9-112">Invoking the depth counter</span></span>

<span data-ttu-id="009d9-113">Chcete-li spustit simulátor trasování doby provozu s čítačem hloubky, je nutné vytvořit <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instanci, nastavit její `UseDepthCounter` vlastnost na **hodnotu true** a poté vytvořit novou <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instanci s `QCTraceSimulatorConfiguration` parametrem.</span><span class="sxs-lookup"><span data-stu-id="009d9-113">To run the quantum trace simulator with the depth counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set its `UseDepthCounter` property to **true** , and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a><span data-ttu-id="009d9-114">Použití čítače hloubky v hostitelském programu C#</span><span class="sxs-lookup"><span data-stu-id="009d9-114">Using the depth counter in a C# host program</span></span>

<span data-ttu-id="009d9-115">Příklad v jazyce C#, který následuje v tomto oddílu `T` , počítá hloubku `CCNOT` operace na základě následujícího :::no-loc(Q#)::: ukázkového kódu:</span><span class="sxs-lookup"><span data-stu-id="009d9-115">The C# example that follows in this section computes the `T` depth of the `CCNOT` operation, based on the following :::no-loc(Q#)::: sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="009d9-116">Chcete-li ověřit, zda `CCNOT` má `T` Hloubka **5** a `ApplySampleWithCCNOT` má `T` hloubku **6** , použijte následující kód jazyka C#:</span><span class="sxs-lookup"><span data-stu-id="009d9-116">To check that `CCNOT` has `T` depth **5** and `ApplySampleWithCCNOT` has `T` depth **6** , use the following C# code:</span></span>

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

<span data-ttu-id="009d9-117">První část programu se spustí `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="009d9-117">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="009d9-118">Druhá část používá [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metodu pro načtení `T` hloubky `CCNOT` a `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="009d9-118">The second part uses the [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`.</span></span> 

<span data-ttu-id="009d9-119">Nakonec můžete výstup všech statistik shromážděných pomocí čítače hloubky ve formátu CSV použít následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="009d9-119">Finally, you can output all the statistics collected by the depth counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="009d9-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="009d9-120">See also</span></span>

- <span data-ttu-id="009d9-121">Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) pro všechna ta.</span><span class="sxs-lookup"><span data-stu-id="009d9-121">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="009d9-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Reference k rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="009d9-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="009d9-123"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Reference k rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="009d9-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="009d9-124"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter>Reference k rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="009d9-124">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> API reference.</span></span>
