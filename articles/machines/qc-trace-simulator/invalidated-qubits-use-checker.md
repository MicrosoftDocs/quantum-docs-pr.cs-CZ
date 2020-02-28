---
title: Kontrola použití neplatných qubitů
description: 'Přečtěte si o nástroji QDK s neplatnými Qubits pro Microsoft, který kontroluje kód Q # pro potenciálně neplatnou Qubits.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: e2bbb12448e27f28db030a0084302fb24f46f26b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907065"
---
# <a name="invalidated-qubits-use-checker"></a>Kontrola použití neověřené Qubits

`Invalidated Qubits Use Checker` je součástí [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítače, který je určený pro detekci potenciálních chyb v kódu. Vezměte v úvahu následující část kódu Q # pro ilustraci problémů zjištěných `Invalidated Qubits Use Checker`.

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

Když se `H` aplikuje na `q[0]` odkazuje na už vydaný qubit. To může způsobit nedefinované chování. Pokud je povolená `Invalidated Qubits Use Checker`, bude vyvolána výjimka `InvalidatedQubitsUseCheckerException`, pokud se operace použije na už vydaný qubit. Další podrobnosti najdete v dokumentaci k rozhraní API v [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) .

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a>Použití funkce Qubits s neověřenou kontrolou v C# programu

Tady je příklad kódu C# ovladače pro použití `Trace
Simulator` počítače s více instancemi s povoleným `Invalidated Qubits Use Checker`em: 

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

Třída `QCTraceSimulatorConfiguration` ukládá konfiguraci simulátoru trasování počítačů a může být poskytnuta jako argument pro `QCTraceSimulator` konstruktor. Pokud je `useInvalidatedQubitsUseChecker` nastaveno na hodnotu true, je povolen `Invalidated Qubits Use Checker`. Další podrobnosti najdete v dokumentaci k rozhraní API na [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) a [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) .

## <a name="see-also"></a>Viz také ##

- Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítačů ve službě.
