---
title: Použití knihovny numerických knihoven | Microsoft Docs
description: Použití knihovny numerických knihoven
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: ca24ff60cd9ae5077c7f4bae0012fe1180d7e6d4
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821027"
---
# <a name="using-the-numerics-library"></a><span data-ttu-id="3eca1-103">Použití knihovny numerických knihoven</span><span class="sxs-lookup"><span data-stu-id="3eca1-103">Using the Numerics library</span></span>

## <a name="overview"></a><span data-ttu-id="3eca1-104">Přehled</span><span class="sxs-lookup"><span data-stu-id="3eca1-104">Overview</span></span>

<span data-ttu-id="3eca1-105">Knihovna numerických typů se skládá ze tří součástí</span><span class="sxs-lookup"><span data-stu-id="3eca1-105">The Numerics library consists of three components</span></span>

1. <span data-ttu-id="3eca1-106">**Základní celočíselná aritmetická operace** s přidanými celočíselnými a komparátorů</span><span class="sxs-lookup"><span data-stu-id="3eca1-106">**Basic integer arithmetic** with integer adders and comparators</span></span>
1. <span data-ttu-id="3eca1-107">**Celočíselná funkce vysoké úrovně** , která je postavená na základních funkcích. zahrnuje násobení, dělení, inverze atd.  pro podepsaná a nepodepsaná celá čísla.</span><span class="sxs-lookup"><span data-stu-id="3eca1-107">**High-level integer functionality** that is built on top of the basic  functionality; it includes multiplication, division, inversion, etc.  for signed and unsigned integers.</span></span>
1. <span data-ttu-id="3eca1-108">**Aritmetické funkce s pevnou desetinnou** čárkou s inicializací s pevnou desetinnou čárkou, sčítání, násobení, recipročního, polynomických vyhodnocení a měření.</span><span class="sxs-lookup"><span data-stu-id="3eca1-108">**Fixed-point arithmetic functionality** with fixed-point initialization,  addition, multiplication, reciprocal, polynomial evaluation, and measurement.</span></span>

<span data-ttu-id="3eca1-109">Všechny tyto součásti jsou k dispozici pomocí jednoho příkazu `open`:</span><span class="sxs-lookup"><span data-stu-id="3eca1-109">All of these components can be accessed using a single `open` statement:</span></span>
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a><span data-ttu-id="3eca1-110">Typy</span><span class="sxs-lookup"><span data-stu-id="3eca1-110">Types</span></span>

<span data-ttu-id="3eca1-111">Knihovna numerických hodnot podporuje následující typy.</span><span class="sxs-lookup"><span data-stu-id="3eca1-111">The numerics library supports the following types</span></span>

1. <span data-ttu-id="3eca1-112">**`LittleEndian`** : `qArr : Qubit[]` pole qubit, které představuje celé číslo, kde `qArr[0]` označuje nejméně významný bit.</span><span class="sxs-lookup"><span data-stu-id="3eca1-112">**`LittleEndian`**: A qubit array `qArr : Qubit[]` that represents an integer where `qArr[0]` denotes the least significant bit.</span></span>
1. <span data-ttu-id="3eca1-113">**`SignedLittleEndian`** : totéž jako `LittleEndian` s tím rozdílem, že představuje celé číslo se znaménkem uložené ve dvou doplňkech.</span><span class="sxs-lookup"><span data-stu-id="3eca1-113">**`SignedLittleEndian`**: Same as `LittleEndian` except that it represents a signed integer stored in two's complement.</span></span>
1. <span data-ttu-id="3eca1-114">**`FixedPoint`** : představuje reálné číslo sestávající z `qArr2 : Qubit[]` pole qubit a umístění binárního bodu `pos`, které počítá počet binárních číslic nalevo od binárního bodu.</span><span class="sxs-lookup"><span data-stu-id="3eca1-114">**`FixedPoint`**: Represents a real number consisting of a qubit array `qArr2 : Qubit[]` and a binary point position `pos`, which counts the number of binary digits to the left of the binary point.</span></span> <span data-ttu-id="3eca1-115">`qArr2` je uložen stejným způsobem jako `SignedLittleEndian`.</span><span class="sxs-lookup"><span data-stu-id="3eca1-115">`qArr2` is stored in the same way as `SignedLittleEndian`.</span></span>

## <a name="operations"></a><span data-ttu-id="3eca1-116">Operations</span><span class="sxs-lookup"><span data-stu-id="3eca1-116">Operations</span></span>

<span data-ttu-id="3eca1-117">Pro každý ze tří typů uvedených výše je k dispozici celá řada operací:</span><span class="sxs-lookup"><span data-stu-id="3eca1-117">For each of the three types above, a variety of operations is available:</span></span>

