---
title: Co je programovací jazyk Q# a sada QDK?
description: Přečtěte si o sadě Microsoft Quantum Development Kit, programovacím jazyku Q# a o vytváření kvantových programů.
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.q-sharp
ms.openlocfilehash: 55ac946aa935d3748b36ac99096a89d0db686835
ms.sourcegitcommit: a03d79ca3f0774161a9f86a15528d36e1291acce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83433023"
---
# <a name="what-are-the-q-programming-language-and-qdk"></a>Co je programovací jazyk Q# a sada QDK?

Q# je opensourcový programovací jazyk od společnosti Microsoft pro vývoj a spouštění kvantových algoritmů. Je součástí sady Quantum Development Kit (QDK), která zahrnuje [knihovny Q#](xref:microsoft.quantum.libraries), [kvantové simulátory](xref:microsoft.quantum.machines), [rozšíření pro další programovací prostředí](xref:microsoft.quantum.install) a [dokumentaci k rozhraní API](xref:microsoft.quantum.standardlibsintro). Kromě standardní knihovny Q# zahrnuje QDK i knihovny pro chemii, strojové učení a numerické výpočty.

Jako programovací jazyk přebírá Q# známé prvky z Pythonu, C# a F# a podporuje základní procedurální model psaní programů se smyčkami, podmínkami a běžnými datovými typy. Zavádí také nové datové struktury a operace specifické pro kvantové výpočty.

## <a name="what-can-i-do-with-the-qdk"></a>Co mohu s QDK dělat?

QDK je plnohodnotná vývojová sady pro jazyk Q#, kterou můžete používat s běžnými nástroji a jazyky při vývoji kvantových aplikací, které pak můžete spouštět v různých prostředích. Programy Q# lze spouštět jako aplikace příkazového řádku, v prostředí Jupyter Notebook nebo v rámci hostitelského programu v Pythonu nebo .NET.

### <a name="develop-in-common-tools-and-environments"></a>Vývoj ve známých nástrojích a prostředích

Integrujte svůj vývoj kvantových programů do prostředí [Visual Studio, Visual Studio Code](xref:microsoft.quantum.install.standalone) a [Jupyter Notebooks](xref:microsoft.quantum.install.jupyter). Použijte vestavěná rozhraní API ke spárování programů s hostitelskými jazyky [Python](xref:microsoft.quantum.install.python) a [.NET](xref:microsoft.quantum.install.cs).

### <a name="try-quantum-operations-and-domain-specific-libraries"></a>Kvantové operace a knihovny pro konkrétní obory

Napište a vyzkoušejte kvantové algoritmy zkoumající superpozici, provázání a další kvantové operace. Knihovny Q# umožňují spouštění složitých kvantových programů, aniž by bylo třeba navrhovat nízkoúrovňové sekvence operací.

### <a name="run-programs-in-simulators"></a>Spouštění programů v simulátorech

Kvantové programy je možné spouštět na plnostavovém kvantovém simulátoru, simulátoru Toffoli s omezeným rozsahem nebo v různých nástrojích pro odhad prostředků pro jazyk Q#. 

## <a name="where-can-i-learn-more"></a>Kde získám další informace?

|||
| ---- | ---- |
| **Jsem v kvantových výpočtech nováčkem** | Seznamte se se základy kvantové fyziky a kvantových výpočtů v dokumentu [Klíčové koncepty](xref:microsoft.quantum.overview.understanding).|
| **Chci proniknout do jazyka Q# hlouběji** | Seznamte se s typy, výrazy, proměnnými a strukturou kvantového programu v [Uživatelské příručce Q#](xref:microsoft.quantum.guide).|
| **Chci jenom začít psát kvantové programy** | Nastavte si prostředí Q# a začněte psát kvantové programy podle dokumentu [Rychlý start](xref:microsoft.quantum.install).|

## <a name="how-does-q-work"></a>Jak jazyk Q# funguje?

Program Q# je možné kompilovat do samostatné aplikace příkazového řádku nebo volat z hostitelského programu napsaného v Pythonu nebo .NET.

Když zkompilujete a spustíte program, vytvoří instanci kvantového simulátoru a předá mu váš kód Q#. Simulátor podle kódu Q# vytvoří simulované qubity a podle zadaných transformací bude manipulovat s jejich stavy. Výsledky kvantových operací ze simulátoru se pak vrátí do programu.  

Izolování kódu Q# v simulátoru zajišťuje, že algoritmy budou odpovídat zákonům kvantové fyziky a budou správně fungovat i na kvantových počítačích.

![qsharp-code-flow](~/media/qsharp-code-flow.png)

## <a name="how-do-i-use-the-qdk"></a>Jak se sada QDK používá?

Vše, co potřebujete k psaní a spouštění programů v Q#, včetně kompilátoru Q#, knihoven Q# a kvantových simulátorů, můžete nainstalovat a spouštět v místním počítači. Časem budete moci spouštět své programy v Q# vzdáleně na skutečných kvantových počítačích, do té doby mohou poskytovat přesné a spolehlivé výsledky simulátory obsažené v sadě QDK.

- Spouštění [programů Q# z příkazového řádku](xref:microsoft.quantum.install.standalone) je nejrychlejší způsob, jak začít.

- Kompilovat, simulovat a vizualizovat programy v Q# můžete také pomocí rozšíření [Jupyter Notebooks with Q#](xref:microsoft.quantum.install.jupyter).

- Pokud znáte [Python](xref:microsoft.quantum.install.python), můžete ho použít jako hostitelskou platformu pro své první kvantové programy. Python je široce rozšířený nejen mezi vývojáři, ale i mezi vědci, výzkumníky a učiteli.

- Pokud již máte zkušenosti s [C#, F# nebo VB.NET](xref:microsoft.quantum.install.cs) a znáte vývojové prostředí Visual Studio, stačí do něj přidat jen několik rozšíření, abyste v něm mohli Q# používat.  

## <a name="summary"></a>Souhrn

Q# je opensourcový programovací jazyk pro vývoj kvantových programů. Obsahuje knihovny, které umožňují sestavování složitých kvantových operací, a simulátory pro přesné spouštění a testování programů. Programy v Q# je možné spouštět jako samostatné aplikace nebo volat z hostitelského programu v Pythonu nebo .NET a můžete je psát, spouštět a testovat přímo v místním počítači.

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Lineární algebra pro kvantové výpočty](xref:microsoft.quantum.overview.algebra)
