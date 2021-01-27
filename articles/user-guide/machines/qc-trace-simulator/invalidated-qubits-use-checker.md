---
title: Kontrola použití neověřených qubits – sada pro vývoj všech procesorů
description: Přečtěte si o nástroji Microsoft QDK invalidateed qubits pro kontrolu použití, který používá simulátor trasování doby provozu ke kontrole Q# kódu pro potenciálně neplatnou qubits.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9014097ace7c9f19d93a92372da40f71fa7f87ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858625"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a>Simulátor trasování provozu: neověřená Kontrola použití qubits

Nástroj pro kontrolu použití neověřených qubits je součástí nástroje pro vybudování doby [provozu.](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Můžete ji použít ke zjištění potenciálních chyb v kódu způsobených neplatným qubits. 

## <a name="invalid-qubits"></a>Neplatný qubits

Vezměte v úvahu následující část Q# kódu pro ilustraci problémů zjištěných neověřeným qubits použití nástroje:

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

Při použití `H` operace na `q[0]` , odkazuje na již vydaný qubit, což může způsobit nedefinované chování. Pokud je povolená funkce Qubits pro kontrolu použití, vyvolá výjimku, `InvalidatedQubitsUseCheckerException` Pokud program použije operaci na už vydaný qubit. Další informace naleznete v tématu <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.InvalidatedQubitsUseCheckerException>.

## <a name="invoking-the-invalidated-qubits-use-checker"></a>Vyvolává se qubits pro kontrolu použití neověřených

Chcete-li spustit simulátor trasování doby provozu s neověřeným qubits, je nutné vytvořit <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instanci, nastavit `UseInvalidatedQubitsUseChecker` vlastnost na **hodnotu true** a poté vytvořit novou <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instanci s `QCTraceSimulatorConfiguration` parametrem. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a>Použití funkce qubits s neověřenou kontrolou v hostitelském programu C#

Následuje příklad hostitelských programů v jazyce C#, které používají simulátor trasování doby provozu s povoleným qubitsm ověřováním pomocí služby invalidateed: 

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
            traceSimCfg.UseInvalidatedQubitsUseChecker = true; // enables UseInvalidatedQubitsUseChecker
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
- <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.InvalidatedQubitsUseCheckerException>Reference k rozhraní API.
