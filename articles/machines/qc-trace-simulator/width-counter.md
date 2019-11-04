---
title: Čítač šířky | Simulátor sledování počítačového systému | Microsoft Docs
description: Přehled simulátoru trasování počítačů s využitím
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: ae0c0ec2e677be03dc8dc1497dc62ad9034295a4
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442400"
---
# <a name="width-counter"></a>Čítač šířky

`Width Counter` počítá počet qubits přidělených a vydaných jednotlivými operacemi.
Všechny operace z oboru názvů `Microsoft.Quantum.Primitive` jsou vyjádřeny v podobě jednoduchých rotací qubit, T Branch, qubit Clifford Branch, CNOTch bran a měření multi-qubit Pauli observables. Některé primitivní operace mohou přidělit další qubits. Můžete například vynásobit kontrolované `X` branami nebo řízenými `T`mi branami. Můžeme nám vypočítat počet dalších qubits přidělených implementací brány `X` s vynásobenou hodnotou:

```qsharp
open Microsoft.Quantum.Primitive;
open Microsoft.Quantum.Arrays;
operation MultiControlledXDriver( numberOfQubits : Int ) : Unit {

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
var res = MultiControlledXDriver.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, MultiControlledXDriver>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, MultiControlledXDriver>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

První část programu provede `MultiControlledXDriver`. V druhé části používáme metodu `QCTraceSimulator.GetMetric` k získání počtu přidělených qubits a počtu qubits, které řízené `X` přijaly jako vstup. 

Nakonec můžete pro výstup všech statistik shromážděných pomocí čítače šířky ve formátu CSV použít následující:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Další informace najdete v tématech ##

- Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítačů ve službě.
