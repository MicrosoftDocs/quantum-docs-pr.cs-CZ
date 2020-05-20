---
title: Typy v Q#
description: 'Seznamte se s různými typy použitými v programovacím jazyce Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: 4a551ee90a0abb6e42953cf04c7f5a8ca3573f26
ms.sourcegitcommit: 682a4a5f5dd23ca58a4addf62aea4086bb308552
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609137"
---
# <a name="types-in-q"></a><span data-ttu-id="5b2c7-103">Typy v Q#</span><span class="sxs-lookup"><span data-stu-id="5b2c7-103">Types in Q#</span></span>

<span data-ttu-id="5b2c7-104">Tato stránka obsahuje model typu Q # a popisuje syntaxi pro zadání a práci s typy.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-104">This page lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="5b2c7-105">Na další stránce [Zadejte výrazy](xref:microsoft.quantum.guide.expressions), podrobnosti o tom, jak vytvořit a pracovat na výrazech těchto typů.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-105">The next page, [Type Expressions](xref:microsoft.quantum.guide.expressions), details how to create and operate on expressions of these types.</span></span>

<span data-ttu-id="5b2c7-106">Upozorňujeme, že Q # je jazyk *silného typu* , takže pečlivé používání těchto typů může kompilátoru přispět, aby poskytovalo silné záruky na programy Q # v době kompilace.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="5b2c7-107">Aby bylo možné zajistit nejpřísnější záruky, převody mezi typy v Q # musí být explicitní pomocí volání funkcí, které tento převod vyjadřují.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-107">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="5b2c7-108">Celá řada takových funkcí je k dispozici jako součást <xref:microsoft.quantum.convert> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-108">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="5b2c7-109">Přetypování na kompatibilní typy na druhé straně se implicitně stane.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-109">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="5b2c7-110">Q # poskytuje jak primitivní typy, které lze použít přímo, a různé způsoby, jak vytvořit nové typy z jiných typů.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-110">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="5b2c7-111">Popíšeme všechny ve zbývající části tohoto oddílu.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-111">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="5b2c7-112">Primitivní typy</span><span class="sxs-lookup"><span data-stu-id="5b2c7-112">Primitive Types</span></span>

