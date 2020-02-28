---
title: Čítač šířky
description: Přečtěte si o čítači šířky Microsoft QDKe, který spočítá počet qubits přidělených a vydaných každou operací v programu pro práci za sebou.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907082"
---
# <a name="width-counter"></a>Čítač šířky

`Width Counter` počítá počet qubits přidělených a vydaných jednotlivými operacemi.
Všechny operace z oboru názvů `Microsoft.Quantum.Intrinsic` jsou vyjádřeny v podobě jednoduchých rotací qubit, T Branch, qubit Clifford Branch, CNOTch bran a měření multi-qubit Pauli observables. Některé primitivní operace mohou přidělit další qubits. Můžete například vynásobit kontrolované `X` branami nebo řízenými `T`mi branami. Můžeme nám vypočítat počet dalších qubits přidělených implementací brány `X` s vynásobenou hodnotou:

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>Použití čítače šířky v rámci C# programu

Vynásobení řízených `X` působících na celkem 5 qubits přiděluje 2 doplňkové qubits a jeho vstupní šířka bude 5. Chcete-li zjistit, zda se jedná o tento případ, můžeme C# použít následující program:

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

První část programu provede `ApplyMultiControlledX`. V druhé části používáme metodu `QCTraceSimulator.GetMetric` k získání počtu přidělených qubits a počtu qubits, které řízené `X` přijaly jako vstup. 

Nakonec můžete pro výstup všech statistik shromážděných pomocí čítače šířky ve formátu CSV použít následující:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Viz také ##

- Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítačů ve službě.
