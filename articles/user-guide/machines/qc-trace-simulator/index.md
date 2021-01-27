---
title: Simulátor kvantového trasování – Quantum Development Kit
description: Naučte se používat simulátor kvantového trasování od Microsoftu k ladění klasického kódu a odhadu požadavků na prostředky v programu v Q#.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1e9207d7dcd6ec09353b234654e0567b377144e9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858639"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a>Simulátor kvantového trasování sady Quantum Development Kit (QDK)

Třída <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> v QDK spouští kvantové programy, aniž by simulovala stav kvantového počítače. Z tohoto důvodu může simulátor kvantového trasování spouštět kvantové programy, které používají tisíce qubitů.  To je užitečné ze dvou hlavních důvodů: 

* Ladění klasického kódu, který je součástí kvantového programu. 
* Odhad prostředků potřebných ke spuštění dané instance kvantového programu v kvantovém počítači. [Estimátor prostředků](xref:microsoft.quantum.machines.resources-estimator), který poskytuje omezenější sadu metrik, je ve skutečnosti založený na simulátoru trasování.

## <a name="invoking-the-quantum-trace-simulator"></a>Vyvolání simulátoru kvantového trasování

Simulátor kvantového trasování můžete využít ke spuštění libovolné operace Q#.

Stejně jako u jiných cílových počítačů nejdřív vytvoříte instanci třídy `QCTraceSimulator` a předáte ji jako první parametr metody `Run` příslušné operace.

Na rozdíl od třídy `QuantumSimulator` ale třída `QCTraceSimulator` neimplementuje rozhraní <xref:System.IDisposable>, a proto ji není nutné uzavírat příkazem `using`.

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

## <a name="providing-the-probability-of-measurement-outcomes"></a>Určování pravděpodobnosti výsledků měření

Vzhledem k tomu, že simulátor kvantového trasování nesimuluje skutečný kvantový stav, není možné vypočítat pravděpodobnost výsledků měření v rámci operace. 

Proto pokud operace obsahuje měření, je nutné explicitně poskytnout tyto pravděpodobnosti pomocí operace <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> z oboru názvů <xref:Microsoft.Quantum.Diagnostics>. Ilustruje to následující příklad:

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

Když simulátor kvantového trasování narazí na operaci `AssertMeasurementProbability`, zaznamená, že pro měření `PauliZ` v umístění `source` a `q` by měl být uveden výstup `Zero` s pravděpodobností **0,5**. Když později spustí operaci `M`, najde zaznamenané hodnoty pravděpodobnosti výsledků a `M` vrátí `Zero` nebo `One`, a to s pravděpodobností **0,5**. Pokud stejný kód běží v simulátoru, který sleduje kvantový stav, tento simulátor ověří správnost pravděpodobností v rámci operace `AssertMeasurementProbability`.

Mějte na paměti, že pokud alespoň jedna operace měření nemá anotaci vytvořenou pomocí `AssertMeasurementProbability`, simulátor vygeneruje [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).

## <a name="quantum-trace-simulator-tools"></a>Nástroje simulátoru kvantového trasování

Sada QDK zahrnuje pět nástrojů, které můžete použít se simulátorem kvantového trasování k detekci chyb ve vašich programech a provádění odhadů prostředků kvantových programů: 

|Nástroj | Popis |
|-----| -----|
|[Kontrola odlišných vstupů](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |Kontroluje možné konflikty se sdílenými qubity. |
|[Kontrola použití neplatných qubitů](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |Kontroluje, jestli program používá operaci na qubit, který už je vydaný. |
|[Čítač primitivních operací](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | Zjišťuje počet primitiv použitých všemi operacemi vyvolanými kvantovým programem.  |
|[Čítač hloubky](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |Shromažďuje počty, které reprezentují dolní hranici hloubky operací vyvolaných v kvantovém programu.   |
|[Čítač šířky](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |Zjišťuje počet qubitů přidělených a vypůjčených jednotlivými operacemi v kvantovém programu. |

Každý z těchto nástrojů se aktivuje nastavením příslušných příznaků v `QCTraceSimulatorConfiguration` a následným předáním této konfigurace do deklarace `QCTraceSimulator`. Informace o použití každého z těchto nástrojů najdete pod odkazy v předchozím seznamu. Další informace týkající se konfigurace `QCTraceSimulator` najdete v tématu [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).

## <a name="qctracesimulator-methods"></a>Metody QCTraceSimulatoru

`QCTraceSimulator` má několik předdefinovaných metod pro načtení hodnot metrik trasovaných během kvantové operace. Příklady metod [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) a [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) najdete ve článcích [Čítač primitivních operací](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Čítač hloubky](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) a [Čítač šířky](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter). Další informace o veškerých dostupných metodách najdete v referenčních informacích k rozhraní API pro Q# v tématu [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator).  

## <a name="see-also"></a>Viz také

- [Estimátor kvantových prostředků](xref:microsoft.quantum.machines.resources-estimator)
- [Kvantový simulátor Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)
- [Simulátor celkového kvantového stavu](xref:microsoft.quantum.machines.full-state-simulator) 