---
title: Čítač primitivních operací – sada pro vývoj všech procesorů
description: Přečtěte si o čítači operací primitivního provozu Microsoft QDK, který používá simulátor trasování doby provozu ke sledování základních spuštění používaných operacemi v Q# programu.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: ceb70cef6dc0a4530b992b5a529248a8b283c17f
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868232"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a>Simulátor trasování doby provozu: čítač primitivních operací

Čítač primitivních operací je součástí nástroje pro vývoj provozu po částech [.](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Počítá počet primitivních spuštění používaných každou operací vyvolanou v programu pro řízení. 

Všechny <xref:microsoft.quantum.intrinsic> operace se vyjadřují v souvislosti s qubit otočeními, T operacemi, qubitmi Clifford operacemi, operacemi CNOT a měřeními multi-qubit Pauli observables. Čítač primitivních operací agreguje a shromažďuje statistické údaje nad všemi hranami [grafu volání](https://en.wikipedia.org/wiki/Call_graph)operace.

## <a name="invoking-the-primitive-operation-counter"></a>Vyvolání čítače primitivní operace

Chcete-li spustit simulátor trasování doby provozu pomocí čítače primitivních operací, je nutné vytvořit <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instanci, nastavit `UsePrimitiveOperationsCounter` vlastnost na **hodnotu true**a poté vytvořit novou <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instanci s `QCTraceSimulatorConfiguration` parametrem jako.

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a>Použití čítače primitivních operací v hostitelském programu C#

Příklad jazyka C#, který následuje v této části, počítá <xref:microsoft.quantum.intrinsic.t> , kolik operací je potřeba k implementaci <xref:microsoft.quantum.intrinsic.ccnot> operace, na základě následujícího Q# ukázkového kódu:

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

Chcete-li ověřit, že `CCNOT` vyžaduje sedm `T` operací a `ApplySampleWithCCNOT` spouští osm `T` operací, použijte následující kód jazyka C#:

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

První část programu se spustí `ApplySampleWithCCNOT` . Druhá část používá [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metodu k načtení počtu `T` operací spuštěných pomocí `ApplySampleWithCCNOT` : 

Při volání `GetMetric` pomocí dvou parametrů typu vrátí hodnotu metriky související s daným okrajem grafu volání. V předchozím příkladu program volá `Primitive.CCNOT` operaci do `ApplySampleWithCCNOT` , a proto graf volání obsahuje hranici `<Primitive.CCNOT, ApplySampleWithCCNOT>` . 

Pokud chcete načíst počet `CNOT` využitých operací, přidejte následující řádek:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Nakonec můžete výstup všech statistik shromažďovaných pomocí čítače primitivních operací ve formátu CSV pomocí následujících možností:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Viz také

- Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) pro všechna ta.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Reference k rozhraní API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Reference k rozhraní API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames>Reference k rozhraní API.