---
title: Seznámení s kvantovými katami
description: Další informace o katách (tréninkových cvičeních) poskytovaných se sadou Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 10/17/2019
ms.topic: overview
uid: microsoft.quantum.overview.katas
ms.openlocfilehash: 7fb8dba2a10f9a983ebee52e394260bbdc0d2f9c
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444136"
---
# <a name="learn-quantum-computing-with-the-quantum-katas"></a>Učte se provádět kvantové výpočty s kvantovými katami

[Kvantové katy](https://github.com/Microsoft/QuantumKatas/) jsou opensourcovou sbírkou programovacích cvičení a kurzů umožňujících postupovat vlastním tempem, které jsou zaměřené na výuku prvků kvantových výpočtů a programování v Q# současně.

## <a name="learning-by-doing"></a>Praktická výuka

Kurzy a katy shromážděné v tomto projektu jsou zaměřené na praktickou výuku: nabízí programovací úkoly, které pokrývají určitá témata, od velmi jednoduchých k docela náročným. Každý úkol vyžaduje zadání nějakého kódu. První úkoly můžou vyžadovat třeba jenom jeden řádek a poslední už poměrně značný fragment kódu.

Nejdůležitější je, že katy obsahují testovací architekturu, která nastaví, spustí a ověří řešení úloh. To vám dá okamžitou zpětnou vazbu k vašemu řešení a umožní znovu si promyslet přístup, pokud není správný.

Katy můžete použít k učení v prostředí podle vaší volby:

* Online poznámkové bloky Jupyter v rámci prostředí Binder
* Poznámkové bloky Jupyter spuštěné ve vašem místním počítači
* Visual Studio
* Visual Studio Code

## <a name="what-can-i-learn-with-the-quantum-katas"></a>Jak se můžu učit s využitím kvantových kat?

Tady je souhrn hlavních témat popsaných v kvantových katách. Doporučujeme vám na začátku postupovat podle tohoto studijního programu, abyste si bezpečně osvojili základní koncepce kvantových výpočtů. Samozřejmě můžete přeskočit témata, která ovládáte, jako je komplexní aritmetika, a učit se algoritmy v libovolném pořadí.

### <a name="introduction-to-quantum-computing-concepts"></a>Úvod do koncepcí kvantových výpočtů

* [Komplexní aritmetika](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/ComplexArithmetic)
* [Lineární algebra](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/LinearAlgebra)
* [Koncepce qubitu](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/Qubit)
* [Jednoqubitová kvantová hradla](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/SingleQubitGates)

### <a name="quantum-computing-fundamentals"></a>Základní kvantových výpočtů

* [Rozlišování kvantových hradel](https://github.com/microsoft/QuantumKatas/tree/master/BasicGates)
* [Vytváření kvantové superpozice](https://github.com/microsoft/QuantumKatas/tree/master/Superposition)
* [Rozlišování kvantových stavů pomocí měření](https://github.com/microsoft/QuantumKatas/tree/master/Measurements)
* [Spojená měření](https://github.com/microsoft/QuantumKatas/tree/master/JointMeasurements)

### <a name="algorithms"></a>Algoritmy

* [Kvantová teleportace](https://github.com/microsoft/QuantumKatas/tree/master/Teleportation)
* [Superhusté kódování](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)
* [Deutsch-Jozsův algoritmus](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/DeutschJozsaAlgorithm)
* [Implementace Groverova vyhledávacího algoritmu](https://github.com/microsoft/QuantumKatas/tree/master/GroversAlgorithm)
* [Zkoumání vlastností Groverova vyhledávacího algoritmu na vysoké úrovni](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/ExploringGroversAlgorithm)
* Řešení reálných problémů pomocí Groverova algoritmu: [Problémy SAT](https://github.com/microsoft/QuantumKatas/blob/master/SolveSATWithGrover) a [problémy barvení grafu](https://github.com/microsoft/QuantumKatas/blob/master/GraphColoring)

### <a name="protocols-and-libraries"></a>Protokoly a knihovny

* [Protokol BB84 pro distribuci kvantových klíčů](https://github.com/microsoft/QuantumKatas/tree/master/KeyDistribution_BB84)
* Oprava kvantových chyb: [kód opravy chyby překlopení bitu](https://github.com/microsoft/QuantumKatas/tree/master/QEC_BitFlipCode)
* [Odhad fáze](https://github.com/microsoft/QuantumKatas/blob/master/PhaseEstimation)
* Kvantová aritmetika: [sestavování sčítaček s přenosem (RPA)](https://github.com/microsoft/QuantumKatas/blob/master/RippleCarryAdder)

### <a name="entanglement-games"></a>Hry s provázáním

* [Hra CHSH](https://github.com/microsoft/QuantumKatas/blob/master/CHSHGame)
* [Hra GHZ](https://github.com/microsoft/QuantumKatas/blob/master/GHZGame)
* [Mermin-Peresův magický čtverec](https://github.com/microsoft/QuantumKatas/tree/master/MagicSquareGame)

## <a name="resources"></a>Zdroje a prostředky

* Kompletní řada [kvantových kat](https://github.com/microsoft/QuantumKatas)
* [Spustit katy online](https://aka.ms/try-quantum-katas)