1. **`LittleEndian`**
    - <span data-ttu-id="3eca1-118">Sčítání</span><span class="sxs-lookup"><span data-stu-id="3eca1-118">Addition</span></span>
    - <span data-ttu-id="3eca1-119">Porovnání</span><span class="sxs-lookup"><span data-stu-id="3eca1-119">Comparison</span></span>
    - <span data-ttu-id="3eca1-120">Násobení</span><span class="sxs-lookup"><span data-stu-id="3eca1-120">Multiplication</span></span>
    - <span data-ttu-id="3eca1-121">Umocnění</span><span class="sxs-lookup"><span data-stu-id="3eca1-121">Squaring</span></span>
    - <span data-ttu-id="3eca1-122">Dělení (se zbytkem)</span><span class="sxs-lookup"><span data-stu-id="3eca1-122">Division (with remainder)</span></span>

1. **`SignedLittleEndian`**
    - <span data-ttu-id="3eca1-123">Sčítání</span><span class="sxs-lookup"><span data-stu-id="3eca1-123">Addition</span></span>
    - <span data-ttu-id="3eca1-124">Porovnání</span><span class="sxs-lookup"><span data-stu-id="3eca1-124">Comparison</span></span>
    - <span data-ttu-id="3eca1-125">Doplněk modulo 2 pro inverze</span><span class="sxs-lookup"><span data-stu-id="3eca1-125">Inversion modulo 2's complement</span></span>
    - <span data-ttu-id="3eca1-126">Násobení</span><span class="sxs-lookup"><span data-stu-id="3eca1-126">Multiplication</span></span>
    - <span data-ttu-id="3eca1-127">Umocnění</span><span class="sxs-lookup"><span data-stu-id="3eca1-127">Squaring</span></span>

1. **`FixedPoint`**
    - <span data-ttu-id="3eca1-128">Příprava/inicializace na klasické hodnoty</span><span class="sxs-lookup"><span data-stu-id="3eca1-128">Preparation / initialization to a classical values</span></span>
    - <span data-ttu-id="3eca1-129">Sčítání (klasická konstanta nebo jiná pevná desetinná čárka)</span><span class="sxs-lookup"><span data-stu-id="3eca1-129">Addition (classical constant or other quantum fixed-point)</span></span>
    - <span data-ttu-id="3eca1-130">Porovnání</span><span class="sxs-lookup"><span data-stu-id="3eca1-130">Comparison</span></span>
    - <span data-ttu-id="3eca1-131">Násobení</span><span class="sxs-lookup"><span data-stu-id="3eca1-131">Multiplication</span></span>
    - <span data-ttu-id="3eca1-132">Umocnění</span><span class="sxs-lookup"><span data-stu-id="3eca1-132">Squaring</span></span>
    - <span data-ttu-id="3eca1-133">Polynomické hodnocení pomocí specializace pro sudé a liché funkce</span><span class="sxs-lookup"><span data-stu-id="3eca1-133">Polynomial evaluation with specialization for even and odd functions</span></span>
    - <span data-ttu-id="3eca1-134">Oboustranný (1/x)</span><span class="sxs-lookup"><span data-stu-id="3eca1-134">Reciprocal (1/x)</span></span>
    - <span data-ttu-id="3eca1-135">Měření (klasická dvojitá přesnost)</span><span class="sxs-lookup"><span data-stu-id="3eca1-135">Measurement (classical Double)</span></span>

<span data-ttu-id="3eca1-136">Další informace a podrobnou dokumentaci ke každé z těchto operací najdete v tématu Referenční dokumentace knihovny Q # na adrese [docs.Microsoft.com](https://docs.microsoft.com/quantum) .</span><span class="sxs-lookup"><span data-stu-id="3eca1-136">For more information and detailed documentation for each of these operations, see the Q# library reference docs at [docs.microsoft.com](https://docs.microsoft.com/quantum)</span></span>

## <a name="sample-integer-addition"></a><span data-ttu-id="3eca1-137">Ukázka: sčítání celých čísel</span><span class="sxs-lookup"><span data-stu-id="3eca1-137">Sample: Integer addition</span></span>

<span data-ttu-id="3eca1-138">Jako základní příklad zvažte operaci $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $ to znamená, že operace, která přebírá n-qubit Integer $x $ a n-nebo (n + 1)-qubit zaregistrovat $y $ jako vstup, přičemž ten, který se mapuje na součet $ (x + y) $.</span><span class="sxs-lookup"><span data-stu-id="3eca1-138">As a basic example, consider the operation $$ \ket x\ket y\mapsto \ket x\ket{x+y} $$ that is, an operation that takes an n-qubit integer $x$ and an n- or (n+1)-qubit register $y$ as input, the latter of which it maps to the sum $(x+y)$.</span></span> <span data-ttu-id="3eca1-139">Všimněte si, že součet je vypočítán modulo $2 ^ n $, pokud je $y $ Uloženo v registru $n $-bit.</span><span class="sxs-lookup"><span data-stu-id="3eca1-139">Note that the sum is computed modulo $2^n$ if $y$ is stored in an $n$-bit register.</span></span>

<span data-ttu-id="3eca1-140">Pomocí vývojové sady pro práci s více operačními systémem můžete tuto operaci použít takto:</span><span class="sxs-lookup"><span data-stu-id="3eca1-140">Using the Quantum Development Kit, this operation can be applied as follows:</span></span>
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        x = LittleEndian(xQubits); // define bit order
        y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a><span data-ttu-id="3eca1-141">Ukázka: vyhodnocení hladkých funkcí</span><span class="sxs-lookup"><span data-stu-id="3eca1-141">Sample: Evaluating smooth functions</span></span>