<span data-ttu-id="5b2c7-113">Jazyk Q # poskytuje několik *primitivních typů*, ze kterých lze sestavit další typy:</span><span class="sxs-lookup"><span data-stu-id="5b2c7-113">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="5b2c7-114">`Int`Typ představuje 64 celé číslo se znaménkem, např.: `2` , `107` , `-5` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-114">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="5b2c7-115">`BigInt`Typ představuje celé číslo se znaménkem libovolné velikosti, např. `2L` , `107L` , `-5L` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-115">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="5b2c7-116">Tento typ je založený na rozhraní .NET.<xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="5b2c7-116">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="5b2c7-117">textový.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-117">type.</span></span>
- <span data-ttu-id="5b2c7-118">`Double`Typ představuje číslo s plovoucí desetinnou čárkou s dvojitou přesností, například: `0.0` , `-1.3` , `4e-7` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-118">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="5b2c7-119">`Bool`Typ představuje logickou hodnotu, která může být buď `true` nebo `false` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-119">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="5b2c7-120">`Range`Typ představuje sekvenci celých čísel, označených jako `start..step..stop` , kde označuje, že krok je nepovinný.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-120">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="5b2c7-121">To `start .. stop` odpovídá `start..1..stop` , a například `1..2..7` představuje sekvenci $ \{ 1, 3, 5, 7 \} $.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-121">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="5b2c7-122">`String`Typ je posloupnost znaků Unicode, která je po vytvoření uživatelem neprůhledná.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-122">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="5b2c7-123">Tento typ slouží k hlášení zpráv na klasického hostitele v případě chyby nebo diagnostické události.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-123">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="5b2c7-124">`Unit`Typ je typ, který povoluje pouze jednu hodnotu `()` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-124">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="5b2c7-125">Tento typ slouží k označení, že funkce Q # nebo operace nevrátí žádné informace.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-125">This type is used to indicate that Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="5b2c7-126">`Qubit`Typ představuje bit s podmnožinou nebo qubit.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-126">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="5b2c7-127">`Qubit`s jsou neprůhlední pro uživatele; jedinou operací, která je k dispozici, je kromě jejich předání jiné operaci testovat identitu (rovnost).</span><span class="sxs-lookup"><span data-stu-id="5b2c7-127">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="5b2c7-128">V konečném případě `Qubit` jsou akce u s implementovány voláním vnitřních instrukcí na procesor nebo na základě jeho simulace.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-128">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="5b2c7-129">`Pauli`Typ představuje jednu ze čtyř operátorů Pauli s jedním qubit.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-129">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="5b2c7-130">Tento typ slouží k označení základní operace pro rotace a určení pozorovatele, které se měří.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-130">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="5b2c7-131">Toto je výčtový typ, který má čtyři možné hodnoty: `PauliI` , `PauliX` , `PauliY` a `PauliZ` , což jsou konstanty typu `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-131">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="5b2c7-132">`Result`Typ představuje výsledek měření.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-132">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="5b2c7-133">Toto je výčtový typ se dvěma možnými hodnotami: `One` a `Zero` , což jsou konstanty typu `Result` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-133">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="5b2c7-134">`Zero`indikuje, že došlo k měření + 1 eigenvalue. `One`označuje eigenvalue-1.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-134">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>

<span data-ttu-id="5b2c7-135">Konstanty,,,,,, `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` a `Zero` jsou všechny rezervované symboly v Q #.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-135">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="5b2c7-136">Typy polí</span><span class="sxs-lookup"><span data-stu-id="5b2c7-136">Array Types</span></span>

<span data-ttu-id="5b2c7-137">Vzhledem k platnému typu Q # `'T` existuje typ, který představuje pole hodnot typu `'T` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-137">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="5b2c7-138">Tento typ pole je reprezentován jako, `'T[]` například `Qubit[]` nebo `Int[][]` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-138">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="5b2c7-139">Například kolekce celých čísel je označena `Int[]` , zatímco pole `(Bool, Pauli)` hodnot pole je označeno `(Bool, Pauli)[][]` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-139">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="5b2c7-140">V druhém příkladu si všimněte, že představuje potenciálně vícenásobné pole polí a ne obdélníkové dvourozměrné pole.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-140">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="5b2c7-141">Q # neposkytuje podporu pro pravoúhlá pole s multidimenzionálními hodnotami.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-141">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="5b2c7-142">Hodnota pole může být napsána ve zdrojovém kódu Q # pomocí hranatých závorek kolem prvků pole, jako v `[PauliI, PauliX, PauliY, PauliZ]` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-142">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="5b2c7-143">Typ literálu pole je určen běžným základním typem všech položek v poli.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-143">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="5b2c7-144">Po vytvoření pole nelze prvky pole změnit.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-144">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="5b2c7-145">K vytvoření upraveného pole lze použít [Příkazy Update a Reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) a [výrazy Copy a Update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-145">[Update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) and/or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) can be used to construct a modified array.</span></span>

<span data-ttu-id="5b2c7-146">Alternativně lze pole vytvořit z jeho velikosti pomocí `new` klíčového slova:</span><span class="sxs-lookup"><span data-stu-id="5b2c7-146">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="5b2c7-147">V obou případech lze po sestavení pole použít základní funkci `Length` k získání počtu prvků jako `Int` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-147">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="5b2c7-148">Pole lze podskriptovat pomocí hranatých závorek s podscripty typu `Int` nebo typu `Range` , aby získaly buď jednotlivé prvky, nebo nová pole obsahující podmnožinu prvků pole.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-148">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="5b2c7-149">Dolní indexy polí jsou počítány od nuly:</span><span class="sxs-lookup"><span data-stu-id="5b2c7-149">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="5b2c7-150">Typy řazené kolekce členů</span><span class="sxs-lookup"><span data-stu-id="5b2c7-150">Tuple Types</span></span>

