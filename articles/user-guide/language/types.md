---
title: Typy vQ#
description: Seznamte se s různými typy používanými v Q# programovacím jazyce.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
no-loc:
- Q#
- $$v
ms.openlocfilehash: b034af0b1d3b967b5680403341813407e4412f93
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869592"
---
# <a name="types-in-no-locq"></a><span data-ttu-id="e9b6b-103">Typy vQ#</span><span class="sxs-lookup"><span data-stu-id="e9b6b-103">Types in Q#</span></span>

<span data-ttu-id="e9b6b-104">Tento článek popisuje Q# typ modelu a syntaxi pro zadání a práci s typy.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-104">This article describes the Q# type model and the syntax for specifying and working with types.</span></span> <span data-ttu-id="e9b6b-105">Podrobnosti o tom, jak vytvořit a pracovat na výrazech těchto typů, naleznete v tématu [Expression Types](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="e9b6b-105">For details on how to create and operate on expressions of these types, see [Type Expressions](xref:microsoft.quantum.guide.expressions).</span></span>

<span data-ttu-id="e9b6b-106">Upozorňujeme, že Q# se jedná o jazyk se *silnými* typy, který pečlivým použitím těchto typů může přispět k tomu, aby kompilátor poskytoval silné záruky na Q# programy v době kompilace.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="e9b6b-107">Aby bylo možné zajistit nejpřísnější záruky, převody mezi typy v Q# nástroji musí být explicitní pomocí volání funkcí, které tento převod vyjadřují.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-107">To provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> 
<span data-ttu-id="e9b6b-108">Q#poskytuje celou řadu takových funkcí jako součást <xref:microsoft.quantum.convert> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-108">Q# provides a variety of such functions as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="e9b6b-109">Přetypování na kompatibilní typy se na druhé straně provede implicitně.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-109">Upcasts to compatible types, on the other hand, happen implicitly.</span></span> 

<span data-ttu-id="e9b6b-110">Q#poskytuje oba primitivní typy, které se používají přímo, a různé způsoby, jak vytvořit nové typy z jiných typů.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-110">Q# provides both primitive types, which are used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="e9b6b-111">Každý ve zbývající části tohoto článku popisujeme.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-111">We describe each in the rest of this article.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="e9b6b-112">Primitivní typy</span><span class="sxs-lookup"><span data-stu-id="e9b6b-112">Primitive Types</span></span>

<span data-ttu-id="e9b6b-113">Q#Jazyk poskytuje následující *primitivní typy*, které lze použít přímo v Q# programu.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-113">The Q# language provides the following *primitive types*, all of which you can use directly in Q# programs.</span></span> <span data-ttu-id="e9b6b-114">Tyto primitivní typy lze také použít k vytvoření nových typů.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-114">You can also use these primitive types to construct new types.</span></span>

