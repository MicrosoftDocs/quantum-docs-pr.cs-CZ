---
title: Kontrola použití neplatných qubitů
description: 'Přečtěte si o nástroji QDK s neplatnými Qubits pro Microsoft, který kontroluje kód Q # pro potenciálně neplatnou Qubits.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: e2bbb12448e27f28db030a0084302fb24f46f26b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274573"
---
# <a name="invalidated-qubits-use-checker"></a>Kontrola použití neověřené Qubits

`Invalidated Qubits Use Checker`Je součástí [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítače, který je navržen pro detekci potenciálních chyb v kódu. Vezměte v úvahu následující část kódu Q # pro ilustraci problémů zjištěných nástrojem `Invalidated Qubits Use Checker` .

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

Při `H` použití na `q[0]` odkazuje na již vydaný qubit. To může způsobit nedefinované chování. Když `Invalidated Qubits Use Checker` je povolená, výjimka se `InvalidatedQubitsUseCheckerException` vyvolá, pokud se operace použije na už vydaný qubit. Další podrobnosti najdete v dokumentaci k rozhraní API v [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) .

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a>Použití funkce Qubits s neověřeným použitím nástroje pro kontrolu použití v programu v C#

Následuje příklad kódu ovladače C# pro použití počítače s příznakem pro práci `Trace
Simulator` s `Invalidated Qubits Use Checker` povoleným: 

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
            traceSimCfg.useInvalidatedQubitsUseChecker = true; // enables useInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

Třída `QCTraceSimulatorConfiguration` ukládá konfiguraci simulátoru trasování počítačů a je možné ho zadat jako argument pro `QCTraceSimulator` konstruktor. Když `useInvalidatedQubitsUseChecker` je nastavená hodnota true, `Invalidated Qubits Use Checker` je povolený. Další podrobnosti najdete v dokumentaci k rozhraní API na [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) a [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) .

## <a name="see-also"></a>Viz také ##

- Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítačů ve službě.