<span data-ttu-id="3eca1-142">Aby bylo možné vyhodnotit plynulé funkce, jako je $ \sin (x) $, na počítači s procesorem, kde $x $ je `FixedPoint` `Evaluate[Even/Odd]PolynomialFxP``EvaluatePolynomialFxP` číslo?</span><span class="sxs-lookup"><span data-stu-id="3eca1-142">To evaluate smooth functions such as $\sin(x)$ on a quantum computer, where $x$ is a quantum `FixedPoint` number, the Quantum Development Kit numerics library provides the operations `EvaluatePolynomialFxP` and `Evaluate[Even/Odd]PolynomialFxP`.</span></span>

<span data-ttu-id="3eca1-143">První `EvaluatePolynomialFxP`umožňuje vyhodnotit polynomu ve tvaru $ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d, $ $, kde $d $ označuje *stupeň*.</span><span class="sxs-lookup"><span data-stu-id="3eca1-143">The first, `EvaluatePolynomialFxP`, allows to evaluate a polynomial of the form $$ P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_dx^d, $$ where $d$ denotes the *degree*.</span></span> <span data-ttu-id="3eca1-144">To provedete tak, že všechno, co je potřeba, jsou polynomické koeficienty `[a_0,..., a_d]` (typu `Double[]`), vstupní `x : FixedPoint` a výstupní `y : FixedPoint` (zpočátku nula):</span><span class="sxs-lookup"><span data-stu-id="3eca1-144">To do so, all that is needed are the polynomial coefficients `[a_0,..., a_d]` (of type `Double[]`), the input `x : FixedPoint` and the output `y : FixedPoint` (initially zero):</span></span>
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="3eca1-145">Výsledek, $P (x) = 1 + 2x $, bude uložen v `yFxP`.</span><span class="sxs-lookup"><span data-stu-id="3eca1-145">The result, $P(x)=1+2x$, will be stored in `yFxP`.</span></span>

<span data-ttu-id="3eca1-146">Druhý, `EvaluateEvenPolynomialFxP`a třetí `EvaluateOddPolynomialFxP`, jsou specializace pro případy, které jsou i pro jiné funkce, v uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="3eca1-146">The second, `EvaluateEvenPolynomialFxP`, and the third, `EvaluateOddPolynomialFxP`, are specializations for the cases of even and odd functions, respectively.</span></span> <span data-ttu-id="3eca1-147">To znamená, že pro sudé/liché funkce $f (x) $ a $ $ P_ {sudý} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2D}, $ $ $f (x) $ je přibližná, že $P _ {sudý} (x) $ nebo $P _ {lichý} (x): = x\cdot P_ {sudý} (x) $, v uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="3eca1-147">That is, for an even/odd function $f(x)$ and $$ P_{even}(x)=a_0 + a_1 x^2 + a_2 x^4 + \cdots + a_d x^{2d}, $$ $f(x)$ is approximated well by $P_{even}(x)$ or $P_{odd}(x) := x\cdot P_{even}(x)$, respectively.</span></span>
<span data-ttu-id="3eca1-148">V Q # lze tyto dva případy zpracovat následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="3eca1-148">In Q#, these two cases can be handled as follows:</span></span>
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="3eca1-149">který vyhodnocuje $P _ {sudý} (x) = 1 + 2x ^ 2 $ a</span><span class="sxs-lookup"><span data-stu-id="3eca1-149">which evaluates $P_{even}(x) = 1 + 2x^2$, and</span></span>
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="3eca1-150">který vyhodnocuje $P _ {liché} (x) = x + 2x ^ 3 $.</span><span class="sxs-lookup"><span data-stu-id="3eca1-150">which evaluates $P_{odd}(x) = x + 2x^3$.</span></span>

## <a name="more-samples"></a><span data-ttu-id="3eca1-151">Další ukázky</span><span class="sxs-lookup"><span data-stu-id="3eca1-151">More samples</span></span>

<span data-ttu-id="3eca1-152">Další ukázky najdete v části [hlavní úložiště ukázek](https://github.com/Microsoft/Quantum).</span><span class="sxs-lookup"><span data-stu-id="3eca1-152">You can find more samples in the [main samples repository](https://github.com/Microsoft/Quantum).</span></span>

<span data-ttu-id="3eca1-153">Začněte tím, že naklonujte úložiště a otevřete podsložku `Numerics`:</span><span class="sxs-lookup"><span data-stu-id="3eca1-153">To get started, clone the repo and open the `Numerics` subfolder:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

<span data-ttu-id="3eca1-154">Pak `cd` do jedné z ukázkových složek a spusťte ukázku prostřednictvím</span><span class="sxs-lookup"><span data-stu-id="3eca1-154">Then, `cd` into one of the sample folders and run the sample via</span></span>

```bash
dotnet run
```
