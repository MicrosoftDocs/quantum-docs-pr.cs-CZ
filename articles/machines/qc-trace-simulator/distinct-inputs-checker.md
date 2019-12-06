---
title: Kontrola různých vstupů | Simulátor sledování počítačového systému | Microsoft Docs
description: Přehled simulátoru trasování kvantového počítače
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: ce3f156a84a4509781a74c9276b953c79670a756
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864300"
---
# <a name="distinct-inputs-checker"></a>Kontrola různých vstupů

`Distinct Inputs Checker` je součástí [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)počítačů. Je navržena pro detekci potenciálních chyb v kódu. Zvažte následující část kódu Q # pro ilustraci problémů zjištěných tímto balíčkem:

```qsharp
operation DoBoth(q1 : Qubit, q2 : Qubit, op1 : (Qubit => Unit), op2 : (Qubit => Unit)) : Unit {

    op1(q1);
    op2(q2);
}
```

Když uživatel tento program prohlíží, předpokládá se, že pořadí, ve kterém `op1` a `op2` jsou volána, nezáleží na tom, že `q1` a `q2` jsou různé qubits a operace fungující na různých qubitsích dojíždění. Nyní si představte, že jsme si vybrali příklad, kde se tato operace používá:

```qsharp
operation CapturedQubits () : Unit {

    using (q = Qubit[3]) {
        let op1 = CNOT(_, q[1]);
        let op2 = CNOT(q[1], _);
        DoBoth(q[0], q[2], op1, op2);
    }
}
```

Nyní `op1` a `op2` jsou získány pomocí částečné aplikace a sdílejí qubit. Pokud uživatel volá `DoBoth` v příkladu výše, výsledkem operace bude záviset na pořadí `op1` a `op2` v `DoBoth`. To znamená, že nebudete mít k tomu uživatele očekávat. `Distinct Inputs Checker` zjistí takové situace, pokud jsou povoleny, a vyvolá `DistinctInputsCheckerException`. Další podrobnosti najdete v dokumentaci k rozhraní API v [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) .

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a>Použití kontroly různých vstupů v C# programu

Tady je příklad kódu C# ovladače pro použití simulátoru trasování počítače v% s povolenou možností `Distinct Inputs Checker`:

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

Třída `QCTraceSimulatorConfiguration` ukládá konfiguraci simulátoru trasování počítačů a může být poskytnuta jako argument pro `QCTraceSimulator` konstruktor. Pokud je `useDistinctInputsChecker` nastaveno na hodnotu true, je povolen `Distinct Inputs Checker`. Další podrobnosti najdete v dokumentaci k rozhraní API na [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) a [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) .

## <a name="see-also"></a>Další informace najdete v tématech

- Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítačů ve službě.
