---
title: Úvod do kvantové numerické knihovny | Microsoft Docs
description: Úvod do kvantové numerické knihovny
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: conceptual
uid: microsoft.quantum.numerics.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 017fd075596e7b5fb7107d3bc5f149b77dc4e504
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854013"
---
# <a name="introduction-to-the-quantum-numerics-library"></a>Úvod do kvantové numerické knihovny

Mnoho kvantových algoritmů je založeno na [orákulu](xref:microsoft.quantum.concepts.oracles), které vyhodnocuje matematické funkce v superpozici vstupů.
Například hlavní součást Shorova algoritmu vyhodnocuje $f(x) = a^x\název_operátoru{mod} N$ pro pevné $a$, faktorizované číslo $N$ a $x$ $2n$qubitové celé číslo v jednotné superpozici nad všemi $2n$bitovými řetězci.

Aby bylo možné spustit Shorův algoritmus na skutečném kvantovém počítači, musí být tato funkce zapsána v rámci nativních operací cílového počítače.
Pomocí binární reprezentace $x$ s $x_i$ označující $i$tý bit počítaný od nejméně významného bitu lze $f(x)$ zapsat jako $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \název_operátoru{mod} N$.
Toto lze potom zapsat jako součin (mod N) $a^{2^i x_i}=(a^{2^i})^{x_i}$. Funkci $f(x)$ lze proto implementovat pomocí sekvence $2n$ (modulárního) vynásobení $a^{2^i}$ za podmínky, že $x_i$ není nula. Konstanty $a^{2^i}$ lze před spuštěním algoritmu předem vypočítat a zmenšit o modulo N.

Tuto posloupnost řízených modulárních násobení lze dále zjednodušit: Každé násobení lze provést pomocí sekvence $n$ řízených modulárních sčítání a každé modulární sčítání lze vytvořit z obyčejného sčítání a komparátoru.


Vzhledem k tomu, že k dosažení skutečné implementace je potřeba provést tak velký počet kroků, by bylo velmi užitečné mít tuto funkci k dispozici od začátku.
A proto sada Quantum Development Kit poskytuje podporu pro širokou řadu numerických funkcí.


## <a name="functionality"></a>Funkce

Kromě zatím zmíněné celočíselné aritmetiky poskytuje numerická knihovna také

- Funkce celého čísla se znaménkem (bez znaménka) (násobení, druhá mocnina, dělení se zbytkem, inverze) s jedním nebo dvěma kvantovými celými čísly jako vstupem
- Funkce s pevnou desetinnou čárkou (sčítání, odečítání, násobení, druhá mocnina, 1/x, vyhodnocení polynomů) s jedním nebo dvěma kvantovými čísly s pevnou desetinnou čárkou jako vstupem

## <a name="getting-started"></a>Začínáme

> [!div class="nextstepaction"]
> [Další informace o použití numerické knihovny](xref:microsoft.quantum.numerics.usage)
