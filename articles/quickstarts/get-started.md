---
uid: microsoft.quantum.welcome
title: Začínáme se sadou Quantum Development Kit (QDK)
description: Naučte se programovat kvantové projekty v jazyce Q# s využitím sady Microsoft Quantum Development Kit.
author: bradben
ms.author: bradben
ms.date: 5/10/2020
ms.topic: overview
no-loc:
- Q#
- $$v
ms.openlocfilehash: ff5eb9984da0b22a65f3919599ee18605a206fa0
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867507"
---
# <a name="get-started-with-the-quantum-development-kit-qdk"></a>Začínáme se sadou Quantum Development Kit (QDK)

Vítejte u sady Microsoft Quantum Development Kit!  

Sada Quantum Development Kit obsahuje všechny nástroje, které budete potřebovat k vytváření vlastních kvantových programů a experimentů s využitím Q#, programovacího jazyka navrženého speciálně pro vývoj kvantových aplikací.

Pokud chcete rovnou začít, přejděte k [průvodci instalací sady QDK](xref:microsoft.quantum.install).
Provede vás instalací sady Quantum Development Kit na počítačích se systémem Windows, Linux nebo MacOS, abyste mohli psát své vlastní kvantové programy.

Pokud s kvantovými výpočty teprve začínáte, přečtěte si [Přehled](xref:microsoft.quantum.overview.introduction), kde se dozvíte, co můžou kvantové počítače dělat a na čem jsou kvantové výpočty založeny.

## <a name="get-started-programming"></a>Začínáme s programováním

Sada Quantum Development Kit nabízí řadu způsobů, jak se naučit vyvíjet kvantové programy s využitím Q#.
Chcete-li rychle začít pracovat na kvantových výpočtech, vyzkoušejte některý z našich kurzů:

* [Kvantový generátor náhodných čísel](xref:microsoft.quantum.quickstarts.qrng) – Začněte od kvantové varianty aplikace Q# Hello World, která vám poskytne stručné seznámení s koncepcí kvantových výpočtů a umožní vám během několika minut sestavit a spustit první kvantovou aplikaci.
* [Základy kvantových výpočtů s využitím jazyka Q#](xref:microsoft.quantum.write-program) – Tento kurz vás provede napsáním programu v Q#, který ukazuje některé ze základních konceptů kvantového programování.
    Pokud na programování nejste připravení, můžete pokračovat i bez instalace sady QDK. Získáte přehled o programovacím jazyku Q# a základních koncepcích kvantových výpočtů.
* [Groverův vyhledávací algoritmus](xref:microsoft.quantum.quickstarts.search) – Prozkoumáním tohoto příkladu programu v jazyce Q# získáte představu o síle jazyka Q# při vyjadřování kvantových algoritmů způsobem abstrahujícím od kvantových operací nízké úrovně.
    Tento kurz vás provede vývojem programu v jazyce Q# ve formě aplikace příkazového řádku pomocí sady Visual Studio nebo Visual Studio Code.

### <a name="learning-further"></a>Získávání dalších informací
* [Moduly Microsoft Learn pro kvantové výpočty](https://docs.microsoft.com/learn/browse/?term=quantum) vás seznámí se základními koncepty vaší vlastní rychlostí a podle vašich časových možností. Základní informace o tom, jak pomocí sady QDK vytvářet kvantové programy, najdete v [prvním modulu](https://docs.microsoft.com/learn/modules/qsharp-create-first-quantum-development-kit/).
* Pokud se chcete do programování v Q# ponořit hlouběji, projděte si [kvantové katy](https://github.com/Microsoft/QuantumKatas). Tato kolekce programovacích cvičení umožňujících postupovat vlastním tempem vám představí kvantové výpočetní funkce prostřednictvím programování v jazyce Q#.
    Mnohé z těchto kat jsou k dispozici také jako poznámkové bloky v Q#. 
* Naše [úložiště ukázek](https://github.com/Microsoft/Quantum) předvádí několik příkladů, jak psát kvantové programy s využitím Q#. Řada těchto příkazů je napsaná s využitím našich opensourcových [kvantových knihoven](https://github.com/Microsoft/QuantumLibraries), včetně naší [standardní](xref:microsoft.quantum.libraries.standard.intro) knihovny a knihovny pro [chemii](xref:microsoft.quantum.chemistry.concepts.intro) (další informace o těchto knihovnách najdete níž).

## <a name="key-concepts-for-quantum-computing"></a>Klíčové koncepty kvantových výpočtů

Uvědomujeme si, že pokud s kvantovým vývojem teprve začínáte, může vám to všechno připadat poněkud náročné. Tyto klíčové koncepty vám pomohou vykročit do kvantového světa a porozumět tomu, čím se kvantové počítače liší od těch klasických.

* [Principy kvantových výpočtů](xref:microsoft.quantum.overview.understanding)
* [Kvantové počítače a kvantové simulátory](xref:microsoft.quantum.overview.simulators)
* [Co je programovací jazyk Q# a sada QDK?](xref:microsoft.quantum.overview.q-sharp)
* [Lineární algebra pro kvantové výpočty](xref:microsoft.quantum.overview.algebra)

## <a name="quantum-development-kit-documentation"></a>Dokumentace k sadě Quantum Development Kit

Aktuální dokumentace obsahuje následující dodatečná témata.

### <a name="no-locq-developer-guides"></a>Příručky pro vývojáře v Q#

* [Uživatelská příručka Q#](xref:microsoft.quantum.guide) podrobně popisuje základní koncepty, které se používají k vytvoření kvantových programů v jazyce Q#.
* Oddíl [Kvantové simulátory a hostitelské aplikace](xref:microsoft.quantum.machines) popisuje, jak se spouštějí kvantové algoritmy, jaké kvantové počítače jsou k dispozici a jak napsat ovladač pro kvantový program v jiném jazyce než Q#.

### <a name="no-locq-libraries"></a>Knihovny Q#

* Oddíl [Standardní knihovny Q#](xref:microsoft.quantum.libraries.standard.intro) popisuje operace a funkce, které podporují jak požadavky řízení klasických jazyků, tak kvantové algoritmy v jazyce Q#. 
    Jednotlivá témata se zaměřují na tok řízení, datové struktury, opravy chyb, testování a ladění. 
* Oddíl [Chemické knihovny Q#](xref:microsoft.quantum.chemistry.concepts.intro) popisuje operace a funkce, které podporují simulaci kvantové chemie, která představuje stěžejní oblast využití kvantových výpočtů. Jednotlivá témata se zaměřují mimo jiné na simulaci hamiltoniánské dynamiky a odhady kvantové fáze.
* Oddíl [Numerické knihovny Q#](xref:microsoft.quantum.numerics.intro) popisuje operace a funkce, které podporují vyjadřování složitých aritmetických funkcí v nativních operacích cílových počítačů.
* Oddíl [Referenční dokumentace knihoven Q#](xref:microsoft.quantum.standardlibsintro) obsahuje referenční informace k jednotlivým knihovním entitám podle oboru názvů.

### <a name="general-quantum-computing"></a>Obecné kvantové výpočty

* Oddíl [Koncepce kvantových výpočtů](xref:microsoft.quantum.concepts.intro) zahrnuje témata, jako je relevance lineární algebry pro kvantové výpočty, povaha a využití qubitu, vysvětlení kvantového obvodu a další.
* [Slovníček kvantových výpočtů](xref:microsoft.quantum.glossary) je slovník obsahující některé důležité termíny z oblasti kvantových výpočtů a vývoje programů.
    Pokud s touto problematikou teprve začínáte, mohl by pro vás být užitečnou pomůckou při pročítání naší dokumentace.
* Oddíl [Další čtení](xref:microsoft.quantum.more-information) obsahuje speciálně vybrané reference pro podrobnější pokrytí témat kvantových výpočtů.

### <a name="additional-info"></a>Další informace

* [Poznámky k verzi sady Microsoft Quantum Development Kit](xref:microsoft.quantum.relnotes)


## <a name="be-a-part-of-the-no-locq-open-source-community"></a>Staňte se součástí opensourcové komunity Q#

Quantum Development Kit je opensourcová vývojářská sada, která umožňuje vývojářům zpřístupnit kvantové výpočty všem, abychom mohli začít řešit některé z nejnáročnějších výzev dnešní doby.  Akademické instituce, které vyžadují opensourcový software, budou schopné nasadit Q# pro svoji kvantovou výuku a vývoj. Skutečnost, že se tato vývojářská sada poskytuje jako open source, také dává vývojářům a odborníkům v jednotlivých oblastech příležitost, aby prostřednictvím svého kódu přispívali svými nápady a vylepšeními.

Vaše názory, angažovanost a příspěvky k sadě Quantum Development Kit jsou důležité.  Pokud se chcete dovědět víc o zdrojích sady Quantum Development Kit, poskytnout zpětnou vazbu a zjistit, jak se dá zapojit do rozhodování a přispívání k této rozvíjející se platformě pro kvantový vývoj, projděte si téma věnované [příspěvkům k sadě Quantum Development Kit](xref:microsoft.quantum.contributing).

Pokud vás zajímají obecnější informace o iniciativě Microsoftu v oblasti kvantových výpočtů, projděte si [Microsoft Quantum](https://www.microsoft.com/en-us/quantum/).
