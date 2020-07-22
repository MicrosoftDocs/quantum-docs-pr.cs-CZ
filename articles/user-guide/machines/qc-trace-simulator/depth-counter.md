---
title: Čítač hloubek – sada pro vývoj pro všechna procesory
description: 'Přečtěte si o čítači hloubky Microsoft QDK, který používá simulátor trasování doby provozu ke shromáždění počtů hloubky každé operace vyvolané v programu Q #.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 811e387fedf547d2681518ae0bb525c13dc84ff4
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871123"
---
# <a name="quantum-trace-simulator-depth-counter"></a>Simulátor trasování doby využití: čítač hloubky

Čítač hloubky je součástí nástroje pro vývoj po [částech.](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
Můžete ji použít ke shromáždění počtů, které reprezentují spodní mez hloubky každé operace vyvolané v programu pro užívání. 

## <a name="depth-values"></a>Hodnoty hloubky

Ve výchozím nastavení mají všechny operace hloubku **0** s výjimkou `T` operace, která má hloubku **1**. To znamená, že ve výchozím nastavení `T` je vypočítána pouze hloubka operací (což je často žádoucí). Čítač hloubky agreguje a shromažďuje statistické údaje nad všemi hranami [grafu volání](https://en.wikipedia.org/wiki/Call_graph)operace.

Všechny <xref:microsoft.quantum.intrinsic> operace se vyjadřují v souvislosti s qubit rotacemi, <xref:microsoft.quantum.intrinsic.t> operacemi, qubitmi Clifford operacemi, <xref:microsoft.quantum.intrinsic.cnot> operacemi a měřeními Pauli observables s více qubity. Uživatelé mohou nastavit hloubku pro jednotlivé primitivní operace prostřednictvím `gateTimes` pole <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .

## <a name="invoking-the-depth-counter"></a>Vyvolání čítače hloubky

Chcete-li spustit simulátor trasování doby provozu s čítačem hloubky, je nutné vytvořit <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instanci, nastavit její `UseDepthCounter` vlastnost na **hodnotu true**a poté vytvořit novou <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instanci s `QCTraceSimulatorConfiguration` parametrem. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a>Použití čítače hloubky v hostitelském programu C#

Příklad v jazyce C#, který následuje v tomto oddílu `T` , počítá hloubku `CCNOT` operace na základě následujícího ukázkového kódu Q #:

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

Chcete-li ověřit, zda `CCNOT` má `T` Hloubka **5** a `ApplySampleWithCCNOT` má `T` hloubku **6**, použijte následující kód jazyka C#:

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

První část programu se spustí `ApplySampleWithCCNOT` . Druhá část používá [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metodu pro načtení `T` hloubky `CCNOT` a `ApplySampleWithCCNOT` . 

Nakonec můžete výstup všech statistik shromážděných pomocí čítače hloubky ve formátu CSV použít následujícím způsobem:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Viz také

- Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) pro všechna ta.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Reference k rozhraní API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Reference k rozhraní API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter>Reference k rozhraní API.
