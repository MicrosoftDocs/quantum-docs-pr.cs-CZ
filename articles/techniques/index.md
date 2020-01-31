---
title: Techniky kvantového vývoje | Microsoft Docs
description: Techniky kvantového vývoje
keywords: Nepřidávejte ani neupravujte klíčová slova, aniž byste se poradili se svým odborníkem na SEO.
author: QuantumWriter
ms.author: MSFT-alias-person-or-DL
ms.date: 9/20/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.techniques.intro
ms.openlocfilehash: c1263edb75f903702ab3c16cec0443857150b662
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820806"
---
# <a name="quantum-development-techniques"></a>Techniky kvantového vývoje

Tato část dokumentace podrobně popisuje základní koncepce používané při vytváření kvantových programů v jazyku Q# a při interakci s těmito programy z klasických aplikací.
Předpokládáme *určité* znalosti kvantových výpočetních konceptů, jako jsou ty, které jsou popsané v části [Koncepce kvantových výpočtů](xref:microsoft.quantum.concepts.intro), ale spoustu se dozvíte, i když nejste odborníkem na kvantové výpočty.

Obsah je následující.

- [Přehled programů v jazyce Q#](xref:microsoft.quantum.techniques.file-structure) poskytuje náhled na účel a funkce programovacího jazyka Q#. 
    Konkrétně vysvětluje, že Q# *není* jazyk pro pouhé simulace kvantové mechaniky, ačkoli tato funkce je samozřejmě naším simulátorem celkového stavu poskytována. 
    Jazyk Q# byl spíš navržen s ohledem na budoucnost a jeho programy popisují, jak počítač s klasickým řízením *interaguje* s qubity. 

- Část [Operace a funkce](xref:microsoft.quantum.techniques.opsandfunctions) detailně popisuje dva volatelné typy jazyka Q#: *operace*, které zahrnují akci s qubity a kvantovými systémy, a *funkce*, které pracují výhradně s klasickými informacemi. 
    Bez spolupráce klasických a kvantových informací by kvantové výpočty zůstaly nedosažitelné. 
    Tato část popisuje, jak definovat a používat tyto volatelné položky v rámci toku řízení programu v Q#.

- Část [Místní proměnné](xref:microsoft.quantum.techniques.local-variables) popisuje roli proměnných v programech v jazyce Q# a jejich efektivní využití. 
    Zejména se dozvíte rozdíl mezi neměnnými a měnitelnými proměnnými a způsob jejich přiřazení nebo opětovného přiřazení.

- Část [Práce s qubity](xref:microsoft.quantum.techniques.qubits) popisuje funkce jazyka Q#, které můžete použít k adresování jednotlivých qubitů a systémů qubitů. 
    Konkrétně to zahrnuje jejich přidělení, provádění operací s nimi a nakonec jejich měření. 
    Navíc se naučíte několik užitečných technik toku řízení.

- V části [Spojení všech součástí dohromady](xref:microsoft.quantum.techniques.puttingittogether) využijete techniky z výše uvedených částí a vytvoříte program, který provádí **kvantovou teleportaci**: pomocí dvou klasických bitů „teleportuje“ úplný stav jednoho qubitu na jiný.

- Část [Další pokračování](xref:microsoft.quantum.techniques.going-further) představuje pokročilé techniky, které se můžou ukázat užitečné, až budete přecházet ke komplexnějšímu kvantovému programování. 
    Konkrétně se podíváme na použití operací a funkcí v jazyce Q# s *typovou parametrizací*, které umožňují tok řízení vyššího řádu tím, že zůstanou agnostické k určitým typům jejich vstupu a výstupu, a také *vypůjčením* qubitů. 
    Tato druhá funkce se liší od základního přidělení qubitů v tom, že operace jazyka Q# může používat „nečisté“ qubity (tj. qubity ne nutně inicializované do známého stavu), aby pomohly při výpočtech.

- Část [Testování a ladění](xref:microsoft.quantum.techniques.testing-and-debugging) podrobně popisuje některé techniky k zajištění, že váš kód dělá to, co by měl. 
    Z důvodu obecné neprůhlednosti kvantových informací může ladění kvantového programu vyžadovat specializované techniky. 
    Naštěstí jazyk Q# podporuje mnoho technik klasického ladění, na které jsou programátoři zvyklí, a také ty, které jsou specifické pro kvantové výpočty. Patří mezi ně vytváření a spouštění testů jednotek v jazyce Q#, vkládání *kontrolních výrazů* pro hodnoty a pravděpodobnosti do kódu a funkce `Dump`, které vypisuje stav cílového počítače. 
    Tyto funkce se dají použít společně s naším simulátorem celkového stavu k ladění určitých částí výpočtů obcházením některých kvantových omezení (např. teorému o nemožnosti klonování).


![Kvantum](~/media/mobius_strip_preview.png)