- <span data-ttu-id="e9b6b-115">`Int`Typ představuje 64 celé číslo se znaménkem, například `2` ,, `107` `-5` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-115">The `Int` type represents a 64-bit signed integer, for example, `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="e9b6b-116">`BigInt`Typ představuje celé číslo se znaménkem libovolné velikosti, například,, `2L` `107L` `-5L` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-116">The `BigInt` type represents a signed integer of arbitrary size, for example, `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="e9b6b-117">Tento typ je založený na rozhraní .NET.<xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="e9b6b-117">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="e9b6b-118">textový.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-118">type.</span></span>

- <span data-ttu-id="e9b6b-119">`Double`Typ představuje číslo s plovoucí desetinnou čárkou s dvojitou přesností, například,, `0.0` `-1.3` `4e-7` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-119">The `Double` type represents a double-precision floating-point number, for example, `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="e9b6b-120">`Bool`Typ představuje logickou hodnotu buď `true` nebo `false` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-120">The `Bool` type represents a Boolean value of either `true` or `false`.</span></span>
- <span data-ttu-id="e9b6b-121">`Range`Typ představuje sekvenci celých čísel, označených jako `start..step..stop` , kde označuje, že krok je nepovinný.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-121">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="e9b6b-122">Například `start .. stop` odpovídá `start..1..stop` a `1..2..7` představuje sekvenci $ \{ 1, 3, 5, 7 \} $.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-122">For example, `start .. stop` corresponds to `start..1..stop`, and `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="e9b6b-123">`String`Typ je posloupnost znaků Unicode, která je po vytvoření uživatelem neprůhledná.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-123">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="e9b6b-124">Použijte `string` typ k hlášení zpráv pro klasického hostitele v případě chyby nebo diagnostické události.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-124">Use the `string` type to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="e9b6b-125">`Unit`Typ může mít pouze jednu hodnotu, `()` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-125">The `Unit` type can have only one value, `()`.</span></span> 
  <span data-ttu-id="e9b6b-126">Tento typ použijte k označení, že Q# funkce nebo operace nevrátí žádné informace.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-126">Use this type to indicate that a Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="e9b6b-127">`Qubit`Typ představuje bit s podmnožinou nebo qubit.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-127">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="e9b6b-128">`Qubit`s jsou neprůhlední pro uživatele.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-128">`Qubit`s are opaque to the user.</span></span> <span data-ttu-id="e9b6b-129">Jedinou operací, která je k dispozici, je kromě jejich předání jiné operaci testovat identitu (rovnost).</span><span class="sxs-lookup"><span data-stu-id="e9b6b-129">The only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="e9b6b-130">Nakonec implementujete akce v `Qubit` s voláním vnitřních pokynů na procesor s procesorem (nebo simulátorem pro plnění).</span><span class="sxs-lookup"><span data-stu-id="e9b6b-130">Ultimately, you implement actions on `Qubit`s by calling intrinsic instructions on a quantum processor (or a quantum simulator).</span></span>
- <span data-ttu-id="e9b6b-131">`Pauli`Typ představuje jednu ze čtyř operátorů Pauli s jedním qubit.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-131">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="e9b6b-132">Tento typ použijte k označení základní operace pro otočení a určení pozorovatele, který se má měřit.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-132">Use this type to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="e9b6b-133">Jedná se o Výčtový typ, který má čtyři možné hodnoty: `PauliI` , `PauliX` , `PauliY` a `PauliZ` , což jsou konstanty typu `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-133">It is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="e9b6b-134">`Result`Typ představuje výsledek měření.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-134">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="e9b6b-135">Jedná se o Výčtový typ se dvěma možnými hodnotami: `One` a `Zero` , což jsou konstanty typu `Result` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-135">It is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="e9b6b-136">`Zero`indikuje, že došlo k měření + 1 eigenvalue. `One`indikuje, že byl změřen eigenvalue-1.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-136">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue was measured.</span></span>

<span data-ttu-id="e9b6b-137">Konstanty,,,,,, `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` a `Zero` jsou všechny vyhrazené symboly v Q# .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-137">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="e9b6b-138">Typy polí</span><span class="sxs-lookup"><span data-stu-id="e9b6b-138">Array Types</span></span>

* <span data-ttu-id="e9b6b-139">Pro libovolný platný Q# typ existuje typ, který představuje pole hodnot daného typu.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-139">For any valid Q# type, there is a type that represents an array of values of that type.</span></span>
    <span data-ttu-id="e9b6b-140">Například `Qubit[]` a `(Bool, Pauli)[]` představuje pole `Qubit` hodnot a `(Bool, Pauli)` hodnot řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-140">For example, `Qubit[]` and `(Bool, Pauli)[]` represent arrays of `Qubit` values and `(Bool, Pauli)` tuple values.</span></span>

* <span data-ttu-id="e9b6b-141">Pole polí je také platné.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-141">An array of arrays is also valid.</span></span> <span data-ttu-id="e9b6b-142">Rozbalení v předchozím příkladu, pole `(Bool, Pauli)` polí je označeno `(Bool, Pauli)[][]` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-142">Expanding on the previous example, an array of `(Bool, Pauli)` arrays is denoted `(Bool, Pauli)[][]`.</span></span>

