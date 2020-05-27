---
title: Úvod do kvantových výpočtů
description: Seznámení s tím, co jsou kvantové výpočty, co zvládnou kvantové počítače a jak se naučit provádět kvantové výpočty
author: bradben
ms.author: bradben
ms.date: 05/05/2020
ms.topic: overview
uid: microsoft.quantum.overview.introduction
ms.openlocfilehash: 7c55420bd35f9b6e0e7ec80ddffe8a861cb7df39
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430777"
---
# <a name="introduction-to-quantum-computing-and-the-quantum-development-kit"></a>Úvod do kvantových výpočtů a sady Quantum Development Kit

Microsoft Quantum Development Kit (QDK) je sada opensourcových nástrojů, které vývojářům pomůžou seznámit se s kvantovými algoritmy a tvorbou kvantových programů. Kvantové počítače slibují vyřešení některých z největších výzev našeho světa – v oblasti životního prostředí, zemědělství, zdraví, energetiky, klimatu, materiálové vědy a dalších, které na své zformulování teprve čekají.  

Některé z těchto problémů překračují možnosti i těch nejvýkonnějších počítačů. Kvantové technologie sice teprve začínají ovlivňovat svět počítačů, ale důsledky mohou být dalekosáhlé a mohou úplně změnit naše uvažování o počítačích.

## <a name="what-is-quantum-computing"></a>Co jsou kvantové výpočty?

V moderním smyslu slovo kvantum označuje nejmenší možnou diskrétní jednotku jakékoli fyzikální vlastnosti, obvykle atomických nebo subatomických částic. Kvantové počítače využívají jako výpočetní jednotky skutečné kvantové částice, umělé atomy nebo souborné vlastnosti skupiny kvantových částic, a jde o velká, složitá a drahá zařízení.

Využitím jedinečných jevů kvantové fyziky při kvantových výpočtech dokážou kvantové počítače rozšířit tradiční metody programování o zcela nové koncepty založené na superpozici, provázání a kvantové interferenci.

## <a name="what-can-a-quantum-computer-do"></a>Co dokáže kvantový počítač?

Kvantový počítač není superpočítač, který zvládne jakoukoli úlohu rychleji než ten klasický, ale existuje několik oblastí, které kvantové počítače zvládají výjimečně dobře.

