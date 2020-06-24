---
title: Simulátor Toffoli pro vývoj pro všechna ta
description: Přečtěte si o simulátoru Microsoft QDKe Toffoli, ke speciálnímu simulátoru pro každý účel, který je možné použít s miliony qubits.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 8a29caaa0fa058600a74e7d130e644374cbfa19c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274681"
---
# <a name="quantum-development-kit-toffoli-simulator"></a>Simulátor Toffoli pro vývoj pro všechna ta

Vývojová sada pro všechna provozní prostředí poskytuje simulátor Toffoli, což je simulátor pro zvláštní účely, který může simulovat algoritmy pro procesory, které jsou omezené na X, CNOT a s více řízenými operacemi X, a to znamená, že jsou k dispozici všechny klasické logiky a výpočty.

I když je simulátor Toffoli mnohem větší omezení operace, než je [úplný stav simulátoru](xref:microsoft.quantum.machines.full-state-simulator), může simulovat mnohem více qubits.
Simulátor Toffoli se dá použít s miliony qubits, zatímco úplný stav simulátoru se obecně omezí na přibližně 30.
Může spouštět a ladit omezené sady algoritmů pro plnění, které jsou napsané v Q # ve vašem počítači. například Oracle pro vyhodnocení logických funkcí lze implementovat pomocí těchto bran a tak testovat v různých velkých číslech qubits pomocí tohoto simulátoru.

Tento simulátor při přístavování se zveřejňuje prostřednictvím `ToffoliSimulator` třídy.
Chcete-li použít simulátor, jednoduše vytvořte instanci této třídy a předejte ji `Run` metodě operace, kterou chcete provést, spolu se zbytkem parametrů:

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a>Jiné operace

`ToffoliSimulator`Podporuje rotace a Exponentiated Pauls, například `R` a `Exp` , pokud se výsledná operace rovná `X` nebo k identitě.

Měření a vyhodnocení jsou podporovány, ale pouze v Pauli `Z` .
Všimněte si, že pravděpodobnost některých měření je vždy rovna 0 nebo 1. simulátor Toffoli neobsahuje náhodnost.

`DumpMachine`a `DumpRegister` jsou podporované.
Nastavují výstup na `Z` základě aktuálního stavu každého qubit, jeden qubit na řádek.

## <a name="qubitcount"></a>QubitCount

Ve výchozím nastavení `ToffoliSimulator` přiděluje prostor pro 65 536 qubits.
Pokud váš algoritmus vyžaduje více než toto, můžete změnit počet qubit zadáním hodnoty `qubitCount` parametru konstruktoru.
Každý další qubit vyžaduje další bajt paměti, takže se neúčtují žádné významné náklady na přeodhad počtu qubits, které budete potřebovat.

Příklad:

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
