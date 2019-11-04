---
title: Čítač primitivních operací | Simulátor sledování počítačového systému | Microsoft Docs
description: Přehled simulátoru trasování počítačů s využitím
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: b7ec8b0d7a713051e36cb778c087050f0257710f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184878"
---
# <a name="primitive-operations-counter"></a>Čítač primitivních operací  

`Primitive Operations Counter` je součástí [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)počítačů. Počítá počet primitivních spuštění používaných každou operací vyvolanou v programu pro řízení. Všechny operace z `Microsoft.Quantum.Primitive` se vyjadřují v souvislosti s qubit rotacemi, T branami, qubit Clifford branami, CNOT branami a měřeními v qubit Pauli observables. Shromážděné statistiky jsou shrnuty na okrajích grafu volání operací. Pojďme nám teď počítat, kolik `T`ch bran je potřeba k implementaci `CCNOT` operace. 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>Použití čítače primitivních operací v rámci C# programu

Pokud chcete ověřit, že `CCNOT` skutečně vyžaduje 7 `T` a že `CCNOTDriver` provádí 8 `T`ch bran, můžeme použít C# následující kód:

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

První část programu provede `CCNOTDriver`. V druhé části používáme metodu `QCTraceSimulator.GetMetric` k získání počtu T vyslaných vratů provedených pomocí `CCNOTDriver`: 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

Když je volána `GetMetric` se dvěma parametry typu, vrátí hodnotu metriky přidružené k dané hraně grafu volání. V našem příkladu je operace `Primitive.CCNOT` volána v rámci `CCNOTDriver`, takže graf volání obsahuje hraniční `<Primitive.CCNOT,CCNOTDriver>`. 

Pokud chcete získat počet `CNOT` používaných bran, můžeme přidat následující řádek:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.CX);
```

Aby bylo možné vystavit výstup všech statistik shromažďovaných čítačem brány ve formátu CSV, můžeme použít následující:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Další informace najdete v tématech ##

- Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítačů ve službě.
