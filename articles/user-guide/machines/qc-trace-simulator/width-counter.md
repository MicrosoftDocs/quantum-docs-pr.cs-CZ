---
title: Čítač šířky – sada pro vývoj všech procesorů
description: Přečtěte si o čítači šířky Microsoft QDK, který používá simulátor trasování doby provozu k výpočtu počtu qubits přidělených a vypůjčených operacemi v Q# programu.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: e54e92cc4a76ce9f9c5aead84f2b64320d6b4f1c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691115"
---
# <a name="quantum-trace-simulator-width-counter"></a>Simulátor trasování doby využití: čítač šířky

Čítač šířky je součástí [simulátoru pro sledování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)doby plnění. Můžete ji použít k určení počtu qubits přidělených a vypůjčených každou operací v Q# programu. Některé primitivní operace mohou přidělit nadbytečné qubits, například vynásobit kontrolované `X` operace nebo kontrolované `T` operace.

## <a name="invoking-the-width-counter"></a>Vyvolání čítače šířky

Chcete-li spustit simulátor trasování doby provozu s čítačem šířky, je nutné vytvořit <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instanci, nastavit `UseWidthCounter` vlastnost na **hodnotu true** a poté vytvořit novou <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instanci s `QCTraceSimulatorConfiguration` parametrem jako. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a>Použití čítače šířky v hostitelském programu C#

Příklad jazyka C#, který následuje v tomto oddílu, vypočítá počet extra qubits přidělených implementací operace s vynásobeným výsledkem <xref:Microsoft.Quantum.Intrinsic.X> , který je založený na následujícím Q# ukázkovém kódu:

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

Operace s hodnotou vynásobení <xref:Microsoft.Quantum.Intrinsic.X> funguje na celkem pět qubits, přiděluje dvě [pomocné qubits](xref:microsoft.quantum.glossary#ancilla)a má vstupní šířku **5** . Pomocí následujícího programu v jazyce C# ověřte počty:

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
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

První část programu spustí `ApplyMultiControlledX` operaci. Druhá část používá [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metodu pro načtení počtu přidělených qubits a také počet qubits, které `Controlled X` operace přijala jako vstup. 

Nakonec můžete vystavit výstup všech statistik shromážděných pomocí čítače šířky ve formátu CSV pomocí následujících možností:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Viz také

- Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) pro všechna ta.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Reference k rozhraní API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Reference k rozhraní API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter>Reference k rozhraní API.
