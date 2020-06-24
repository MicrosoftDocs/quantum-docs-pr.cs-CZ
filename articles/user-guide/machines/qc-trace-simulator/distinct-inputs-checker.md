---
title: Kontrola různých vstupů
description: 'Přečtěte si o nástroji Microsoft QDK DISTINCT Input Checker, který zkontroluje kód Q # a ověří potenciální konflikty se sdílenými qubits.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 11a0573242c8afb12f242aa3be5f9cff18290452
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274585"
---
# <a name="distinct-inputs-checker"></a>Kontrola různých vstupů

`Distinct Inputs Checker`Je součástí [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)počítačů. Je navržena pro detekci potenciálních chyb v kódu. Zvažte následující část kódu Q # pro ilustraci problémů zjištěných tímto balíčkem:

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

Když uživatel tento program prohlíží, předpokládá se, že pořadí, ve kterém `op1` a `op2` jsou volány, nezáleží, protože `q1` a `q2` jsou různé qubits a operace fungující na různých qubitsích dojíždění. Nyní si představte, že jsme si vybrali příklad, kde se tato operace používá:

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

Nyní `op1` a `op2` jsou získány pomocí částečné aplikace a sdílejí qubit. Pokud uživatel volá `ApplyBoth` v příkladu výše, výsledek operace bude záviset na pořadí `op1` a `op2` dovnitř `ApplyBoth` . To znamená, že nebudete mít k tomu uživatele očekávat. Vyhledá `Distinct Inputs Checker` takové situace, pokud jsou povoleny, a vyvolá `DistinctInputsCheckerException` . Další podrobnosti najdete v dokumentaci k rozhraní API v [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) .

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a>Použití kontroly různých vstupů v programu v C#

Následuje příklad kódu ovladače jazyka C# pro použití simulátoru trasování počítačů v poli s `Distinct Inputs Checker` povoleným:

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
            traceSimCfg.useDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

Třída `QCTraceSimulatorConfiguration` ukládá konfiguraci simulátoru trasování počítačů a je možné ho zadat jako argument pro `QCTraceSimulator` konstruktor. Když `useDistinctInputsChecker` je nastavená hodnota true, `Distinct Inputs Checker` je povolený. Další podrobnosti najdete v dokumentaci k rozhraní API na [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) a [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) .

## <a name="see-also"></a>Viz také

- Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítačů ve službě.
