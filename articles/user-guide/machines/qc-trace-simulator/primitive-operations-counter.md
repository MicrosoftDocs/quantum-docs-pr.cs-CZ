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
# <a name="primitive-operations-counter"></a>Čítač primitivních operací  

`Primitive Operations Counter`Je součástí [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)počítačů. Počítá počet primitivních spuštění používaných každou operací vyvolanou v programu pro řízení. Všechny operace z `Microsoft.Quantum.Intrinsic` jsou vyjádřeny v rámci jednoduchých qubit rotací, T Branch, qubitch Cliffordch bran, CNOT bran a měření multi-qubit Pauli observables. Shromážděné statistiky jsou shrnuty na okrajích grafu volání operací. Pojďme nám teď počítat, kolik `T` bran je potřeba k implementaci této `CCNOT` operace. 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>Použití čítače primitivních operací v programu v jazyce C#

Chcete-li ověřit, že `CCNOT` skutečně vyžaduje 7 `T` bran a že se `ApplySampleWithCCNOT` provede 8 `T` bran, můžeme použít následující kód jazyka C#:

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

První část programu se spustí `ApplySampleWithCCNOT` . V druhé části používáme metodu `QCTraceSimulator.GetMetric` k získání počtu T bran, které provedly `ApplySampleWithCCNOT` : 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

Když `GetMetric` je volána pomocí dvou parametrů typu, vrátí hodnotu metriky související s daným okrajem grafu volání. V našem příkladu `Primitive.CCNOT` se operace volá v `ApplySampleWithCCNOT` a proto graf volání obsahuje okraje `<Primitive.CCNOT, ApplySampleWithCCNOT>` . 

Pokud chcete získat počet `CNOT` použitých bran, můžeme přidat následující řádek:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Aby bylo možné vystavit výstup všech statistik shromažďovaných čítačem brány ve formátu CSV, můžeme použít následující:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Viz také ##

- Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítačů ve službě.
