---
title: Úvod do kvantové numerické knihovny | Microsoft Docs
description: Úvod do kvantové numerické knihovny
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
ms.openlocfilehash: efd1a712616534ac281433fc008f0983271881d7
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/13/2020
ms.locfileid: "73442442"
---
# <a name="introduction-to-the-quantum-numerics-library"></a><span data-ttu-id="4506e-103">Úvod do kvantové numerické knihovny</span><span class="sxs-lookup"><span data-stu-id="4506e-103">Introduction to the Quantum Numerics Library</span></span>

<span data-ttu-id="4506e-104">Mnoho kvantových algoritmů je založeno na [orákulu](xref:microsoft.quantum.concepts.oracles), které vyhodnocuje matematické funkce v superpozici vstupů.</span><span class="sxs-lookup"><span data-stu-id="4506e-104">Many quantum algorithms rely on [oracles](xref:microsoft.quantum.concepts.oracles) that evaluate mathematical functions on a superposition of inputs.</span></span>
<span data-ttu-id="4506e-105">Například hlavní součást Shorova algoritmu vyhodnocuje $f(x) = a^x\název_operátoru{mod} N$ pro pevné $a$, faktorizované číslo $N$ a $x$ $2n$qubitové celé číslo v jednotné superpozici nad všemi $2n$bitovými řetězci.</span><span class="sxs-lookup"><span data-stu-id="4506e-105">The main component of Shor's algorithm, for example, evaluates $f(x) = a^x\operatorname{mod} N$ for a fixed $a$, the number to factor $N$, and $x$ a $2n$-qubit integer in a uniform superposition over all $2n$-bit strings.</span></span>

<span data-ttu-id="4506e-106">Aby bylo možné spustit Shorův algoritmus na skutečném kvantovém počítači, musí být tato funkce zapsána v rámci nativních operací cílového počítače.</span><span class="sxs-lookup"><span data-stu-id="4506e-106">To run Shor's algorithm on an actual quantum computer, this function has to be written in terms of the native operations of the target machine.</span></span>
<span data-ttu-id="4506e-107">Pomocí binární reprezentace $x$ s $x_i$ označující $i$tý bit počítaný od nejméně významného bitu lze $f(x)$ zapsat jako $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \název_operátoru{mod} N$.</span><span class="sxs-lookup"><span data-stu-id="4506e-107">Using the binary representation of $x$ with $x_i$ denoting the $i$-th bit counting from the least-significant bit, $f(x)$ can be written as $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.</span></span>
<span data-ttu-id="4506e-108">Toto lze potom zapsat jako součin (mod N) $a^{2^i x_i}=(a^{2^i})^{x_i}$.</span><span class="sxs-lookup"><span data-stu-id="4506e-108">In turn, this can be written as a product (mod N) of terms $a^{2^i x_i}=(a^{2^i})^{x_i}$.</span></span> <span data-ttu-id="4506e-109">Funkci $f(x)$ lze proto implementovat pomocí sekvence $2n$ (modulárního) vynásobení $a^{2^i}$ za podmínky, že $x_i$ není nula.</span><span class="sxs-lookup"><span data-stu-id="4506e-109">The function $f(x)$ can thus be implemented using a sequence of $2n$ (modular) multiplications by $a^{2^i}$ conditional on $x_i$ being nonzero.</span></span> <span data-ttu-id="4506e-110">Konstanty $a^{2^i}$ lze před spuštěním algoritmu předem vypočítat a zmenšit o modulo N.</span><span class="sxs-lookup"><span data-stu-id="4506e-110">The constants $a^{2^i}$ can be precomputed and reduced modulo N before running the algorithm.</span></span>

<span data-ttu-id="4506e-111">Tuto posloupnost řízených modulárních násobení lze dále zjednodušit: Každé násobení lze provést pomocí sekvence $n$ řízených modulárních sčítání a každé modulární sčítání lze vytvořit z obyčejného sčítání a komparátoru.</span><span class="sxs-lookup"><span data-stu-id="4506e-111">This sequence of controlled modular multiplications can be simplified further: Each multiplication can be performed using a sequence of $n$ controlled modular additions; and each modular addition can be built from a regular addition and a comparator.</span></span>


<span data-ttu-id="4506e-112">Vzhledem k tomu, že k dosažení skutečné implementace je potřeba provést tak velký počet kroků, by bylo velmi užitečné mít tuto funkci k dispozici od začátku.</span><span class="sxs-lookup"><span data-stu-id="4506e-112">Given that so many steps are necessary to arrive at an actual implementation, it would be extremely helpful to have such functionality available from the start.</span></span>
<span data-ttu-id="4506e-113">A proto sada Quantum Development Kit poskytuje podporu pro širokou řadu numerických funkcí.</span><span class="sxs-lookup"><span data-stu-id="4506e-113">This is why the Quantum Development Kit provides support for a wide range of numerics functionality.</span></span>


## <a name="functionality"></a><span data-ttu-id="4506e-114">Funkce</span><span class="sxs-lookup"><span data-stu-id="4506e-114">Functionality</span></span>

<span data-ttu-id="4506e-115">Kromě zatím zmíněné celočíselné aritmetiky poskytuje numerická knihovna také</span><span class="sxs-lookup"><span data-stu-id="4506e-115">Besides the integer arithmetic mentioned thus far, the numerics library provides</span></span>

 - <span data-ttu-id="4506e-116">Funkce celého čísla se znaménkem (bez znaménka) (násobení, druhá mocnina, dělení se zbytkem, inverze) s jedním nebo dvěma kvantovými celými čísly jako vstupem</span><span class="sxs-lookup"><span data-stu-id="4506e-116">(Un)signed integer functionality (multiply, square, division with remainder, inversion, ...) with one or two quantum integer numbers as input</span></span>
 - <span data-ttu-id="4506e-117">Funkce s pevnou desetinnou čárkou (sčítání, odečítání, násobení, druhá mocnina, 1/x, vyhodnocení polynomů) s jedním nebo dvěma kvantovými čísly s pevnou desetinnou čárkou jako vstupem</span><span class="sxs-lookup"><span data-stu-id="4506e-117">Fixed-point functionality (add / subtract, multiply, square, 1/x, polynomial evaluation) with one or two quantum fixed-point numbers as input</span></span>

## <a name="getting-started"></a><span data-ttu-id="4506e-118">Začínáme</span><span class="sxs-lookup"><span data-stu-id="4506e-118">Getting started</span></span>

<span data-ttu-id="4506e-119">Pokud chcete začít pracovat s numerickou knihovnou, přečtěte si [průvodce instalací](xref:microsoft.quantum.numerics.installation) a další informace týkající se [používání numerické knihovny](xref:microsoft.quantum.numerics.usage).</span><span class="sxs-lookup"><span data-stu-id="4506e-119">To get started with the Numerics Library, check out the [installation guide](xref:microsoft.quantum.numerics.installation) and more information on [using the Numerics Library](xref:microsoft.quantum.numerics.usage).</span></span>