<span data-ttu-id="5b2c7-151">Vzhledem k nule nebo více různým typům, `T0` `T1` ,..., `Tn` můžeme jako *typ zadat nový typ řazené kolekce členů* `(T0, T1, ..., Tn)` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-151">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="5b2c7-152">Typy použité k vytvoření nového typu řazené kolekce členů mohou být řazené kolekce členů, jako v `(Int, (Qubit, Qubit))` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-152">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="5b2c7-153">Takové vnořování je vždy omezené, ale v případě, že typy řazené kolekce členů nemůžou za žádných okolností obsahovat samy sebe.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-153">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="5b2c7-154">Hodnoty nového typu řazené kolekce členů jsou řazené kolekce členů vytvořené pomocí sekvencí hodnot z každého typu v řazené kolekci členů.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-154">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="5b2c7-155">Například `(3, false)` je řazená kolekce členů, jejíž typ je typ řazené kolekce členů `(Int, Bool)` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-155">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="5b2c7-156">Je možné vytvořit pole řazených kolekcí členů, řazené kolekce členů, řazené kolekce členů, atd.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-156">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="5b2c7-157">Od Q # 0,3 `Unit` je název *typu* prázdné řazené kolekce členů; `()` používá se pro prázdnou *hodnotu*řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-157">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="5b2c7-158">Instance řazené kolekce členů jsou neměnné.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-158">Tuple instances are immutable.</span></span>
<span data-ttu-id="5b2c7-159">Q # neposkytuje mechanismus pro změnu obsahu řazené kolekce členů po vytvoření.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-159">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="5b2c7-160">Řazené kolekce členů jsou účinným konceptem použitým v rámci Q # ke shromáždění hodnot dohromady do jedné hodnoty, což usnadňuje jejich předání.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-160">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="5b2c7-161">Konkrétně při použití notace řazené kolekce členů můžeme vyjádřit, že každá operace a možnost volat přebírá přesně jeden vstup a vrátí přesně jeden výstup.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-161">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="5b2c7-162">Rovnost řazené kolekce členů singleton</span><span class="sxs-lookup"><span data-stu-id="5b2c7-162">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="5b2c7-163">Je možné vytvořit singleton (jeden prvek) řazené kolekce členů, `('T1)` například `(5)` nebo `([1,2,3])` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-163">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="5b2c7-164">Otázka č. Q však považuje typ Tuple typu Singleton za úplný ekvivalent hodnoty uzavřeného typu.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-164">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="5b2c7-165">To znamená, že neexistuje žádný rozdíl mezi `5` a `(5)` , ani mezi `5` a `(((5)))` , ani mezi `(5, (6))` a `(5, 6)` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-165">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="5b2c7-166">Je stejně platná pro zápis `(5)+3` jako k zápisu `5+3` a oba výrazy budou vyhodnoceny `8` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>

<span data-ttu-id="5b2c7-167">Tato rovnocennost se vztahuje na všechny účely, včetně přiřazení a výrazů.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-167">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="5b2c7-168">V případě libovolného výrazu je stejný výraz uzavřený v závorkách výraz stejného typu.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-168">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="5b2c7-169">Například `(7)` výraz je výraz `Int` , `([1,2,3])` je výraz typu array `Int` s a `((1,2))` je výraz s typem `(Int, Int)` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-169">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="5b2c7-170">Konkrétně to znamená, že operace nebo funkce, jejíž vstupní řazená kolekce členů nebo výstupní řazená kolekce členů má jedno pole, může být považována za jeden argument nebo vrací jedinou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-170">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="5b2c7-171">Tato vlastnost odkazuje jako na _rovnost v řazené kolekci členů typu Singleton_.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-171">We refer to this property as _singleton tuple equivalence_.</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="5b2c7-172">Uživatelsky definované typy</span><span class="sxs-lookup"><span data-stu-id="5b2c7-172">User-Defined Types</span></span>

<span data-ttu-id="5b2c7-173">Uživatelsky definovaná deklarace typu se skládá z klíčového slova `newtype` , následované názvem uživatelsky definovaného typu, a `=` platnou specifikací typu a ukončující středník.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-173">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="5b2c7-174">Například:</span><span class="sxs-lookup"><span data-stu-id="5b2c7-174">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="5b2c7-175">Každý zdrojový soubor Q # může deklarovat libovolný počet uživatelsky definovaných typů.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-175">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="5b2c7-176">Názvy typů musí být v rámci oboru názvů jedinečné a nemusí být v konfliktu s názvy operací a funkcí.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-176">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="5b2c7-177">Uživatelsky definované typy jsou odlišné, i když základní typy jsou identické.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-177">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="5b2c7-178">Konkrétně neexistuje žádný automatický převod mezi hodnotami dvou uživatelsky definovaných typů i v případě, že jsou základní typy identické.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-178">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="5b2c7-179">Pojmenované vs. anonymní položky</span><span class="sxs-lookup"><span data-stu-id="5b2c7-179">Named vs. anonymous items</span></span>

