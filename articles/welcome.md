---
uid: microsoft.quantum.welcome
title: Začínáme se sadou Quantum Development Kit (QDK)
description: Naučte se programovat kvantové projekty v jazyce Q# s využitím sady Microsoft Quantum Development Kit (QDK).
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: overview
ms.openlocfilehash: cea39e47ec5e7e2ad97adbbb39ba586274564967
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907626"
---
# <a name="get-started-with-the-quantum-development-kit-qdk"></a>Začínáme se sadou Quantum Development Kit (QDK)

Vítejte u sady Microsoft Quantum Development Kit!  
Sada QDK obsahuje všechny nástroje, které budete potřebovat k vytváření vlastních kvantových programů a experimentů s využitím Q#, programovacího jazyka navrženého speciálně pro vývoj kvantových aplikací. 

Pokud chcete rovnou začít, můžete přejít k [průvodci instalací sady QDK](xref:microsoft.quantum.install).
Provede vás instalací sady Quantum Development Kit na počítačích se systémem Windows, Linux nebo MacOS, abyste mohli psát své vlastní kvantové programy.

Pokud si ještě nepřipadáte dost připraveni na to, abyste začali s kódováním, ale chcete získat další informace o kvantových výpočtech a jazyce Q#, doporučujeme, abyste si tento článek přečetli a seznámili se s prostředky, které máte k dispozici. V části [Pět dotazů ke kvantovým výpočtům](#five-questions-about-quantum-computing) najdete přesně ty odkazy, které hledáte!

## <a name="get-started-programming"></a>Začínáme s programováním

Sada Quantum Development Kit nabízí řadu způsobů, jak se naučit vyvíjet kvantové programy s využitím Q#.
Pokud si chcete zajistit rychlé zprovoznění kvantových technologií, můžete vyzkoušet naše *rychlá zprovoznění*:

* [Generátor kvantových náhodných čísel](xref:microsoft.quantum.quickstarts.qrng) je aplikace stylu „Q# Hello World“, která vám zajistí stručné seznámení s koncepcí kvantových výpočtů a umožní sestavit a spustit kvantovou aplikaci během několika minut.
* Příručka [Základy kvantových výpočtů s využitím jazyka Q#](xref:microsoft.quantum.write-program) vás provede napsáním programu v Q#, který ukazuje některé ze základních konceptů kvantového programování. 
    Pokud na programování nejste připravení, můžete pokračovat i bez instalace sady QDK. Získáte přehled o programovacím jazyku Q# a základních koncepcích kvantových výpočtů.
* [Groverův vyhledávací algoritmus](xref:microsoft.quantum.quickstarts.search) nabízí příklad programu v Q#, který vám dá představu o síle jazyka Q# při vyjádření kvantového algoritmu způsobem abstrahujícím od kvantových operací nízké úrovně. 
    Toto rychlé zprovoznění vás provede vývojem tohoto programu s využitím mnoha programovacích prostředí (s hostitelem jazyka Python nebo s hostitelem jazyka .NET a sadou Visual Studio nebo editorem Visual Studio Code).

### <a name="learning-further"></a>Získávání dalších informací
* Pokud se chcete do programování v Q# ponořit hlouběji, projděte si [kvantové katy](https://github.com/Microsoft/QuantumKatas). Tato kolekce programovacích cvičení umožňujících postupovat vlastním tempem vám představí kvantové výpočetní funkce prostřednictvím programování v jazyce Q#.
    Mnohé z těchto kat jsou k dispozici také jako poznámkové bloky v Q#. 
* Naše [úložiště ukázek](https://github.com/Microsoft/Quantum) předvádí několik příkladů, jak psát kvantové programy s využitím Q#. Řada těchto příkazů je napsaná s využitím našich opensourcových [kvantových knihoven](https://github.com/Microsoft/QuantumLibraries), včetně naší [standardní](xref:microsoft.quantum.libraries.standard.intro) knihovny a knihovny pro [chemii](xref:microsoft.quantum.chemistry.concepts.intro) (další informace o těchto knihovnách najdete níž).

## <a name="five-questions-about-quantum-computing"></a>Pět dotazů ke kvantovým výpočtům

Uvědomujeme si, že pokud s kvantovým vývojem teprve začínáte, může vám to všechno připadat poněkud náročné. Zajistili jsme proto materiály, které vám pomohou začít se seznamovat s kvantovými výpočty. Jsme si jistí, že s pomocí těchto krátkých článků dostanete chuť pustit se do programování bez dalších odkladů.
* [Co jsou kvantové výpočty?](xref:microsoft.quantum.overview.what)
* [Co dokážou kvantové počítače?](xref:microsoft.quantum.overview.computers)
* [Proč se učit provádět kvantové výpočty?](xref:microsoft.quantum.overview.why)
* [Co je Q#?](xref:microsoft.quantum.overview.qsharp)
* [Jak se naučit provádět kvantové výpočty s využitím jazyka Q#?](xref:microsoft.quantum.overview.learn)

## <a name="quantum-development-kit-documentation"></a>Dokumentace k sadě Quantum Development Kit

Aktuální dokumentace obsahuje následující dodatečná témata.

### <a name="using-q"></a>Použití Q#
* Oddíl [Techniky kvantového vývoje](xref:microsoft.quantum.techniques.intro) představuje základní koncepce vytváření kvantových programů v jazyce Q#. Jednotlivá témata se zaměřují na struktury souborů, operace a funkce a práci s qubity a k dispozici je i pár pokročilých témat.
* Oddíl [Referenční příručka jazyka Q#](xref:microsoft.quantum.language.intro) podrobně popisuje jazyk Q#, včetně modelu typů, výrazů, příkazů a využití kompilátoru.
* Oddíl [Kvantové simulátory a hostitelské aplikace](xref:microsoft.quantum.machines) popisuje, jak se spouštějí kvantové algoritmy, jaké kvantové počítače jsou k dispozici a jak napsat ovladač pro kvantový program v jiném jazyce než Q#.

### <a name="q-libraries"></a>Knihovny Q#
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


## <a name="be-a-part-of-the-q-open-source-community"></a>Staňte se součástí opensourcové komunity Q#
Quantum Development Kit je opensourcová vývojářská sada, která umožňuje vývojářům zpřístupnit kvantové výpočty všem, abychom mohli začít řešit některé z nejnáročnějších výzev dnešní doby.  Akademické instituce, které vyžadují opensourcový software, budou schopné nasadit Q# pro svoji kvantovou výuku a vývoj. Skutečnost, že se tato vývojářská sada poskytuje jako open source, také dává vývojářům a odborníkům v jednotlivých oblastech příležitost, aby prostřednictvím svého kódu přispívali svými nápady a vylepšeními.

Vaše názory, angažovanost a příspěvky k sadě Quantum Development Kit jsou důležité.  Pokud se chcete dovědět víc o zdrojích sady Quantum Development Kit, poskytnout zpětnou vazbu a zjistit, jak se dá zapojit do rozhodování a přispívání k této rozvíjející se platformě pro kvantový vývoj, projděte si téma věnované [příspěvkům k sadě Quantum Development Kit](xref:microsoft.quantum.contributing).

Pokud vás zajímají obecnější informace o iniciativě Microsoftu v oblasti kvantových výpočtů, projděte si [Microsoft Quantum](https://www.microsoft.com/en-us/quantum/).
