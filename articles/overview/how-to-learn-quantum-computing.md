---
title: Jak se naučit provádět kvantové výpočty s využitím jazyka Q#?
description: Zdroje informací pro základní matematické a fyzikální znalosti, které vám pomůžou začít s kvantovými výpočty
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.learn
ms.openlocfilehash: 17fc4e7a73f93a86d981996bf8b59309bccb6e67
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907745"
---
# <a name="how-to-learn-about-quantum-computing"></a>Jak se o kvantových výpočtech dozvědět víc?

Využijte pomoc se získáváním informací o kvantových výpočtech a psaním prvních programů. Tento popis není vyčerpávající, spíš se jedná o vhodné místo, na kterém můžete začít.

## <a name="getting-started-overview"></a>Začínáme – přehled

[Začínáme se sadou Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome) poskytuje základní přehled kvantového výpočetního prostředí s jazykem Q#, včetně kurzů psaní vašeho prvního programu Q#, úvodních příruček a úvodu do kvantové knihovny Q# pro vývoj kvantových programů.

## <a name="learning-the-basics-what-do-you-need-to-know"></a>Seznámení se základy: co potřebujete znát?

Na to, abyste se naučili pracovat s jazykem Q# a provádět kvantové výpočty nebo začali psát kvantové aplikace, nemusíte ovládat kvantovou fyziku.

Tyto koncepce vám poskytnou odpovídající úvod k základním znalostem, které budete potřebovat při psaní kvantových programů.  

* [Základy kvantové mechaniky](xref:microsoft.quantum.concepts.intro): Právě jsme řekli, že nepotřebujete znát kvantovou fyziku, abyste mohli začít psát programy (a je to pravda!). Některé základní koncepce kvantové mechaniky a její matematická notace vám však pomůžou porozumět kvantovému programování.

* **Lineární algebra (vektory a matice)** : V kvantových výpočtech jsou kvantové stavy reprezentovány vektory a kvantové operace jsou lineární transformace aplikované na tyto vektory.  Tady je [kurz ve formě poznámkového bloku Jupyter pro lineární algebru](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra).  Další informace o lineární algebře najdete v našem průvodci koncepcemi [vektorů a matic](xref:microsoft.quantum.concepts.vectors).

* **Komplexní aritmetika**: Koeficienty vektorů kvantového stavu jsou komplexní čísla. Některé koncepce kvantových výpočtů pochopíte i bez nich, nedojdete však daleko, než je budete muset zahrnout do své kvantové sady nástrojů.  Tady je [kurz ve formě poznámkového bloku Jupyter pro komplexní aritmetiku](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic), který vysvětluje některé aspekty matematického pozadí, které jsou potřeba pro práci s kvantovým výpočetním prostředím. 

Teď už rozumíte základům a jste připravení začít se učit psát kvantové programy.  Existuje mnoho způsobů, jak pokračovat:

## <a name="do-the-quantum-katas"></a>Procházení kvantových kat

[Kvantové katy](xref:microsoft.quantum.overview.katas) jsou opensourcové série kurzů umožňujících postupovat vlastním tempem, které jsou zaměřené na výuku prvků kvantových výpočtů a programování v Q# současně.  Každá kata odkazuje na další studijní materiály, které můžete použít k získání informací o konceptech kvantových výpočtů potřebných k úspěšnému dokončení kat.  

## <a name="dive-into-the-theory"></a>Ponořte se do teorie

Možná se budete chtít blíž podívat na teorii kvantové mechaniky a kvantových výpočtů. Tady je seznam užitečných materiálů:

* Začněte příručkou [koncepcí kvantových výpočtů](xref:microsoft.quantum.concepts.intro), což je soubor základních koncepcí kvantových výpočtů.
* Článek _Naučte se kvantové výpočty v Pythonu a Q#_ (od Sarah C. Kaiser a Christophera E. Granade) je vynikajícím úvodem pro ty, kdo nemají téměř žádné nebo vůbec žádné zkušenosti s kvantovou mechanikou, ale s programováním ano.
* _Kvantové výpočty a informace o kvantovém přístupu_ (od Michaela A. Nielsena a Isaaca L. Chuanga) jsou nejčastěji citovaným materiálem v oblasti kvantových výpočtů a považují se v této oblasti za standard. Tato kniha předpokládá minimální předchozí zkušenosti s kvantovou mechanikou a informatikou. Je skvělou volbou pro čtenáře, kteří hledají podrobný úvod do tématu, i pro ty, kdo chtějí najít odkazy na pokročilé koncepce.
* OpenCourseWare na MIT nabízí skvělý [online kurz](https://www.youtube.com/watch?v=lZ3bPUKo5zc&list=PLUl4u3cNGP61-9PEhRognw5vryrSEVLPr) vedený Allanem Adamsem, kde se můžete naučit základy kvantové mechaniky. Je ideální pro vývojáře, kteří chtějí lépe porozumět fyzice, která tvoří základ.

## <a name="join-the-quantum-community"></a>Přidejte se ke kvantové komunitě

Nemusíte se učit sami, je tady rozsáhlá komunita amatérů i odborníků ochotných pomoct vám. Nebojte se zeptat!

* Pokud máte nějaké otázky týkající se jazyka Q# nebo kvantových výpočtů, nečekejte a podívejte se na web Quantum Computing StackExchange. Pokud tam svou konkrétní otázku nenajdete, můžete ji kdykoli položit. 
* Podívejte se na [blog o jazyku Q#](https://devblogs.microsoft.com/qsharp/) a na [blog Microsoft Quantum](https://cloudblogs.microsoft.com/quantum/) – najdete tam novinky a zdroje informací o jazyku Q#.
* Pokud hledáte další zdroje a materiály, prozkoumejte [komunitu Q#](https://qsharp.community/) a web [Awesome Q#](https://project-awesome.org/ebraminio/awesome-qsharp).

 Pokud se chystáte učit kurz kvantových výpočtů, [Microsoft Quantum Network](https://info.microsoft.com/LearnMoreAboutMicrosoftQuantumNetwork.html) vám může poskytnout pomoc se studiem.  