<span data-ttu-id="5b2c7-180">Soubor Q # může definovat nový pojmenovaný typ obsahující jednu hodnotu jakéhokoli právního typu.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-180">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="5b2c7-181">Pro libovolný typ řazené kolekce členů `T` můžeme deklarovat nový uživatelsky definovaný typ, který je podtypem `T` s `newtype` příkazem.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-181">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="5b2c7-182">V @"microsoft.quantum.math" oboru názvů je například komplexní čísla definována jako uživatelsky definovaný typ:</span><span class="sxs-lookup"><span data-stu-id="5b2c7-182">In the @"microsoft.quantum.math" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="5b2c7-183">Tento příkaz vytvoří nový typ se dvěma anonymními položkami typu `Double` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-183">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="5b2c7-184">Kromě anonymních položek podporuje uživatelsky definované typy také *pojmenované položky* jako Q # verze 0,7 nebo vyšší.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-184">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="5b2c7-185">Například můžeme mít název k položkám `Re` pro dvojitou hodnotu představující reálnou část komplexního čísla a `Im` pro imaginární část:</span><span class="sxs-lookup"><span data-stu-id="5b2c7-185">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="5b2c7-186">Pojmenování jedné položky v uživatelsky definovaném typu neznamená, že všechny položky musí být pojmenovány – podporuje se libovolná kombinace pojmenovaných a nepojmenovaných položek.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-186">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="5b2c7-187">Kromě toho mohou být také pojmenovány vnitřní položky.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-187">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="5b2c7-188">Typ `Nested` definovaný níže pro příklad má základní typ `(Double, (Int, String))` , z nějž `Int` je pojmenována pouze položka typu a všechny ostatní položky jsou anonymní.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-188">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="5b2c7-189">Pojmenované položky mají výhodu, ke kterým lze přistupovat přímo prostřednictvím *operátoru přístupu* `::` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-189">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="5b2c7-190">Kromě poskytování krátkých aliasů pro potenciálně složité typy řazené kolekce členů, což je jedna významná výhoda pro definování takových typů, je, že mohou zdokumentovat záměr konkrétní hodnoty.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-190">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="5b2c7-191">Návrat do příkladu `Complex` , jeden mohl také definovat 2D polární souřadnice jako uživatelsky definovaný typ:</span><span class="sxs-lookup"><span data-stu-id="5b2c7-191">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="5b2c7-192">I když oba i mají `Complex` `Polar` základní typ `(Double, Double)` , jsou tyto dva typy zcela nekompatibilní v Q # a minimalizují riziko náhodného volání komplexní matematické funkce s polárními souřadnicemi a naopak.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-192">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="5b2c7-193">Tímto způsobem mají uživatelsky definované typy podobnou roli jako záznamy v F # například.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-193">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="5b2c7-194">Přístup k anonymním položkám pomocí operátoru rozbalení</span><span class="sxs-lookup"><span data-stu-id="5b2c7-194">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="5b2c7-195">Aby bylo možné přistupovat k anonymním položkám na druhé straně, je třeba zabalenou hodnotu nejprve extrahovat pomocí operátoru přípony `!` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-195">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="5b2c7-196">Operátor "Unwrap" `!` umožňuje extrahovat hodnotu obsaženou v uživatelsky definovaném typu.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-196">The "unwrap" operator, `!`, allows to extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="5b2c7-197">Typ takového výrazu "Unwrap" je základní typ uživatelsky definovaného typu.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-197">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="5b2c7-198">Operátor rozbalení rozbalí právě jednu vrstvu obtékání.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-198">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="5b2c7-199">Pro přístup k hodnotě zabalené na násobení lze použít více operátorů rozbalení.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-199">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="5b2c7-200">Například:</span><span class="sxs-lookup"><span data-stu-id="5b2c7-200">For instance:</span></span>

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

