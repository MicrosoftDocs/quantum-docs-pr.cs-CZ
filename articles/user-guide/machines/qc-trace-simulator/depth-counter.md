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
# <a name="depth-counter"></a>Čítač hloubky

`Depth Counter`Je součástí [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)počítačů.
Používá se ke shromáždění počtů, které reprezentují spodní hranici hloubky každé operace vyvolané v programu pro práci v poli. Všechny operace z <xref:microsoft.quantum.intrinsic> jsou vyjádřeny v rámci jednoduchých qubit rotací, T Branch, qubitch Cliffordch bran, CNOT bran a měření multi-qubit Pauli observables. Uživatelé mohou nastavit hloubku pro jednotlivé primitivní operace prostřednictvím `gateTimes` pole <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .

Ve výchozím nastavení mají všechny operace hloubku 0 s výjimkou brány T s hloubkou 1. To znamená, že ve výchozím nastavení je vypočítána pouze hloubka T operací (což je často žádoucí). Shromážděné statistiky jsou shrnuty přes všechny hrany grafu volání operací. 

Nyní můžeme vypočítat <xref:microsoft.quantum.intrinsic.t> hloubku <xref:microsoft.quantum.intrinsic.ccnot> operace. Budeme používat následující vzorový kód Q #:

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>Použití čítače hloubky v rámci programu v jazyce C#

Chcete-li ověřit, zda `CCNOT` má `T` Hloubka 5 a `ApplySampleWithCCNOT` má `T` hloubku 6, můžeme použít následující kód jazyka C#:

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

První část programu se spustí `ApplySampleWithCCNOT` . V druhé části používáme metodu `QCTraceSimulator.GetMetric` k získání `T` hloubky `CCNOT` a `ApplySampleWithCCNOT` : 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

Nakonec můžete pro výstup všech statistik shromážděných `Depth Counter` ve formátu CSV použít následující:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Viz také ##

- Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítačů ve službě.