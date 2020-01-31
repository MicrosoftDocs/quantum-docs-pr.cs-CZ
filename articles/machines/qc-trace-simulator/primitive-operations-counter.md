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
# <a name="primitive-operations-counter"></a>Čítač primitivních operací  

`Primitive Operations Counter` je součástí [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)počítačů. Počítá počet primitivních spuštění používaných každou operací vyvolanou v programu pro řízení. Všechny operace z `Microsoft.Quantum.Intrinsic` se vyjadřují v souvislosti s qubit rotacemi, T branami, qubit Clifford branami, CNOT branami a měřeními v qubit Pauli observables. Shromážděné statistiky jsou shrnuty na okrajích grafu volání operací. Pojďme nám teď počítat, kolik `T`ch bran je potřeba k implementaci `CCNOT` operace. 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>Použití čítače primitivních operací v rámci C# programu

Pokud chcete ověřit, že `CCNOT` skutečně vyžaduje 7 `T` a že `ApplySampleWithCCNOT` provádí 8 `T`ch bran, můžeme použít C# následující kód:

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

První část programu provede `ApplySampleWithCCNOT`. V druhé části používáme metodu `QCTraceSimulator.GetMetric` k získání počtu T vyslaných vratů provedených pomocí `ApplySampleWithCCNOT`: 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

Když je volána `GetMetric` se dvěma parametry typu, vrátí hodnotu metriky přidružené k dané hraně grafu volání. V našem příkladu je operace `Primitive.CCNOT` volána v rámci `ApplySampleWithCCNOT`, takže graf volání obsahuje hraniční `<Primitive.CCNOT, ApplySampleWithCCNOT>`. 

Pokud chcete získat počet `CNOT` používaných bran, můžeme přidat následující řádek:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Aby bylo možné vystavit výstup všech statistik shromažďovaných čítačem brány ve formátu CSV, můžeme použít následující:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Další informace najdete v tématech ##

- Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítačů ve službě.
