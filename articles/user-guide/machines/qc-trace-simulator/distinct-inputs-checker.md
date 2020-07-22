---
title: Kontrola různých vstupů – pro vývojová prostředí
description: 'Přečtěte si o nástroji Microsoft QDK DISTINCT Inputs Checker, který používá simulátor trasování doby využívání, ke kontrole kódu Q # pro případné konflikty se sdílenými qubits.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 49a1ccc5f37acfeaa1ee08bd974be45a40a76f93
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871140"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a>Simulátor trasování doby využití: Kontrola různých vstupů

Nástroj pro kontrolu různých vstupů je součástí nástroje pro vývoj po částech. [simulátor trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro). Můžete ji použít ke zjištění potenciálních chyb v kódu způsobených konflikty se sdílenými qubits. 

## <a name="conflicts-with-shared-qubits"></a>Konflikty se sdílenými qubits

Vezměte v úvahu následující část kódu Q # a ilustrujte problémy zjištěné nástrojem pro kontrolu různých vstupů:

```qsharp
operation ApplyBoth(
    q1 : Qubit,
    q2 : Qubit,
    op1 : (Qubit => Unit),
    op2 : (Qubit => Unit))
: Unit {
    op1(q1);
    op2(q2);
}
```

Když se podíváte na tento program, můžete předpokládat, že pořadí, ve kterém se volá `op1` `op2` , nezáleží na tom, protože `q1` a `q2` jsou různé qubits a operace fungující na různých qubits dojíždění. 

Nyní vezměte v úvahu tento příklad:

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

Všimněte si, že `op1` a `op2` jsou získány pomocí částečné aplikace a sdílejí qubit. Při volání `ApplyBoth` v tomto příkladu výsledek operace závisí na pořadí `op1` a `op2` uvnitř `ApplyBoth` Not, co byste měli očekávat. Povolíte-li nástroj pro kontrolu různých vstupů, detekuje takové situace a vyvolá `DistinctInputsCheckerException` . Další informace najdete v tématu <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> v knihovně rozhraní API Q #.

## <a name="invoking-the-distinct-inputs-checker"></a>Vyvolání kontroly různých vstupů

Chcete-li spustit simulátor trasování doby provozu s nástrojem pro kontrolu různých vstupů, je nutné vytvořit <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instanci, nastavit `UseDistinctInputsChecker` vlastnost na **hodnotu true**a poté vytvořit novou <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instanci s `QCTraceSimulatorConfiguration` parametrem. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a>Použití kontroly různých vstupů v hostitelském programu C#

Následuje příklad hostitelského programu C#, který používá simulátor trasování doby využívání, se zapnutou kontrolou různých vstupů:

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            var traceSimCfg = new QCTraceSimulatorConfiguration();
            traceSimCfg.UseDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a>Viz také

- Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) pro všechna ta.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Reference k rozhraní API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Reference k rozhraní API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException>Reference k rozhraní API.
