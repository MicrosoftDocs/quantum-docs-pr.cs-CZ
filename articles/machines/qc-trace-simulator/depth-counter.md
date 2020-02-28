---
title: Čítač hloubky
description: Přečtěte si o čítači hloubky Microsoft QDK, který shromažďuje počty hloubky každé operace vyvolané v programu
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: d532a9f512b8c87d83d62ed26e3bb67e1b6f668b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906096"
---
# <a name="depth-counter"></a>Čítač hloubky

`Depth Counter` je součástí [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)počítačů.
Používá se k získání počtů hloubky každé operace vyvolané v programu pro práci v poli. Všechny operace z <xref:microsoft.quantum.intrinsic> se vyjadřují v souvislosti s qubit rotacemi, T branami, qubit Clifford branami, CNOT branami a měřeními v qubit Pauli observables. Uživatelé mohou nastavit hloubku pro jednotlivé primitivní operace prostřednictvím pole `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.

Ve výchozím nastavení mají všechny operace hloubku 0 s výjimkou brány T s hloubkou 1. To znamená, že ve výchozím nastavení je vypočítána pouze hloubka T operací (což je často žádoucí). Shromážděné statistiky jsou shrnuty přes všechny hrany grafu volání operací. 

Nyní můžeme vypočítat <xref:microsoft.quantum.intrinsic.t> hloubku operace <xref:microsoft.quantum.intrinsic.ccnot>. Budeme používat následující vzorový kód Q #:

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>Použití čítače hloubky v C# rámci programu

Chcete-li ověřit, zda `CCNOT` má `T` hloubku 5 a `ApplySampleWithCCNOT` má `T` hloubku 6 C# , můžeme použít následující kód:

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

První část programu provede `ApplySampleWithCCNOT`. V druhé části používáme metodu `QCTraceSimulator.GetMetric` k získání `T` hloubky `CCNOT` a `ApplySampleWithCCNOT`: 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

Nakonec můžete pro výstup všech statistik shromážděných službou `Depth Counter` ve formátu CSV použít následující:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Viz také ##

- Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítačů ve službě.