<span data-ttu-id="5b2c7-201">Další podrobnosti o operátoru rozbalení lze nalézt ve [výrazech typu v Q #](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="5b2c7-201">More details on the unwrap operator can be found at [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="5b2c7-202">Vytváření hodnot uživatelsky definovaných typů</span><span class="sxs-lookup"><span data-stu-id="5b2c7-202">Creating values of user-defined types</span></span>

<span data-ttu-id="5b2c7-203">Hodnoty uživatelsky definovaného typu lze vytvořit voláním odpovídajícího konstruktoru typu:</span><span class="sxs-lookup"><span data-stu-id="5b2c7-203">Values of a user-defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="5b2c7-204">Případně můžete nové hodnoty vytvořit z existujících pomocí [výrazů kopírování a aktualizace](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="5b2c7-204">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="5b2c7-205">Podobně jako u polí tyto výrazy kopírují všechny hodnoty položky původního výrazu s výjimkou zadaných pojmenovaných položek.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-205">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="5b2c7-206">Pro tyto hodnoty jsou nastaveny na ty definované na pravé straně výrazu.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-206">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="5b2c7-207">Jakékoli jiné jazykové konstrukce, například [Příkazy Update-a-Reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), které jsou k dispozici pro položky pole existují také pro pojmenované položky v uživatelsky definovaných typech.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-207">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), that are available for array items exist for named-items in user-defined types as well.</span></span>

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

<span data-ttu-id="5b2c7-208">Uživatelsky definované typy lze použít kdekoli v jakémkoli jiném typu.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-208">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="5b2c7-209">Konkrétně je možné definovat pole uživatelsky definovaného typu a zahrnout uživatelsky definovaný typ jako prvek typu řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-209">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="5b2c7-210">Poznámka: nemůžete vytvořit struktury rekurzivního typu.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-210">Note is not possible to create recursive type structures.</span></span>
<span data-ttu-id="5b2c7-211">To znamená, že typ, který definuje uživatelsky definovaný typ, nemůže být typ řazené kolekce členů, který obsahuje prvek uživatelsky definovaného typu.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-211">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="5b2c7-212">Obecněji, uživatelsky definované typy nemůžou mít na sobě navzájem cyklické závislosti, takže následující sada definic typu by mohla být neplatná:</span><span class="sxs-lookup"><span data-stu-id="5b2c7-212">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a><span data-ttu-id="5b2c7-213">Typy operací a funkcí</span><span class="sxs-lookup"><span data-stu-id="5b2c7-213">Operation and Function Types</span></span>

<span data-ttu-id="5b2c7-214">Základní typ pro všechny volat lze zapsat jako `('Tinput => 'Tresult)` nebo `('Tinput -> 'Tresult)` , kde `'Tinput` a `'Tresult` jsou typy.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-214">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="5b2c7-215">Nazývají se *signatury* , které lze volat.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-215">These are called the *signature* of the callable.</span></span>

<span data-ttu-id="5b2c7-216">Všechny volat pomocí Q # se považují za vstupní hodnotu a jako výstup vrátí jedinou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-216">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="5b2c7-217">Vstupní i výstupní hodnoty mohou být řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-217">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="5b2c7-218">Je k dispozici bez výsledku vrácení `Unit` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-218">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="5b2c7-219">Volat, které nemají žádný vstup, přebírají jako vstup prázdnou řazenou kolekci členů.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-219">Callables that have no input take the empty tuple as input.</span></span>

> [!NOTE]
> <span data-ttu-id="5b2c7-220">První formulář s, se `=>` používá pro operace, druhý formulář, with `->` , for Functions.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-220">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
> <span data-ttu-id="5b2c7-221">Například `((Qubit, Pauli) => Result)` představuje signaturu pro možnou operaci měření s jedním qubit.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-221">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>
<span data-ttu-id="5b2c7-222">Typy *funkcí* jsou zcela určeny jejich signaturou.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-222">*Function* types are completely specified by their signature.</span></span>
<span data-ttu-id="5b2c7-223">Například funkce, která vypočítá sinus úhlu, by měla typ `(Double -> Double)` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-223">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="5b2c7-224">*Operations*---, ale funkce not---mají určité další vlastnosti, které se vyjadřují jako součást typu operace.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-224">*Operations*---but not functions---have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="5b2c7-225">Tyto vlastnosti zahrnují informace o tom, co *funktory* operace podporuje.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-225">Such characteristics include information about what *functors* the operation supports.</span></span>
<span data-ttu-id="5b2c7-226">Například pokud provádění operace může být podmíněně na stav jiného qubits, měla by podporovat `Controlled` funktor; Pokud má operace hodnotu INVERT, měla by podporovat `Adjoint` funktor.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-226">For example, if execution of the operation can be conditioned on the state of other qubits, it should support the `Controlled` functor; if the operation has an inverse, it should support the `Adjoint` functor.</span></span> <span data-ttu-id="5b2c7-227">Funktory a operace jsou podrobněji popsány v tématu [operace a funkce v Q #](xref:microsoft.quantum.guide.operationsfunctions), ale v této části jednoduše probereme, jak tato změna signatura operace mění.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-227">Functors and operations are discussed in detail at [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions), but here we simply discuss how this alters the operation signature.</span></span>

<span data-ttu-id="5b2c7-228">Aby `Controlled` bylo nutné v typu operace vyžadovat podporu pro a/nebo `Adjoint` funktor, musíme přidat poznámku indikující odpovídající vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-228">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="5b2c7-229">Anotace `is Ctl` (např. `(Qubit => Unit is Ctl)` ) indikuje, že operace je ovladatelné---to znamená, že je vykonávání stavu jiného qubit nebo qubits.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-229">An annotation `is Ctl` (e.g. `(Qubit => Unit is Ctl)`) indicates that the operation is controllable---that is, it's execution conditioned on the state of another qubit or qubits.</span></span> <span data-ttu-id="5b2c7-230">Podobně `is Adj` označuje, že operace má sousední, nebo jednoduše, může být "obrácená" tak, že se po sobě provede operace, a potom její sousední vztah do stavu opustí stav beze změny.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-230">Similarly, `is Adj` indicates that the operation has an adjoint; or simply, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="5b2c7-231">Pokud chceme vyžadovat, aby operace tohoto typu podporovala i `Adjoint` `Controlled` funktor, můžeme to vyjádřit jako `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-231">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="5b2c7-232">Například integrovaná <xref:microsoft.quantum.intrinsic.x> operace Pauli je typu `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-232">For example, the built-in Pauli <xref:microsoft.quantum.intrinsic.x> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="5b2c7-233">Typ operace, který nepodporuje žádné funktory, je určen samotným typem vstupu a výstupu bez další poznámky.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-233">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="5b2c7-234">Typ – parametrizované funkce a operace</span><span class="sxs-lookup"><span data-stu-id="5b2c7-234">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="5b2c7-235">Typy, které lze volat, mohou obsahovat parametry typu.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-235">Callable types may contain type parameters.</span></span>
<span data-ttu-id="5b2c7-236">Parametry typu jsou označeny symbolem, který je předponou jedné uvozovky. Například je platným `'A` parametrem typu.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-236">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="5b2c7-237">Podrobnosti o definování typu, který lze volat, jsou k dispozici na stránce [operace a funkce v Q #](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-237">Details on defining type-parameterized callables are provided on the [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) page.</span></span>

<span data-ttu-id="5b2c7-238">Parametr typu se může v jednom podpisu objevit více než jednou.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-238">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="5b2c7-239">Například funkce, která použije jinou funkci na každý prvek pole a vrátí shromážděné výsledky, by měly signaturu `(('A[], 'A->'A) -> 'A[])` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-239">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="5b2c7-240">Podobně funkce, která vrací složení dvou operací, může mít signaturu `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-240">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="5b2c7-241">Při vyvolání volání typu s parametrem typu musí být všechny argumenty, které mají stejný parametr typu, stejného typu.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-241">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="5b2c7-242">Q # neposkytuje mechanismus pro omezení možných typů, které mohou být nahrazeny parametrem typu.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-242">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

## <a name="whats-next"></a><span data-ttu-id="5b2c7-243">A co dál?</span><span class="sxs-lookup"><span data-stu-id="5b2c7-243">What's Next?</span></span>
<span data-ttu-id="5b2c7-244">Teď, když jste viděli všechny typy, které tvoří jazyk Q #, můžete přejít na [typ výrazy v Q #](xref:microsoft.quantum.guide.expressions) a podívat se, jak vytvořit a manipulovat s výrazy těchto různých typů.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-244">Now that you've seen all the types which comprise the Q# language, you can head to [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to see how to create and manipulate expressions of these various types.</span></span>


