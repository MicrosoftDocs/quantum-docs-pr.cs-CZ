---
title: Co jsou Q# a QDK?
description: Seznamte se s programovacím jazykem Q#, který Microsoft vytvořil pro vývoj aplikací pro kvantové počítače, a s klíčovými komponentami sady Quantum Development Kit od Microsoftu.
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: a4bf21887e34ac85f75e5e0b9a033138464fd09d
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906997"
---
# <a name="what-are-q-and-the-qdk"></a>Co jsou Q# a QDK?

Q # je programovací jazyk s funkcemi navrženými speciálně pro kvantové výpočty.
Jazyk Q# je klíčovou komponentou sady Quantum Development Kit (QDK) od Microsoftu a poskytuje kvantovým programátorům architekturu, která jim umožňuje zaměřit se na algoritmy, aniž by se museli starat o technické podrobnosti, jako je optimalizace posloupnosti hradel nebo fyzická implementace kvantového počítače.

Sada QDK se skládá z celé řady nástrojů, které vývojářům poskytují všechno, co potřebují k tomu, aby začali psát kvantové programy.
QDK kromě jazyka Q# zahrnuje tyto komponenty:
* *Knihovny Q#* , které vývojářům umožňují úspěšně vytvářet kvantové aplikace z reálného prostředí už dnes.
* Různé *cílové počítače*, na kterých se dají spouštět programy v Q#. Patří mezi ně estimátory prostředků a simulátory pro rozsáhlejší kvantové programy, a také kvantový simulátor celkového stavu, který se chová jako bezšumový kvantový počítač. Tento simulátor je velice užitečný pro pohrávání si s nápady, ladění programů a seznámení s kvantovou fyzikou, ale je efektivní jenom pro programy s relativně malým počtem qubitů. Velice se těšíme, až v budoucnu jako cílové počítače zpřístupníme specializovaný hardware pro kvantové výpočty.
* *Nástroje* pro maximální usnadnění práce s Q#, jako jsou rozšíření pro Visual Studio a VS Code a balíčky určené pro použití s Pythonem a aplikacemi Jupyter Notebook.
* *Dokumentace k rozhraní API* pro spárování Q# s klasickými hostitelskými jazyka, jako je Python a C#.

Aplikace vyvinuté pomocí sady Microsoft Quantum Development Kit se obvykle skládají ze dvou částí:
1. Jeden nebo několik kvantových algoritmů, které jsou implementované v kvantovém programovacím jazyce Q# a vyvolávané klasickým hostitelským programem. Skládají se z 
    - operací Q# (subrutin obsahujících kvantové operace) a 
    - funkcí Q# (klasických subrutin využívaných v rámci kvantového algoritmu).
2. Klasický program implementovaný v klasickém programovacím jazyce jako Python nebo C#, který slouží jako hlavní vstupní bod a když chce spustit kvantový algoritmus, vyvolá operace Q#.

## <a name="write-quantum-programs-not-quantum-circuits"></a>Pište kvantové programy, a ne kvantové obvody

V počátcích kvantových výpočtů se algoritmy vizualizovaly ve formě schémat, podobně jako u schémat obvodů v klasických výpočtech.
I když byl při výzkumu kvantových výpočtů řadu let užitečný model obvodů, domníváme se v Microsoftu, že vývojáři můžou jít ještě dál, než jim umožňují kvantové obvody, a vyvíjet kvantové algoritmy a aplikace s použitím jazyka Q#.
Jazyk Q# byl vytvořen tak, aby využíval znalosti získané desetiletími vývoje klasického softwaru a umožňoval kvantovým vývojářům pracovat s funkcemi jazyka vysoké úrovně cílenými na kvantové výpočty.

## <a name="how-does-q-work"></a>Jak jazyk Q# funguje?

Programovací jazyk Q# přináší intuitivní sadu typů, operací a logických výrazů pro vývoj algoritmů, aniž byste se museli starat o interní logiku kvantového počítače.

Jedním ze základních stavebních bloků jazyka Q# je typ `Qubit`, který není možné zkopírovat ani k němu přistupovat přímo – stejně jako u skutečného qubitu.
Místo toho ho můžeme změřit a uložit výsledek měření do proměnné `Result`, což je typ v jazyku Q#, který může mít dvě hodnoty: `Zero` a `One`.
Konstrukty jako tento zaručují, že algoritmy vždy respektují zákony o kvantové fyziky a na kvantových počítačích nebo simulátorech můžou běžet správně.

Jazyk Q# obsahuje i klasické funkce logiky, jako jsou podmíněné výrazy nebo cykly s drobnými odlišnostmi, díky nimž je zajištěno dodržování všech kvantových pravidel.
Například omezení způsobu spouštění smyček, aby se zajistilo, že kvantové operace se nevolají uvnitř funkcí, které mohou obsahovat jenom deterministické klasické subrutiny.

Programy v jazyku Q# jsou často sdružené s hostitelským programem napsaným v C# nebo Pythonu. Tím je umožněno pohodlné uspořádání klasického a kvantového kódu.
Kromě podpory jazyků, jako je C# a Python, poskytuje sada QDK podporu pro Jupyter Notebook díky použití jádra IQ# Jupyter.

## <a name="what-can-i-use-q-for"></a>K čemu se dá Q# využít?

### <a name="use-q-to-learn-quantum-computing"></a>Používání jazyka Q# při studiu kvantových výpočtů

Až dosud jste ke studiu kvantových výpočtů potřebovali seznámit se s modelem okruhů, abyste porozuměli algoritmům v podobě řazených posloupností kvantových hradel a měření. V jazyku Q# se můžete vydat jinou cestou: naučit se provádět kvantové výpočty psaním kvantových programů.

### <a name="use-q-to-design-quantum-algorithms"></a>Použití Q# k návrhu kvantových algoritmů

Jazyk Q# nabízí neustále rostoucí množství knihoven a uživatelsky definovaných typů, které vám pomůžou implementovat nástroje a sestavovat pokročilé kvantové algoritmy. Potřebujete například provázat dva qubity q1 a q2? Místo jednotlivé aplikace potřebných hradel s cílem provázat qubity můžete použít již vestavěnou operaci `PrepareEntangledState([q1], [q2])`.

### <a name="use-q-to-estimate-quantum-resources"></a>Použití Q# k odhadu kvantových prostředků

Provedení vašeho programu v Q# můžete simulovat pomocí kvantového simulátoru celkového stavu, který je součástí sady Quantum Development Kit (QDK).  Sada QDK také poskytuje estimátory prostředků, které vám poskytnou představu o výkonu programů v Q#, které jsou pro spuštění v simulátoru příliš velké.  To je velmi cenné pro návrháře algoritmů, protože můžou vyladit své programy, aby využívali méně prostředků (např. menší počet qubitů spuštěných s menším počtem operací), a bylo je tak možné dřív spouštět na kvantovém hardwaru v menším měřítku.

### <a name="use-q-to-validate-hardware-performance"></a>Použití Q# k ověření výkonu hardwaru

Výhodou jazyka Q# je, že program stačí napsat jednou a spouštět na kvantových simulátorech kvůli ladění, a pak je spouštět na různém hardwaru kvantových počítačů.  V jazyce Q# jde napsat programy srovnávacích testů, aby se ověřil výkon hardwaru a porovnaly výsledky, jak se kvantové počítače vyvíjejí a stávají se dostupné nové kvantové počítače.  

## <a name="next-steps"></a>Další kroky

* [Jak se o kvantových výpočtech dozvím víc?](xref:microsoft.quantum.overview.learn)
* [Začínáme se sadou Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