> [!NOTE] 
> <span data-ttu-id="e9b6b-143">V tomto příkladu `(Bool, Pauli)[][]` představuje potenciálně vícenásobné pole polí a ne obdélníkové dvourozměrné pole.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-143">This example, `(Bool, Pauli)[][]`, represents a potentially jagged array of arrays and not a rectangular two-dimensional array.</span></span> <span data-ttu-id="e9b6b-144">Q#nepodporuje obdélníková multidimenzionální pole.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-144">Q# does not support rectangular multi-dimensional arrays.</span></span>

* <span data-ttu-id="e9b6b-145">Hodnota pole může být napsána ve Q# zdrojovém kódu pomocí hranatých závorek kolem prvků pole, jako v `[PauliI, PauliX, PauliY, PauliZ]` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-145">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="e9b6b-146">Běžný základní typ všech položek v poli určuje typ literálu pole.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-146">The common base type of all items in the array determines the type of an array literal.</span></span> <span data-ttu-id="e9b6b-147">Proto Sestavte pole s prvky, které nemají žádný společný základní typ, vyvolá chybu.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-147">Hence, constructing an array with elements that have no common base type raises an error.</span></span>  
<span data-ttu-id="e9b6b-148">Příklad naleznete v tématu [pole volat](xref:microsoft.quantum.guide.expressions#arrays-of-callables).</span><span class="sxs-lookup"><span data-stu-id="e9b6b-148">For an example, see [arrays of callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables).</span></span>

    > [!WARNING]
    > <span data-ttu-id="e9b6b-149">Po vytvoření nelze prvky pole změnit.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-149">Once created, the elements of an array cannot be changed.</span></span>
    > <span data-ttu-id="e9b6b-150">K vytvoření upraveného pole použijte [Příkazy Update-and-Reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) nebo [copy-and-Update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="e9b6b-150">To construct a modified array, use [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span>

* <span data-ttu-id="e9b6b-151">Alternativně lze pole vytvořit z jeho velikosti pomocí `new` klíčového slova:</span><span class="sxs-lookup"><span data-stu-id="e9b6b-151">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* <span data-ttu-id="e9b6b-152">Použijte základní funkci `Length` k získání počtu prvků z pole jako `Int` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-152">Use the core function `Length` to obtain the number of elements from an array as an `Int`.</span></span>
* <span data-ttu-id="e9b6b-153">Pole mohou být zastaralá, aby získala buď jednotlivé prvky, nebo nová pole obsahující podmnožinu prvků pole.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-153">Arrays can be subscripted to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="e9b6b-154">Dolní indexy polí jsou založené na nule a musí být typu `Int` nebo typu `Range` :</span><span class="sxs-lookup"><span data-stu-id="e9b6b-154">The subscripts of arrays are zero-based and must be type `Int` or type `Range`:</span></span>

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a><span data-ttu-id="e9b6b-155">Typy řazené kolekce členů</span><span class="sxs-lookup"><span data-stu-id="e9b6b-155">Tuple Types</span></span>

<span data-ttu-id="e9b6b-156">Řazené kolekce členů jsou účinným konceptem použitým v celém Q# ke shromáždění hodnot dohromady do jedné hodnoty, což usnadňuje jejich předání.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-156">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="e9b6b-157">Zejména pomocí zápisu řazené kolekce členů můžete vyjádřit, že každá operace a možnost volat přebírá přesně jeden vstup a vrátí přesně jeden výstup.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-157">In particular, using tuple notation, you can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

* <span data-ttu-id="e9b6b-158">Předanému nule nebo více různým typům, `T0` `T1` ,..., `Tn` můžete odznačte nový *typ řazené kolekce členů* jako `(T0, T1, ..., Tn)` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-158">Given zero or more different types `T0`, `T1`, ..., `Tn`, you can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="e9b6b-159">Typy použité k vytvoření nového typu řazené kolekce členů mohou být řazené kolekce členů, jako v `(Int, (Qubit, Qubit))` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-159">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="e9b6b-160">Takové vnořování je vždy omezené, ale v případě, že typy řazené kolekce členů nemůžou za žádných okolností obsahovat samy sebe.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-160">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

* <span data-ttu-id="e9b6b-161">Hodnoty nového typu řazené kolekce členů jsou řazené kolekce členů vytvořené pomocí sekvencí hodnot z každého typu v řazené kolekci členů.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-161">The values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="e9b6b-162">Například `(3, false)` je řazená kolekce členů, jejíž typ je typ řazené kolekce členů `(Int, Bool)` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-162">For example, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="e9b6b-163">Je možné vytvořit pole řazených kolekcí členů, řazené kolekce členů polí, řazené kolekce členů a tak dále.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-163">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, and so on.</span></span>

* <span data-ttu-id="e9b6b-164">Od Q# 0,3 `Unit` je název *typu* prázdné řazené kolekce členů, který `()` se používá pro *hodnotu* prázdné řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-164">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the *value* of the empty tuple.</span></span>

* <span data-ttu-id="e9b6b-165">Instance řazené kolekce členů jsou neměnné.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-165">Tuple instances are immutable.</span></span>
<span data-ttu-id="e9b6b-166">Q#neposkytuje mechanismus pro změnu obsahu řazené kolekce členů po vytvoření.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-166">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>



### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="e9b6b-167">Rovnost řazené kolekce členů singleton</span><span class="sxs-lookup"><span data-stu-id="e9b6b-167">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="e9b6b-168">Je možné vytvořit singleton (jeden prvek) řazené kolekce členů `('T1)` , například `(5)` nebo `([1,2,3])` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-168">It is possible to create a singleton (single-element) tuple `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="e9b6b-169">Nicméně Q# zpracovává řazenou kolekci členů jako ekvivalent hodnoty uzavřeného typu.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-169">However, Q# treats a singleton tuple as equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="e9b6b-170">To znamená, že neexistuje žádný rozdíl mezi `5` a `(5)` , ani mezi `5` a `(((5)))` , ani mezi `(5, (6))` a `(5, 6)` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-170">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="e9b6b-171">Je stejně platná pro zápis, `(5)+3` protože je možné zapisovat. `5+3` oba výrazy jsou vyhodnoceny `8` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-171">It is just as valid to write `(5)+3` as it is to write `5+3`; both expressions evaluate to `8`.</span></span>

<span data-ttu-id="e9b6b-172">Tato rovnocennost se vztahuje na všechny účely, včetně přiřazení a výrazů.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-172">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="e9b6b-173">V případě libovolného výrazu je stejný výraz uzavřený v závorkách výraz stejného typu.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-173">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="e9b6b-174">Například `(7)` je výraz typu `Int` , `([1,2,3])` je výraz typu `Int[]` a `((1,2))` je výraz typu `(Int, Int)` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-174">For example, `(7)` is an expression of type `Int`, `([1,2,3])` is an expression of type `Int[]`, and `((1,2))` is an expression of type `(Int, Int)`.</span></span>

<span data-ttu-id="e9b6b-175">Konkrétně to znamená, že můžete zobrazit operaci nebo funkci, jejíž typ řazené kolekce členů nebo výstupní řazené kolekce členů má jedno pole jako přebírání jednoho argumentu nebo vrácení jedné hodnoty.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-175">In particular, this means that you can view an operation or function whose input tuple or output tuple type has one field as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="e9b6b-176">Tato vlastnost odkazuje jako na _rovnost v řazené kolekci členů typu Singleton_.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-176">We refer to this property as _singleton tuple equivalence_.</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="e9b6b-177">Uživatelsky definované typy</span><span class="sxs-lookup"><span data-stu-id="e9b6b-177">User-Defined Types</span></span>

<span data-ttu-id="e9b6b-178">Uživatelsky definovaná deklarace typu se skládá z klíčového slova `newtype` , následované názvem uživatelsky definovaného typu, a `=` platnou specifikací typu a ukončující středník.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-178">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="e9b6b-179">Příklad:</span><span class="sxs-lookup"><span data-stu-id="e9b6b-179">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* <span data-ttu-id="e9b6b-180">Každý Q# zdrojový soubor může deklarovat libovolný počet uživatelsky definovaných typů.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-180">Each Q# source file may declare any number of user-defined types.</span></span>
* <span data-ttu-id="e9b6b-181">Názvy typů musí být v rámci oboru názvů jedinečné a nemusí být v konfliktu s názvy operací a funkcí.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-181">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>
* <span data-ttu-id="e9b6b-182">Uživatelsky definované typy jsou odlišné, i když základní typy jsou identické.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-182">User-defined types are distinct, even if the base types are identical.</span></span>
<span data-ttu-id="e9b6b-183">Konkrétně neexistuje žádný automatický převod mezi hodnotami dvou uživatelsky definovaných typů, a to i v případě, že jsou základní typy identické.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-183">In particular, there is no automatic conversion between the values of two user-defined types, even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="e9b6b-184">Pojmenované vs. anonymní položky</span><span class="sxs-lookup"><span data-stu-id="e9b6b-184">Named vs. anonymous items</span></span>

<span data-ttu-id="e9b6b-185">Q#Soubor může definovat nový pojmenovaný typ obsahující jednu hodnotu jakéhokoli právního typu.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-185">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="e9b6b-186">Pro libovolný typ řazené kolekce členů `T` můžete deklarovat nový uživatelsky definovaný typ, který je podtypem `T` s `newtype` příkazem.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-186">For any tuple type `T`, you can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="e9b6b-187">V @"microsoft.quantum.math" oboru názvů jsou například komplexní čísla definovány jako uživatelsky definovaný typ:</span><span class="sxs-lookup"><span data-stu-id="e9b6b-187">In the @"microsoft.quantum.math" namespace, for example, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="e9b6b-188">Tento příkaz vytvoří nový typ se dvěma anonymními položkami typu `Double` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-188">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="e9b6b-189">Kromě anonymních položek podporuje uživatelsky definované typy také *pojmenované položky* od Q# verze 0,7 nebo vyšší.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-189">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="e9b6b-190">Například můžete pojmenovat položky `Re` pro dvojitou hodnotu představující reálnou část komplexního čísla a `Im` pro imaginární část:</span><span class="sxs-lookup"><span data-stu-id="e9b6b-190">For example, you could name the items to `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="e9b6b-191">Pojmenování jedné položky v uživatelsky definovaném typu neznamená, že všechny položky musí být pojmenovány – podporuje se libovolná kombinace pojmenovaných a nepojmenovaných položek.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-191">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="e9b6b-192">Kromě toho mohou být také pojmenovány vnitřní položky.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-192">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="e9b6b-193">Typ `Nested` , jak je definován níže, má například nadřízený typ `(Double, (Int, String))` , který `Int` je pojmenován pouze položka typu a všechny ostatní položky jsou anonymní.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-193">The type `Nested`, as defined below for example, has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named, and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="e9b6b-194">Pojmenované položky mají výhodu, ke kterým lze přistupovat přímo prostřednictvím *operátoru přístupu* `::` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-194">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="e9b6b-195">Kromě poskytování krátkých aliasů pro potenciálně složité typy řazené kolekce členů, což je významná výhoda definování takových typů, je, že mohou zdokumentovat záměr konkrétní hodnoty.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-195">In addition to providing short aliases for potentially complicated tuple types, a significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="e9b6b-196">Návrat do příkladu `Complex` , jeden mohl také definovat 2D polární souřadnice jako uživatelsky definovaný typ:</span><span class="sxs-lookup"><span data-stu-id="e9b6b-196">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="e9b6b-197">I když oba `Complex` i `Polar` oba mají základní typ `(Double, Double)` , jsou tyto dva typy zcela nekompatibilní v Q# a minimalizují riziko náhodného volání komplexní matematické funkce s polárními souřadnicemi a naopak.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-197">Even though both `Complex` and `Polar` both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="e9b6b-198">Přístup k anonymním položkám pomocí operátoru rozbalení</span><span class="sxs-lookup"><span data-stu-id="e9b6b-198">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="e9b6b-199">Pro přístup k anonymním položkám nejprve extrahuje zabalenou hodnotu pomocí operátoru přípony `!` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-199">To access anonymous items, first extract the wrapped value using the postfix operator `!`.</span></span>
<span data-ttu-id="e9b6b-200">Pomocí operátoru "Unwrap" `!` můžete extrahovat hodnotu obsaženou v uživatelsky definovaném typu.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-200">With the "unwrap" operator, `!`, you can extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="e9b6b-201">Typ takového výrazu "Unwrap" je základní typ uživatelsky definovaného typu.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-201">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="e9b6b-202">Jeden operátor rozbalení rozbalí jednu vrstvu obtékání.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-202">A single unwrap operator unwraps one layer of wrapping.</span></span> <span data-ttu-id="e9b6b-203">Pro přístup k hodnotě zabalené v násobení použijte více operátorů rozbalení.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-203">Use multiple unwrap operators to access a multiply-wrapped value.</span></span>

<span data-ttu-id="e9b6b-204">Příklad:</span><span class="sxs-lookup"><span data-stu-id="e9b6b-204">For example:</span></span>

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

<span data-ttu-id="e9b6b-205">Další informace o operátoru rozbalení naleznete v tématu [výrazy typu v Q# ](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="e9b6b-205">For more details on the unwrap operator, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="e9b6b-206">Vytváření hodnot uživatelsky definovaných typů</span><span class="sxs-lookup"><span data-stu-id="e9b6b-206">Creating values of user-defined types</span></span>

<span data-ttu-id="e9b6b-207">Vytvořte hodnoty uživatelsky definovaného typu voláním odpovídajícího konstruktoru typu:</span><span class="sxs-lookup"><span data-stu-id="e9b6b-207">Create values of a user-defined type by calling the corresponding type constructor:</span></span>

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="e9b6b-208">Alternativně můžete vytvořit nové hodnoty z existujících pomocí [výrazů kopírování a aktualizace](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="e9b6b-208">Alternatively, you can create new values from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="e9b6b-209">Stejně jako u polí, výrazy kopírování a aktualizace kopírují všechny hodnoty položky původního výrazu, s výjimkou zadaných pojmenovaných položek.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-209">Just as they do with arrays, copy-and-update expressions copy all item values of the original expression, except for the specified named items.</span></span> <span data-ttu-id="e9b6b-210">Pro tyto výjimky jsou hodnoty těchto položek hodnotami definované na pravé straně výrazu.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-210">For these exceptions, the values of these items are the values defined on the right-hand side of the expression.</span></span> <span data-ttu-id="e9b6b-211">Jakékoli jiné jazykové konstrukce, které jsou k dispozici pro položky pole, například [Příkazy Update-a-Reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), existují také pro pojmenované položky v uživatelsky definovaných typech.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-211">Any other language constructs that are available for array items, for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), exist for named-items in user-defined types as well.</span></span>

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

* <span data-ttu-id="e9b6b-212">Uživatelsky definované typy lze použít kdekoli, kde používáte jiné typy.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-212">You can use user-defined types anywhere you use any other types.</span></span>
<span data-ttu-id="e9b6b-213">Konkrétně je možné definovat pole uživatelsky definovaného typu a zahrnout uživatelsky definovaný typ jako prvek typu řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-213">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

* <span data-ttu-id="e9b6b-214">Není možné vytvářet struktury rekurzivního typu.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-214">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="e9b6b-215">To znamená, že typ, který definuje uživatelsky definovaný typ, nemůže být typ řazené kolekce členů, který obsahuje prvek uživatelsky definovaného typu.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-215">That is, the type that defines a user-defined type cannot be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="e9b6b-216">Obecně platí, že uživatelsky definované typy nemůžou mít cyklicky závislé závislosti, takže následující sada definic typů je neplatná:</span><span class="sxs-lookup"><span data-stu-id="e9b6b-216">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions are invalid:</span></span>

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a><span data-ttu-id="e9b6b-217">Typy operací a funkcí</span><span class="sxs-lookup"><span data-stu-id="e9b6b-217">Operation and Function Types</span></span>

<span data-ttu-id="e9b6b-218">Zadané typy `'Tinput` a `'Tresult` :</span><span class="sxs-lookup"><span data-stu-id="e9b6b-218">Given the types `'Tinput` and `'Tresult`:</span></span>

* <span data-ttu-id="e9b6b-219">`('Tinput => 'Tresult)`je základní typ pro každou *operaci*, například `((Qubit, Pauli) => Result)` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-219">`('Tinput => 'Tresult)` is the basic type for any *operation*, for example `((Qubit, Pauli) => Result)`.</span></span>
* <span data-ttu-id="e9b6b-220">`('Tinput -> 'Tresult)`je základní typ pro libovolnou *funkci*, například `(Int -> Int)` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-220">`('Tinput -> 'Tresult)` is the basic type for any *function*, for example `(Int -> Int)`.</span></span> 

<span data-ttu-id="e9b6b-221">Nazývají se *signatury* , které lze volat.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-221">These are called the *signature* of the callable.</span></span>

* <span data-ttu-id="e9b6b-222">Všechny Q# volat jako vstup přijímají jednu hodnotu a jako výstup vrátí jedinou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-222">All Q# callables take a single value as input and return a single value as output.</span></span>
* <span data-ttu-id="e9b6b-223">Můžete použít řazené kolekce členů pro vstupní i výstupní hodnoty.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-223">You can use tuples for both the input and output values.</span></span>
* <span data-ttu-id="e9b6b-224">Volat, které nemají žádný výsledek, vrátí `Unit` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-224">Callables that have no result, return `Unit`.</span></span>
* <span data-ttu-id="e9b6b-225">Volat, které nemají žádný vstup, přebírají jako vstup prázdnou řazenou kolekci členů.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-225">Callables that have no input take the empty tuple as input.</span></span>

### <a name="functors"></a><span data-ttu-id="e9b6b-226">Funktory</span><span class="sxs-lookup"><span data-stu-id="e9b6b-226">Functors</span></span>

<span data-ttu-id="e9b6b-227">Typy *funkcí* jsou zcela určeny jejich signaturou.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-227">*Function* types are completely specified by their signature.</span></span> <span data-ttu-id="e9b6b-228">Například funkce, která vypočítá sinus úhlu, by měla typ `(Double -> Double)` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-228">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span> 

<span data-ttu-id="e9b6b-229">*Operace* mají určité další vlastnosti, které se vyjadřují jako součást typu operace.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-229">*Operations* have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="e9b6b-230">Tyto vlastnosti obsahují informace o tom, které operace *funktory* podporuje.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-230">Such characteristics include information about which *functors* the operation supports.</span></span>
<span data-ttu-id="e9b6b-231">Například pokud provedení operace spoléhá na stav jiného qubits, pak by měla podporovat `Controlled` funktor; Pokud má operace hodnotu Inverted, měla by podporovat `Adjoint` funktor.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-231">For example, if the execution of the operation relies on the state of other qubits, then it should support the `Controlled` functor; if the operation has an inverse, then it should support the `Adjoint` functor.</span></span>

> [!NOTE]
> <span data-ttu-id="e9b6b-232">Tento článek popisuje, jak funktory mění signaturu operace.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-232">This article only discuss how functors alter the operation signature.</span></span> <span data-ttu-id="e9b6b-233">Další podrobnosti o funktory a operacích naleznete [v tématu Operations and Q# Functions in ](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="e9b6b-233">For more details about functors and operations, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span> 

<span data-ttu-id="e9b6b-234">Chcete-li `Controlled` v typu operace vyžadovat podporu pro a/nebo `Adjoint` funktor, je nutné přidat poznámku indikující odpovídající vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-234">To require support for the `Controlled` and/or `Adjoint` functor in an operation type, you need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="e9b6b-235">Poznámka `is Ctl` (například `(Qubit => Unit is Ctl)` ) indikuje, že operace je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-235">The annotation `is Ctl` (for example, `(Qubit => Unit is Ctl)`) indicates that the operation is controllable.</span></span> <span data-ttu-id="e9b6b-236">To znamená, že jeho spuštění spoléhá na stav jiného qubit nebo qubits.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-236">That is, its execution relies on the state of another qubit or qubits.</span></span> <span data-ttu-id="e9b6b-237">Podobně Poznámka `is Adj` znamená, že operace má sousední, to znamená, že se může jednat o "Inverted", který po sobě provede operaci, a pak její sousední vztah do stavu opustí stav beze změny.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-237">Similarly, the annotation `is Adj` indicates that the operation has an adjoint, that is, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="e9b6b-238">Pokud chcete vyžadovat, aby operace tohoto typu podporovala i `Adjoint` `Controlled` funktor, můžete to vyjádřit jako `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-238">If you want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor you can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="e9b6b-239">Například integrovaná <xref:microsoft.quantum.intrinsic.x> operace Pauli je typu `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-239">For example, the built-in Pauli <xref:microsoft.quantum.intrinsic.x> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="e9b6b-240">Typ operace, který nepodporuje žádné funktory, je určen samotným typem vstupu a výstupu bez další poznámky.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-240">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="e9b6b-241">Typ – parametrizované funkce a operace</span><span class="sxs-lookup"><span data-stu-id="e9b6b-241">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="e9b6b-242">Typy, které lze volat, mohou obsahovat *parametry typu*.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-242">Callable types may contain *type parameters*.</span></span>
<span data-ttu-id="e9b6b-243">Použijte symbol, který je předponou jednoduché uvozovky k označení parametru typu; Například je platným `'A` parametrem typu.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-243">Use a symbol prefixed by a single quote to indicated a type parameter; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="e9b6b-244">Další informace a podrobnosti o tom, jak definovat typ-parametrizované volat, naleznete [v tématu Operations and Q# Functions in ](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span><span class="sxs-lookup"><span data-stu-id="e9b6b-244">For more information and details on how to define type-parameterized callables, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span></span>

<span data-ttu-id="e9b6b-245">Parametr typu se může v jednom podpisu objevit více než jednou.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-245">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="e9b6b-246">Například funkce, která použije jinou funkci na každý prvek pole a vrátí shromážděné výsledky má signaturu `(('A[], 'A->'A) -> 'A[])` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-246">For example, a function that applies another function to each element of an array and returns the collected results has the signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="e9b6b-247">Podobně funkce, která vrací složení dvou operací, má signaturu `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .</span><span class="sxs-lookup"><span data-stu-id="e9b6b-247">Similarly, a function that returns the composition of two operations has the signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="e9b6b-248">Když vyvoláte typ s parametrem Invoke, všechny argumenty, které mají stejný parametr typu, musí být stejného typu.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-248">When you invoke a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="e9b6b-249">Q#neposkytuje mechanismus pro omezení možných typů, které může uživatel nahradit parametrem typu.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-249">Q# does not provide a mechanism for constraining the possible types that a user might substitute for a type parameter.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e9b6b-250">Další kroky</span><span class="sxs-lookup"><span data-stu-id="e9b6b-250">Next steps</span></span>

<span data-ttu-id="e9b6b-251">Nyní, když jste viděli všechny typy, které se skládají z Q# jazyka, naleznete [v tématu Výrazy Q# typu v](xref:microsoft.quantum.guide.expressions) , kde se dozvíte, jak vytvořit a manipulovat s výrazy těchto různých typů.</span><span class="sxs-lookup"><span data-stu-id="e9b6b-251">Now that you've seen all the types which comprise the Q# language, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to learn how to create and manipulate expressions of these various types.</span></span>
