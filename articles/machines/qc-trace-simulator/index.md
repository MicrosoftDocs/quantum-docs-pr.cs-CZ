---
title: Simulátor trasování kvantového počítače
description: Naučte se používat simulátor kvantového trasování od Microsoftu k ladění klasického kódu a odhadu požadavků na prostředky v kvantovém programu.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 4cec688da35951271d87396d9b6a8fed744defc6
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/09/2020
ms.locfileid: "84577661"
---
# <a name="quantum-trace-simulator"></a>Simulátor kvantového trasování

Simulátor trasování kvantového počítače od Microsoftu spouští kvantový program, aniž by ve skutečnosti simuloval stav kvantového počítače.  Simulátor trasování proto může spouštět kvantové programy, které používají tisíce qubitů.  To je užitečné ze dvou hlavních důvodů: 

* Ladění klasického kódu, který je součástí kvantového programu. 
* Odhad prostředků potřebných ke spuštění dané instance kvantového programu v kvantovém počítači.

Simulátor trasování je závislý na dalších informacích poskytovaných uživatelem, když je třeba provést měření. Podrobnější informace najdete v části [Určování pravděpodobnosti výsledků měření](#providing-the-probability-of-measurement-outcomes). 

## <a name="providing-the-probability-of-measurement-outcomes"></a>Určování pravděpodobnosti výsledků měření

V kvantových algoritmech se provádějí dva druhy měření. První druh má doplňující roli tam, kde uživatel zpravidla zná pravděpodobnost výsledků. V takovém případě může uživatel tuto znalost vyjádřit zapsáním operace <xref:microsoft.quantum.intrinsic.assertprob> z oboru názvů <xref:microsoft.quantum.intrinsic>. Ilustruje to následující příklad:

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

Když simulátor trasování provede operaci `AssertProb`, zaznamená, že pro měření `PauliZ` v umístění `source` a `q` by měl být uveden výstup `Zero` s pravděpodobností 0,5. Když simulátor později provede akci `M`, najde zaznamenané hodnoty pravděpodobnosti výstupu a akce `M` vrátí hodnotu `Zero` nebo `One` s pravděpodobností 0,5. Když je stejný kód spuštěn v simulátoru, který sleduje kvantový stav, tento simulátor ověří správnost pravděpodobností v rámci operace `AssertProb`.

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a>Spuštění programu v simulátoru trasování kvantového počítače 

Simulátor trasování kvantového počítače lze vnímat pouze jako další cílový počítač. Program ovladače C# pro jeho použití je velmi podobný programu pro jakýkoli jiný kvantový simulátor. 

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
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

Mějte na paměti, že pokud alespoň jedno měření nemá anotaci vytvořenou operací `AssertProb`, simulátor vygeneruje výjimku `UnconstrainedMeasurementException` z oboru názvů `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators`. Podrobnější informace najdete v dokumentaci k rozhraní API pro výjimku [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException).

Kromě spouštění kvantových programů je simulátor trasování vybaven pěti komponentami pro zjišťování chyb v programech a zjišťování odhadů prostředků kvantových programů: 

* [Kontrola odlišných vstupů](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [Kontrola použití neplatných qubitů](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [Čítač primitivních operací](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [Čítač hloubky okruhu](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [Čítač šířky okruhu](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

Každou z těchto komponent je možné povolit nastavením příslušných příznaků v rámci třídy `QCTraceSimulatorConfiguration`. Podrobnější informace o používání jednotlivých komponent jsou k dispozici v příslušných referenčních souborech. Konkrétní podrobnosti najdete v dokumentaci k rozhraní API pro třídu [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).

## <a name="see-also"></a>Viz také
Reference ke kódu C# [simulátoru trasování](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) kvantového počítače 

