---
title: Co je Q#?
description: Seznamte se s programovacím jazykem Q#, který byl vytvořen Microsoftem pro vývoj aplikací pro kvantové počítače.
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: e04228ff62092a15c529297bd56b9ee48399f4a5
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443949"
---
# <a name="what-is-q"></a>Co je Q#?

Q# je programovací jazyk se speciálními funkcemi pro kvantové výpočty. Jazyk Q# poskytuje kvantovým programátorům architekturu, která jim umožňuje zaměřit se na algoritmy, aniž by se museli starat o technické podrobnosti, jako je optimalizace posloupnosti hradel nebo fyzická implementace kvantového počítače.

Programovací jazyk Q# přináší intuitivní sadu typů, operací a logických výrazů pro vývoj algoritmů, aniž byste se museli starat o interní logiku kvantového počítače.

## <a name="code-algorithms"></a>Programování algoritmů

V počátcích kvantových výpočtů se algoritmy vizualizovaly ve formě schémat, podobně jako u schémat obvodů v klasických výpočtech.  I když byl při výzkumu kvantových výpočtů řadu let velmi užitečný model okruhů, domníváme se v Microsoftu, že vývojáři můžou jít ještě dál, než jim umožňují kvantové okruhy, a vyvíjet kvantové algoritmy a aplikace s použitím jazyka Q#. Jazyk Q# byl vytvořen tak, aby využíval znalosti získané desetiletími vývoje klasického softwaru a umožňoval kvantovým vývojářům pracovat s funkcemi jazyka vysoké úrovně cílenými konkrétně na kvantové výpočty.


## <a name="how-does-q-work"></a>Jak jazyk Q# funguje?

Jedním ze základních stavebních bloků jazyka Q# je typ `Qubit`, který není možné zkopírovat ani k němu přistupovat přímo – stejně jako u skutečného qubitu. Místo toho ho můžeme změřit a uložit výsledek měření do proměnné `Result`, což je typ v jazyku Q#, který může mít dvě hodnoty: `Zero` a `One`. Konstrukty jako tento zaručují, že algoritmy vždy respektují zákony o kvantové fyziky a na kvantových počítačích nebo simulátorech můžou běžet správně.

Jazyk Q# obsahuje i klasické funkce logiky, jako jsou podmíněné výrazy nebo cykly s drobnými odlišnostmi, díky nimž je zajištěno dodržování všech kvantových pravidel. Kvantové operace například musí být vratné. Tím se vynucují určitá omezení způsobu, jakým se provádějí cykly.

Programy v jazyku Q# jsou často sdružené s hostitelským programem napsaným v C# nebo Pythonu. Tím je umožněno pohodlné uspořádání klasického a kvantového kódu. Kromě podpory jazyků .NET, jako je C# a Python, poskytuje sada QDK podporu pro Jupyter Notebook díky použití jádra IQ# Jupyter.

## <a name="use-q-to-learn-quantum-computing"></a>Používání jazyka Q# při studiu kvantových výpočtů

Až dosud jste ke studiu kvantových výpočtů potřebovali seznámit se s modelem okruhů, abyste porozuměli algoritmům v podobě řazených posloupností kvantových hradel a měření. V jazyku Q# se můžete vydat jinou cestou: naučit se provádět kvantové výpočty psaním kvantových programů.

## <a name="use-q-to-design-quantum-algorithms"></a>Použití Q# k návrhu kvantových algoritmů

Jazyk Q# nabízí neustále rostoucí množství knihoven a uživatelsky definovaných typů, které vám pomůžou implementovat nástroje a sestavovat pokročilé kvantové algoritmy. Potřebujete například provázat dva qubity q1 a q2? Místo jednotlivé aplikace potřebných hradel s cílem provázat qubity můžete použít již vestavěnou operaci `PrepareEntangledState([q1], [q2])`.

## <a name="use-q-to-estimate-quantum-resources"></a>Použití Q# k odhadu kvantových prostředků

Provedení vašeho programu v Q# můžete simulovat pomocí kvantového simulátoru celkového stavu, který je součástí sady Quantum Development Kit (QDK).  Sada QDK také poskytuje estimátory prostředků, které vám poskytnou představu o výkonu programů v Q#, které jsou pro spuštění v simulátoru příliš velké.  To je velmi cenné pro návrháře algoritmů, protože můžou vyladit své programy, aby využívali méně prostředků (např. menší počet qubitů spuštěných s menším počtem operací), a bylo je tak možné dřív spouštět na kvantovém hardwaru v menším měřítku.   

## <a name="use-q-to-validate-hardware-performance"></a>Použití Q# k ověření výkonu hardwaru

Výhodou jazyka Q# je, že program stačí napsat jednou a spouštět na kvantových simulátorech kvůli ladění, a pak je spouštět na různém hardwaru kvantových počítačů.  V jazyce Q# jde napsat programy srovnávacích testů, aby se ověřil výkon hardwaru a porovnaly výsledky, jak se kvantové počítače vyvíjejí a stávají se dostupné nové kvantové počítače.  

## <a name="next-steps"></a>Další kroky

* [Jak se můžu naučit provádět kvantové výpočty?](xref:microsoft.quantum.overview.learn)
* [Začínáme se sadou Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
