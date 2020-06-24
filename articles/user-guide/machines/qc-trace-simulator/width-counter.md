---
title: Čítač šířky
description: Přečtěte si o čítači šířky Microsoft QDKe, který spočítá počet qubits přidělených a vydaných každou operací v programu pro práci za sebou.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274570"
---
# <a name="width-counter"></a>Čítač šířky

`Width Counter`Počítá počet qubits přidělených a vydaných jednotlivými operacemi.
Všechny operace z `Microsoft.Quantum.Intrinsic` oboru názvů se vyjadřují v rámci jednoduchých qubit rotací, T Branch, qubitch Clifford bran, CNOT bran a měření multi-qubit Pauli observables. Některé primitivní operace mohou přidělit další qubits. Můžete například vynásobit kontrolované `X` brány nebo řízené `T` brány. Můžeme nám vypočítat počet dalších qubits přidělených implementací brány řízené vynásobením `X` :

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>Použití čítače šířky v rámci programu v jazyce C#

Vynásobení kontrolovaného `X` na základě celkového počtu 5 qubits přidělí 2 doplňkové qubits a jeho vstupní šířka bude 5. Chcete-li zjistit, zda se jedná o tento případ, můžeme použít následující program C#:

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

První část programu se spustí `ApplyMultiControlledX` . V druhé části používáme metodu `QCTraceSimulator.GetMetric` k získání počtu přidělených qubits a také počtu qubits, které řízené `X` přijetí jako vstupu. 

Nakonec můžete pro výstup všech statistik shromážděných pomocí čítače šířky ve formátu CSV použít následující:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Viz také ##

- Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítačů ve službě.