- [Kvantová simulace](xref:microsoft.quantum.overview.introduction#quantum-simulation)
- [Kryptografie](xref:microsoft.quantum.overview.introduction#cryptography-and-shors-algorithm)
- [Vyhledávání](xref:microsoft.quantum.overview.introduction#search-and-grovers-algorithm)
- [Optimalizace](xref:microsoft.quantum.overview.introduction#quantum-inspired-computing-and-optimization)
- [Strojové učení](xref:microsoft.quantum.overview.introduction#quantum-machine-learning)

## <a name="quantum-simulation"></a>Kvantová simulace

Vzhledem k tomu, že kvantové počítače využívají při výpočtech kvantové jevy, výborně se hodí na modelování jiných kvantových systémů. Příkladem kvantových mechanismů, které můžou kvantové počítače simulovat, je fotosyntéza, supravodivost nebo práce se složitými molekulami.

## <a name="cryptography-and-shors-algorithm"></a>Kryptografie a Shorův algoritmus

V roce 1994 Petr Shor ukázal, že škálovatelný kvantový počítač dokáže prolomit široce rozšířené šifrovací metody, například RSA. Klasická kryptografie spoléhá na výpočetní složitost určitých problémů, jako je například faktorizace celých čísel nebo diskrétní logaritmy, ale mnoho z těchto úloh se dá efektivněji řešit pomocí kvantových počítačů.

## <a name="search-and-grovers-algorithm"></a>Vyhledávání a Groverův algoritmus

V roce 1996 Lov Grover vyvinul kvantový algoritmus, který dramaticky zrychluje vyhledávání v nestrukturované databázi, takže potřebuje méně kroků než jakýkoli algoritmus v klasickém počítači.

## <a name="quantum-inspired-computing-and-optimization"></a>Výpočty a optimalizace inspirované kvantovým přístupem

Algoritmy inspirované kvantovým přístupem využívají kvantové principy ke zvýšení rychlosti a přesnosti, jsou však implementovány na klasických počítačových systémech. Tento přístup umožňuje vývojářům využít sílu nových kvantových postupů již dnes, takže nemusí čekat na fyzické kvantové počítače, které se stále ještě vyvíjejí.

Optimalizace je proces nalezení nejlepšího řešení problému s ohledem na požadovaný výsledek a zadané omezující podmínky. Při kriticky důležitých rozhodnutích ve vědě a průmyslu hrají důležitou roli faktory jako náklady, kvalita nebo doba výroby. Algoritmy inspirované kvantovým přístupem, ale spouštěné na současných počítačích, dokážou najít řešení, která byla dosud nedosažitelná. Vedle optimalizace dopravy kvůli předcházení zácpám může jít třeba o problém přiřazování stojánek letadlům, doručování zásilek, plánování úloh a další. Zásadní objevy v oblasti materiálové vědy můžou vést k novým formám energie, bateriím s větší kapacitou nebo lehčím a pevnějším materiálům.

> [!NOTE]
> Přečtěte si více o tom, jak se výpočty inspirované kvantovým přístupem vyvinuté společností Microsoft používá v [materiálové vědě](https://cloudblogs.microsoft.com/quantum/2020/01/21/oti-lumionics-accelerating-materials-design-microsoft-azure-quantum/), [řízení rizik](https://cloudblogs.microsoft.com/quantum/2019/05/22/microsoft-quantum-collaborates-with-willis-towers-watson-to-transform-risk-management-solutions/) a [medicíně](https://blogs.microsoft.com/blog/2018/05/18/microsoft-quantum-helps-case-western-reserve-university-advance-mri-research/).

## <a name="quantum-machine-learning"></a>Kvantové strojové učení

Strojové učení na klasických počítačích způsobilo ve světě vědy a obchodu skutečný převrat. Vysoké výpočetní náklady na trénování modelů však brzdí vývoj a rozsah nasazení tohoto oboru. Oblast kvantového strojového učení zkoumá, jak navrhnout a implementovat kvantový software, který umožní zrychlit strojové učení oproti klasickým počítačům.

Sada Quantum Development Kit obsahuje [knihovnu pro kvantové strojové učení](xref:microsoft.quantum.machine-learning.concepts.intro), které umožňuje spouštění hybridních experimentů kvantového/klasického strojového učení. Knihovna obsahuje ukázky a kurzy a poskytuje nezbytné nástroje pro implementaci nového hybridního kvantově-klasického algoritmu – klasifikátoru obvodů, který umožňuje řešit úlohy dozorované klasifikace.

## <a name="q-and-the-microsoft-quantum-development-kit-qdk"></a>Q# a sada Microsoft Quantum Development Kit (QDK)

Q# je opensourcový programovací jazyk od Microsoftu pro vývoj a spouštění kvantových algoritmů. Je součástí [QDK](https://docs.microsoft.com/quantum/), plnohodnotné vývojové sady v jazyce Q#, kterou můžete používat se standardními nástroji a jazyky pro vývoj kvantových aplikací, které můžete spouštět v různých prostředích, včetně integrovaného plnostavového kvantového simulátoru.

Existují rozšíření pro Visual Studio a VS Code a balíčky pro použití v prostředích Python a Jupyter Notebook.

QDK nabízí standardní knihovnu a dále specializované knihovny pro chemii, strojové učení a numerické výpočty.

Dokumentace obsahuje průvodce jazykem Q#, kurzy a ukázkové programy pro rychlý začátek práce, stejně jako bohaté články, které vás seznámí s hlubšími koncepty kvantových výpočtů.  

## <a name="microsoft-quantum-hardware-partners"></a>Partneři společnosti Microsoft v oblasti kvantového hardwaru

Microsoft spolupracuje se společnostmi vyvíjejícími kvantový hardware, aby zajistil vývojářům cloudový přístup k hardwaru. Díky platformě [Azure Quantum](https://azure.microsoft.com/services/quantum/) a jazyku Q# budou vývojáři moci zkoumat kvantové algoritmy a spouštět své kvantové programy na nejrůznějších typech kvantového hardwaru.

[IonQ](https://ionq.com/news/november-4-2019-microsoft-partnership) a [Honeywell](https://www.honeywell.com/en-us/newsroom/news/2019/11/the-future-of-quantum-computing) používají procesor na bázi **iontových pastí**, v kterých jsou jednotlivé ionty zachycené v elektromagnetickém poli, zatímco [QCI](https://quantumcircuits.com/news-and-publications/quantum-circuits-partners-with-microsoft-on-azure-quantum) pracuje se supravodivými okruhy.

## <a name="next-steps"></a>Další kroky

[Klíčové koncepty kvantových výpočtů](xref:microsoft.quantum.overview.understanding)
[Rychlý start](xref:microsoft.quantum.welcome)