---
title: 'Typ Q # model | Microsoft Docs'
description: Model typu Q#
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 0aabb144779da301b71ad215c8e975cc29b4dcce
ms.sourcegitcommit: ca5015fed409eaf0395a89c2e4bc6a890c360aa2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76871630"
---
# <a name="the-type-model"></a><span data-ttu-id="8ec35-103">Model typu</span><span class="sxs-lookup"><span data-stu-id="8ec35-103">The Type Model</span></span>

<span data-ttu-id="8ec35-104">V této části se dozvíte o modelu typu Q # a popisuje syntaxi pro zadání a práci s typy.</span><span class="sxs-lookup"><span data-stu-id="8ec35-104">This section lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="8ec35-105">Upozorňujeme, že Q # je jazyk *silného typu* , takže pečlivé používání těchto typů může kompilátoru přispět, aby poskytovalo silné záruky na programy Q # v době kompilace.</span><span class="sxs-lookup"><span data-stu-id="8ec35-105">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>

<span data-ttu-id="8ec35-106">Aby bylo možné zajistit nejpřísnější záruky, převody mezi typy v Q # musí být explicitní pomocí volání funkcí, které tento převod vyjadřují.</span><span class="sxs-lookup"><span data-stu-id="8ec35-106">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="8ec35-107">K dispozici je celá řada takových funkcí jako součást oboru názvů <xref:microsoft.quantum.convert>.</span><span class="sxs-lookup"><span data-stu-id="8ec35-107">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="8ec35-108">Přetypování na kompatibilní typy na druhé straně se implicitně stane.</span><span class="sxs-lookup"><span data-stu-id="8ec35-108">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="8ec35-109">Q # poskytuje jak primitivní typy, které lze použít přímo, a různé způsoby, jak vytvořit nové typy z jiných typů.</span><span class="sxs-lookup"><span data-stu-id="8ec35-109">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="8ec35-110">Popíšeme všechny ve zbývající části tohoto oddílu.</span><span class="sxs-lookup"><span data-stu-id="8ec35-110">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="8ec35-111">Primitivní typy</span><span class="sxs-lookup"><span data-stu-id="8ec35-111">Primitive Types</span></span>

<span data-ttu-id="8ec35-112">Jazyk Q # poskytuje několik *primitivních typů*, ze kterých lze sestavit další typy:</span><span class="sxs-lookup"><span data-stu-id="8ec35-112">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="8ec35-113">Typ `Int` představuje celé číslo se znaménkem 64, např.: `2`, `107``-5`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-113">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="8ec35-114">Typ `BigInt` představuje celé číslo se znaménkem libovolné velikosti, např. `2L`, `107L``-5L`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-114">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="8ec35-115">Tento typ je založený na <xref:System.Numerics.BigInteger> .NET.</span><span class="sxs-lookup"><span data-stu-id="8ec35-115">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="8ec35-116">textový.</span><span class="sxs-lookup"><span data-stu-id="8ec35-116">type.</span></span>
- <span data-ttu-id="8ec35-117">Typ `Double` představuje číslo s plovoucí desetinnou čárkou s dvojitou přesností, např.: `0.0`, `-1.3`, `4e-7`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-117">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="8ec35-118">Typ `Bool` představuje logickou hodnotu, která může být buď `true` nebo `false`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-118">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="8ec35-119">Typ `Qubit` představuje bit qubit nebo.</span><span class="sxs-lookup"><span data-stu-id="8ec35-119">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="8ec35-120">`Qubit`s jsou neprůhledné pro uživatele; jedinou operací, která je k dispozici, je kromě jejich předání jiné operaci testovat identitu (rovnost).</span><span class="sxs-lookup"><span data-stu-id="8ec35-120">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="8ec35-121">V konečném případě se akce u `Qubit`s implementují voláním vnitřních instrukcí na procesor s více procesory (nebo na jeho simulaci).</span><span class="sxs-lookup"><span data-stu-id="8ec35-121">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="8ec35-122">Typ `Pauli` představuje jednu ze čtyř operátorů Pauli s jedním qubit.</span><span class="sxs-lookup"><span data-stu-id="8ec35-122">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="8ec35-123">Tento typ slouží k označení základní operace pro rotace a určení pozorovatele, které se měří.</span><span class="sxs-lookup"><span data-stu-id="8ec35-123">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="8ec35-124">Toto je výčtový typ, který má čtyři možné hodnoty: `PauliI`, `PauliX`, `PauliY`a `PauliZ`, což jsou konstanty typu `Pauli`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-124">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="8ec35-125">Typ `Result` představuje výsledek měření.</span><span class="sxs-lookup"><span data-stu-id="8ec35-125">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="8ec35-126">Toto je výčtový typ se dvěma možnými hodnotami: `One` a `Zero`, což jsou konstanty typu `Result`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-126">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="8ec35-127">`Zero` označuje, že došlo k měření + 1 eigenvalue; `One` označuje eigenvalue-1.</span><span class="sxs-lookup"><span data-stu-id="8ec35-127">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>
- <span data-ttu-id="8ec35-128">Typ `Range` představuje sekvenci celých čísel, označených `start..step..stop`, kde označuje krok s možnostmi.</span><span class="sxs-lookup"><span data-stu-id="8ec35-128">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is options.</span></span> 
   <span data-ttu-id="8ec35-129">To znamená, že `start .. stop` odpovídá `start..1..stop`a například `1..2..7` představuje sekvenci $\{1, 3, 5, 7\}$.</span><span class="sxs-lookup"><span data-stu-id="8ec35-129">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="8ec35-130">Typ `String` je posloupnost znaků Unicode, která je po vytvoření uživatelem neprůhledná.</span><span class="sxs-lookup"><span data-stu-id="8ec35-130">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="8ec35-131">Tento typ slouží k hlášení zpráv na klasického hostitele v případě chyby nebo diagnostické události.</span><span class="sxs-lookup"><span data-stu-id="8ec35-131">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="8ec35-132">Typ `Unit` je typ, který povoluje pouze jednu hodnotu `()`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-132">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="8ec35-133">Tento typ slouží k označení, že funkce Q # nebo operace nevrátí žádné informace.</span><span class="sxs-lookup"><span data-stu-id="8ec35-133">This type is used to indicate that Q# function or operation returns no information.</span></span> 

<span data-ttu-id="8ec35-134">Konstanty `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`a `Zero`, jsou všechny rezervované symboly v Q #.</span><span class="sxs-lookup"><span data-stu-id="8ec35-134">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="8ec35-135">Typy polí</span><span class="sxs-lookup"><span data-stu-id="8ec35-135">Array Types</span></span>

<span data-ttu-id="8ec35-136">Vzhledem k platnému `'T`typu Q # existuje typ, který představuje pole hodnot typu `'T`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-136">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="8ec35-137">Tento typ pole je reprezentován jako `'T[]`; například `Qubit[]` nebo `Int[][]`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-137">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="8ec35-138">Například kolekce celých čísel je označena `Int[]`, zatímco pole polí hodnot `(Bool, Pauli)` je označeno `(Bool, Pauli)[][]`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-138">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="8ec35-139">V druhém příkladu si všimněte, že představuje potenciálně vícenásobné pole polí a ne obdélníkové dvourozměrné pole.</span><span class="sxs-lookup"><span data-stu-id="8ec35-139">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="8ec35-140">Q # neposkytuje podporu pro pravoúhlá pole s multidimenzionálními hodnotami.</span><span class="sxs-lookup"><span data-stu-id="8ec35-140">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="8ec35-141">Hodnota pole může být napsána ve zdrojovém kódu Q # pomocí hranatých závorek kolem prvků pole, jak je uvedeno v `[PauliI, PauliX, PauliY, PauliZ]`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-141">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="8ec35-142">Typ literálu pole je určen běžným základním typem všech položek v poli.</span><span class="sxs-lookup"><span data-stu-id="8ec35-142">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="8ec35-143">Po vytvoření pole nelze prvky pole změnit.</span><span class="sxs-lookup"><span data-stu-id="8ec35-143">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="8ec35-144">K vytvoření upraveného pole lze použít příkazy Update a Reassign a výrazy Copy a Update.</span><span class="sxs-lookup"><span data-stu-id="8ec35-144">Update-and-reassign statements and/or copy-and-update expressions can be used to construct a modified array.</span></span>

<span data-ttu-id="8ec35-145">Pole lze také vytvořit z jeho velikosti pomocí klíčového slova `new`:</span><span class="sxs-lookup"><span data-stu-id="8ec35-145">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="8ec35-146">V obou případech je po sestavení pole základní funkce `Length` možné použít k získání počtu prvků jako `Int`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-146">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="8ec35-147">Pole mohou být v dolních lomených závorkách, s dolními indexy buď typu `Int`, nebo typu `Range`, pro získání jednoho nebo nového pole obsahujícího podmnožinu prvků pole.</span><span class="sxs-lookup"><span data-stu-id="8ec35-147">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="8ec35-148">Dolní indexy polí jsou počítány od nuly:</span><span class="sxs-lookup"><span data-stu-id="8ec35-148">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="8ec35-149">Typy řazené kolekce členů</span><span class="sxs-lookup"><span data-stu-id="8ec35-149">Tuple Types</span></span>

<span data-ttu-id="8ec35-150">Vzhledem k nule nebo více různým typům `T0`, `T1`,... `Tn`, můžeme jako `(T0, T1, ..., Tn)`poznamenat nový *typ řazené kolekce členů* .</span><span class="sxs-lookup"><span data-stu-id="8ec35-150">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="8ec35-151">Typy, které slouží k vytvoření nového typu řazené kolekce členů, mohou být řazené kolekce členů, jako v `(Int, (Qubit, Qubit))`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-151">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="8ec35-152">Takové vnořování je vždy omezené, ale v případě, že typy řazené kolekce členů nemůžou za žádných okolností obsahovat samy sebe.</span><span class="sxs-lookup"><span data-stu-id="8ec35-152">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="8ec35-153">Hodnoty nového typu řazené kolekce členů jsou řazené kolekce členů vytvořené pomocí sekvencí hodnot z každého typu v řazené kolekci členů.</span><span class="sxs-lookup"><span data-stu-id="8ec35-153">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="8ec35-154">Například `(3, false)` je řazená kolekce členů, jejíž typ je typ řazené kolekce členů `(Int, Bool)`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-154">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="8ec35-155">Je možné vytvořit pole řazených kolekcí členů, řazené kolekce členů, řazené kolekce členů, atd.</span><span class="sxs-lookup"><span data-stu-id="8ec35-155">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="8ec35-156">Od Q # 0,3 je `Unit` název *typu* prázdné řazené kolekce členů; pro prázdnou *hodnotu*řazené kolekce členů se používá `()`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-156">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="8ec35-157">Instance řazené kolekce členů jsou neměnné.</span><span class="sxs-lookup"><span data-stu-id="8ec35-157">Tuple instances are immutable.</span></span>
<span data-ttu-id="8ec35-158">Q # neposkytuje mechanismus pro změnu obsahu řazené kolekce členů po vytvoření.</span><span class="sxs-lookup"><span data-stu-id="8ec35-158">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="8ec35-159">Řazené kolekce členů jsou účinným konceptem použitým v rámci Q # ke shromáždění hodnot dohromady do jedné hodnoty, což usnadňuje jejich předání.</span><span class="sxs-lookup"><span data-stu-id="8ec35-159">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="8ec35-160">Konkrétně při použití notace řazené kolekce členů můžeme vyjádřit, že každá operace a možnost volat přebírá přesně jeden vstup a vrátí přesně jeden výstup.</span><span class="sxs-lookup"><span data-stu-id="8ec35-160">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="8ec35-161">Rovnost řazené kolekce členů singleton</span><span class="sxs-lookup"><span data-stu-id="8ec35-161">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="8ec35-162">Je možné vytvořit singleton (jeden prvek) řazené kolekce členů, `('T1)`, například `(5)` nebo `([1,2,3])`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-162">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="8ec35-163">Otázka č. Q však považuje typ Tuple typu Singleton za úplný ekvivalent hodnoty uzavřeného typu.</span><span class="sxs-lookup"><span data-stu-id="8ec35-163">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="8ec35-164">To znamená, že se nejedná o rozdíl mezi `5` a `(5)`ani mezi `5`mi a `(((5)))`nebo mezi `(5, (6))` a `(5, 6)`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-164">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>

<span data-ttu-id="8ec35-165">Tato rovnocennost se vztahuje na všechny účely, včetně přiřazení a výrazů.</span><span class="sxs-lookup"><span data-stu-id="8ec35-165">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="8ec35-166">Je stejná jako platná pro zápis `(5)+3` jako zápis `5+3`a oba výrazy se vyhodnotí jako `8`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>
<span data-ttu-id="8ec35-167">Konkrétně to znamená, že operace nebo funkce, jejíž vstupní řazená kolekce členů nebo výstupní řazená kolekce členů má jedno pole, může být považována za jeden argument nebo vrací jedinou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="8ec35-167">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="8ec35-168">Tato vlastnost odkazuje jako na _rovnost v řazené kolekci členů typu Singleton_.</span><span class="sxs-lookup"><span data-stu-id="8ec35-168">We refer to this property as _singleton tuple equivalence_.</span></span>

## <a name="user-defined-types"></a><span data-ttu-id="8ec35-169">Uživatelsky definované typy</span><span class="sxs-lookup"><span data-stu-id="8ec35-169">User-Defined Types</span></span>

<span data-ttu-id="8ec35-170">Soubor Q # může definovat nový pojmenovaný typ obsahující jednu hodnotu jakéhokoli právního typu.</span><span class="sxs-lookup"><span data-stu-id="8ec35-170">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="8ec35-171">Pro jakýkoli typ řazené kolekce členů `T`můžeme deklarovat nový uživatelsky definovaný typ, který je podtypem `T` pomocí příkazu `newtype`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-171">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="8ec35-172">V oboru názvů @"microsoft.quantum.math" jsou například komplexní čísla definovány jako uživatelsky definovaný typ:</span><span class="sxs-lookup"><span data-stu-id="8ec35-172">In the @"microsoft.quantum.math" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```

<span data-ttu-id="8ec35-173">Tento příkaz vytvoří nový typ se dvěma anonymními položkami typu `Double`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-173">This statement creates a new type with two anonymous items of type `Double`.</span></span>   
<span data-ttu-id="8ec35-174">Kromě anonymních položek podporuje uživatelsky definované typy také pojmenované položky jako Q # verze 0,7 nebo vyšší.</span><span class="sxs-lookup"><span data-stu-id="8ec35-174">Aside from anonymous items, user defined types also support named items as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="8ec35-175">Například můžeme mít název položky `Re` pro dvojitou hodnotu, která představuje skutečnou část komplexního čísla a `Im` pro imaginární část:</span><span class="sxs-lookup"><span data-stu-id="8ec35-175">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="8ec35-176">Pojmenování jedné položky v uživatelsky definovaném typu neznamená, že všechny položky musí být pojmenovány – podporuje se libovolná kombinace pojmenovaných a nepojmenovaných položek.</span><span class="sxs-lookup"><span data-stu-id="8ec35-176">Naming one item in a user defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="8ec35-177">Kromě toho mohou být pojmenovány také vnitřní položky.</span><span class="sxs-lookup"><span data-stu-id="8ec35-177">Furthermore, also inner items may be named.</span></span>
<span data-ttu-id="8ec35-178">Typ `Nested`, jak je definováno níže pro příklad má `(Double, (Int, String))`základního typu, z něhož je pojmenována pouze položka typu `Int` a všechny ostatní položky jsou anonymní.</span><span class="sxs-lookup"><span data-stu-id="8ec35-178">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
<span data-ttu-id="8ec35-179">Pojmenované položky mají výhodu, ke kterým lze přistupovat přímo prostřednictvím operátoru přístupu `::`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-179">Named items have the advantage that they can be accessed directly via the access operator `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="8ec35-180">Aby bylo možné přistupovat k anonymním položkám na druhé straně, je třeba zabalenou hodnotu nejprve extrahovat pomocí operátoru přípony `!`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-180">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="8ec35-181">Operátor "Unwrap", `!`umožňuje extrahovat hodnotu obsaženou v uživatelsky definovaném typu.</span><span class="sxs-lookup"><span data-stu-id="8ec35-181">The "unwrap" operator, `!`, allows to extract the value contained in a user defined type.</span></span>
<span data-ttu-id="8ec35-182">Typ takového výrazu "Unwrap" je základní typ uživatelsky definovaného typu.</span><span class="sxs-lookup"><span data-stu-id="8ec35-182">The type of such an "unwrap" expression is the underlying type of the user defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="8ec35-183">Operátor rozbalení rozbalí právě jednu vrstvu obtékání.</span><span class="sxs-lookup"><span data-stu-id="8ec35-183">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="8ec35-184">Pro přístup k hodnotě zabalené na násobení lze použít více operátorů rozbalení.</span><span class="sxs-lookup"><span data-stu-id="8ec35-184">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="8ec35-185">Příklad:</span><span class="sxs-lookup"><span data-stu-id="8ec35-185">For instance:</span></span>

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

<span data-ttu-id="8ec35-186">Další podrobnosti najdete v oddílu věnovaném [rozbalení výrazů](xref:microsoft.quantum.language.expressions#unwrap-expressions) a [prioritě operátorů](xref:microsoft.quantum.language.expressions#operator-precedence) .</span><span class="sxs-lookup"><span data-stu-id="8ec35-186">Take a look at the section on [unwrap expressions](xref:microsoft.quantum.language.expressions#unwrap-expressions) and [operators precedence](xref:microsoft.quantum.language.expressions#operator-precedence) for more details.</span></span>

<span data-ttu-id="8ec35-187">Hodnoty uživatelsky definovaného typu lze vytvořit voláním odpovídajícího konstruktoru typu:</span><span class="sxs-lookup"><span data-stu-id="8ec35-187">Values of a user defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="8ec35-188">Případně můžete nové hodnoty vytvořit z existujících pomocí [výrazů kopírování a aktualizace](xref:microsoft.quantum.language.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="8ec35-188">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.language.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="8ec35-189">Podobně jako u polí tyto výrazy kopírují všechny hodnoty položky původního výrazu s výjimkou zadaných pojmenovaných položek.</span><span class="sxs-lookup"><span data-stu-id="8ec35-189">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="8ec35-190">Pro tyto hodnoty jsou nastaveny na ty definované na pravé straně výrazu.</span><span class="sxs-lookup"><span data-stu-id="8ec35-190">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="8ec35-191">Jakékoli jiné jazykové konstrukce, jako například [Příkazy Update-a-Reassign](xref:microsoft.quantum.language.statements#update-and-reassign-statement), které jsou k dispozici pro položky pole pro pojmenované položky v uživatelsky definovaných typech.</span><span class="sxs-lookup"><span data-stu-id="8ec35-191">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.language.statements#update-and-reassign-statement), that are available for array items exist for named-items in user defined types as well.</span></span>

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

<span data-ttu-id="8ec35-192">Uživatelsky definované typy lze použít kdekoli v jakémkoli jiném typu.</span><span class="sxs-lookup"><span data-stu-id="8ec35-192">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="8ec35-193">Konkrétně je možné definovat pole uživatelsky definovaného typu a zahrnout uživatelsky definovaný typ jako prvek typu řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="8ec35-193">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="8ec35-194">Není možné vytvářet struktury rekurzivního typu.</span><span class="sxs-lookup"><span data-stu-id="8ec35-194">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="8ec35-195">To znamená, že typ, který definuje uživatelsky definovaný typ, nemůže být typ řazené kolekce členů, který obsahuje prvek uživatelsky definovaného typu.</span><span class="sxs-lookup"><span data-stu-id="8ec35-195">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="8ec35-196">Obecněji, uživatelsky definované typy nemůžou mít na sobě navzájem cyklické závislosti, takže následující sada definic typu by mohla být neplatná:</span><span class="sxs-lookup"><span data-stu-id="8ec35-196">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

<span data-ttu-id="8ec35-197">Kromě poskytování krátkých aliasů pro potenciálně složité typy řazené kolekce členů, což je jedna významná výhoda pro definování takových typů, je, že mohou zdokumentovat záměr konkrétní hodnoty.</span><span class="sxs-lookup"><span data-stu-id="8ec35-197">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="8ec35-198">Návrat na příklad `Complex`, jeden mohl také definovat 2D polární souřadnice jako uživatelsky definovaný typ:</span><span class="sxs-lookup"><span data-stu-id="8ec35-198">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="8ec35-199">I když mají oba `Complex` i `Polar` základní typ `(Double, Double)`, jsou tyto dva typy zcela nekompatibilní v Q #, což minimalizuje riziko náhodného volání komplexní matematické funkce s polárními souřadnicemi a naopak.</span><span class="sxs-lookup"><span data-stu-id="8ec35-199">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="8ec35-200">Tímto způsobem mají uživatelsky definované typy podobnou roli jako záznamy F# například.</span><span class="sxs-lookup"><span data-stu-id="8ec35-200">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


## <a name="operation-and-function-types"></a><span data-ttu-id="8ec35-201">Typy operací a funkcí</span><span class="sxs-lookup"><span data-stu-id="8ec35-201">Operation and Function Types</span></span>

<span data-ttu-id="8ec35-202">_Operace_ Q # je podprogram.</span><span class="sxs-lookup"><span data-stu-id="8ec35-202">A Q# _operation_ is a quantum subroutine.</span></span>
<span data-ttu-id="8ec35-203">To znamená, že se jedná o volanou rutinu, která obsahuje kvantové operace.</span><span class="sxs-lookup"><span data-stu-id="8ec35-203">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="8ec35-204">_Funkce_ Q # je klasická subrutina používaná v rámci algoritmu pro každé z nich.</span><span class="sxs-lookup"><span data-stu-id="8ec35-204">A Q# _function_ is a classical subroutine used within a quantum algorithm.</span></span>
<span data-ttu-id="8ec35-205">Může obsahovat klasický kód, ale žádné nečinnosti.</span><span class="sxs-lookup"><span data-stu-id="8ec35-205">It may contain classical code but no quantum operations.</span></span>
<span data-ttu-id="8ec35-206">Konkrétně funkce nemusí přidělovat ani půjčovat qubits a nesmí volat operace.</span><span class="sxs-lookup"><span data-stu-id="8ec35-206">Specifically, functions may not allocate or borrow qubits, nor may they call operations.</span></span>
<span data-ttu-id="8ec35-207">Je však možné předat jejich operace nebo qubits ke zpracování.</span><span class="sxs-lookup"><span data-stu-id="8ec35-207">It is possible, however, to pass them operations or qubits for processing.</span></span>
<span data-ttu-id="8ec35-208">Funkce jsou tedy zcela deterministické v tom smyslu, že volání se stejnými argumenty budou vždy vracet stejný výsledek.</span><span class="sxs-lookup"><span data-stu-id="8ec35-208">Functions are thus entirely deterministic in the sense that calling them with the same arguments will always produce the same result.</span></span> 

<span data-ttu-id="8ec35-209">Operace a funkce se společně nazývají _volat_.</span><span class="sxs-lookup"><span data-stu-id="8ec35-209">Together, operations and functions are called _callables_.</span></span>  <span data-ttu-id="8ec35-210">Níže vidíte některé [Příklady](#examples) .</span><span class="sxs-lookup"><span data-stu-id="8ec35-210">You can see some [examples](#examples) of these below.</span></span>

<span data-ttu-id="8ec35-211">Všechny volat pomocí Q # se považují za vstupní hodnotu a jako výstup vrátí jedinou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="8ec35-211">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="8ec35-212">Vstupní i výstupní hodnoty mohou být řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="8ec35-212">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="8ec35-213">Je k dispozici, které nemají `Unit`žádného výsledku vrácení.</span><span class="sxs-lookup"><span data-stu-id="8ec35-213">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="8ec35-214">Volat, které nemají žádný vstup, přebírají jako vstup prázdnou řazenou kolekci členů.</span><span class="sxs-lookup"><span data-stu-id="8ec35-214">Callables that have no input take the empty tuple as input.</span></span>

<span data-ttu-id="8ec35-215">Základní typ pro jakékoli vyzkoušení se zapisuje jako `('Tinput => 'Tresult)` nebo `('Tinput -> 'Tresult)`, kde jsou typy `'Tinput` i `'Tresult`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-215">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="8ec35-216">Pro operace se používá první formulář s `=>`. Druhý formulář s `->`pro funkce.</span><span class="sxs-lookup"><span data-stu-id="8ec35-216">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
<span data-ttu-id="8ec35-217">`((Qubit, Pauli) => Result)` například představuje signaturu pro možnou operaci měření s jedním qubit.</span><span class="sxs-lookup"><span data-stu-id="8ec35-217">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>

<span data-ttu-id="8ec35-218">Typy funkcí jsou zcela určeny jejich signaturou.</span><span class="sxs-lookup"><span data-stu-id="8ec35-218">Function types are completely specified by their signature.</span></span>
<span data-ttu-id="8ec35-219">Například funkce, která vypočítá sinus úhlu, by měla typu `(Double -> Double)`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-219">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="8ec35-220">Operace, ale ne funkce – mají určité další _vlastnosti_ , které se vyjadřují jako součást typu operace.</span><span class="sxs-lookup"><span data-stu-id="8ec35-220">Operations—but not functions—have certain additional _characteristics_ that are expressed as part of the operation type.</span></span> <span data-ttu-id="8ec35-221">Tyto vlastnosti zahrnují informace o tom, co funktory operace podporuje.</span><span class="sxs-lookup"><span data-stu-id="8ec35-221">Such characteristics include information about what functors the operation supports.</span></span>
<span data-ttu-id="8ec35-222">Funktory jsou meta operace, které generují specializaci základní operace. viz [funktory](#functors)níže.</span><span class="sxs-lookup"><span data-stu-id="8ec35-222">Functors are meta-operations that generate a specialization of a base operation; see [Functors](#functors), below.</span></span>

<span data-ttu-id="8ec35-223">Typy operací jsou určeny jejich vstupním typem, typem výstupu a jejich charakteristikami.</span><span class="sxs-lookup"><span data-stu-id="8ec35-223">Operation types are specified by the their input type, output type, and their characteristics.</span></span>    
<span data-ttu-id="8ec35-224">Aby bylo možné vyžadovat podporu `Controlled` a/nebo `Adjoint` funktor v typu operace, musíme přidat poznámku, která indikuje odpovídající vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="8ec35-224">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="8ec35-225">`is Ctl` poznámky například označuje, že je operace ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="8ec35-225">An annotation `is Ctl` for example indicates that the operation is controllable.</span></span> <span data-ttu-id="8ec35-226">Pokud chceme vyžadovat, aby operace tohoto typu podporovala `Adjoint` i `Controlled` funktor, můžeme to vyjádřit jako `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-226">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="8ec35-227">Použité charakteristiky operace `Adj` a `Ctl` výhradně řečeno jsou dvě předem definované sady popisků, kde každý popisek označuje konkrétní charakteristiky operace, například podporu konkrétního funktoru.</span><span class="sxs-lookup"><span data-stu-id="8ec35-227">The used operation characteristics `Adj` and `Ctl` strictly speaking are two pre-defined sets of labels, where each label indicates a particular operation characteristics like e.g. support for a particular functor.</span></span>
<span data-ttu-id="8ec35-228">Proto `+` slouží k označení sjednocení těchto dvou sad a `*` se používá k označení průniku, tj. popisky, které jsou pro obě sady společné.</span><span class="sxs-lookup"><span data-stu-id="8ec35-228">Hence, `+` is used to indicate the union of those two sets, and `*` is used to indicate the intersection - i.e. the labels that are common to both sets.</span></span>  

<span data-ttu-id="8ec35-229">Například operace Pauli `X` je typu `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-229">For example, the Pauli `X` operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="8ec35-230">Typ operace, který nepodporuje žádné funktory, je určen samotným typem vstupu a výstupu bez další poznámky.</span><span class="sxs-lookup"><span data-stu-id="8ec35-230">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>


### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="8ec35-231">Typ – parametrizované funkce a operace</span><span class="sxs-lookup"><span data-stu-id="8ec35-231">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="8ec35-232">Typy, které lze volat, mohou obsahovat parametry typu.</span><span class="sxs-lookup"><span data-stu-id="8ec35-232">Callable types may contain type parameters.</span></span>
<span data-ttu-id="8ec35-233">Parametry typu jsou označeny symbolem, který je předponou jedné uvozovky. například `'A` je platným parametrem typu.</span><span class="sxs-lookup"><span data-stu-id="8ec35-233">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>

<span data-ttu-id="8ec35-234">Parametr typu se může v jednom podpisu objevit více než jednou.</span><span class="sxs-lookup"><span data-stu-id="8ec35-234">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="8ec35-235">Například funkce, která použije jinou funkci na každý prvek pole a vrátí shromážděné výsledky, by měly `(('A[], 'A->'A) -> 'A[])`podpisu.</span><span class="sxs-lookup"><span data-stu-id="8ec35-235">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="8ec35-236">Podobně funkce, která vrací složení dvou operací, může mít `((('A=>'B), ('B=>'C)) -> ('A=>'C))`signatury.</span><span class="sxs-lookup"><span data-stu-id="8ec35-236">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="8ec35-237">Při vyvolání volání typu s parametrem typu musí být všechny argumenty, které mají stejný parametr typu, stejného typu.</span><span class="sxs-lookup"><span data-stu-id="8ec35-237">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="8ec35-238">Q # neposkytuje mechanismus pro omezení možných typů, které mohou být nahrazeny parametrem typu.</span><span class="sxs-lookup"><span data-stu-id="8ec35-238">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

### <a name="type-compatibility"></a><span data-ttu-id="8ec35-239">Kompatibilita typů</span><span class="sxs-lookup"><span data-stu-id="8ec35-239">Type Compatibility</span></span>

<span data-ttu-id="8ec35-240">Operaci s dalšími podporovanými funktory se dají použít kdekoli operace s menším počtem funktory, ale je očekáván stejný podpis.</span><span class="sxs-lookup"><span data-stu-id="8ec35-240">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="8ec35-241">Například operace typu `(Qubit => Unit is Adj)` může být použita kdekoli je očekávána operace typu `(Qubit => Unit)`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-241">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="8ec35-242">Q # je kovariantní s ohledem na možné návratové typy: volat, která vrací typ `'A` je kompatibilní s typem, který je možné volat stejným vstupním typem a výsledným typem, který je `'A` kompatibilní.</span><span class="sxs-lookup"><span data-stu-id="8ec35-242">Q# is covariant with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="8ec35-243">Q # je kontravariantní s ohledem na typy vstupu: dá se volat, který přebírá typ `'A` jako vstup je kompatibilní s typem, který se dá volat se stejným typem výsledku a vstupním typem, který je kompatibilní s `'A`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-243">Q# is contravariant with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="8ec35-244">To znamená s ohledem na následující definice:</span><span class="sxs-lookup"><span data-stu-id="8ec35-244">That is, given the following definitions:</span></span>

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

<span data-ttu-id="8ec35-245">platí následující:</span><span class="sxs-lookup"><span data-stu-id="8ec35-245">the following are true:</span></span>

- <span data-ttu-id="8ec35-246">Funkci `ConjugateInvertWith` lze vyvolat pomocí `inner` argumentu buď `Invert`, nebo `ApplyUnitary`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-246">The function `ConjugateInvertWith` may be invoked with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="8ec35-247">Funkci `ConjugateUnitaryWith` lze vyvolat pomocí argumentu `inner` `ApplyUnitary`, ale ne `Invert`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-247">The function `ConjugateUnitaryWith` may be invoked with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="8ec35-248">Z `ConjugateInvertWith`může být vrácena hodnota typu `(Qubit[] => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-248">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ec35-249">Q # 0,3 zavádí značný rozdíl v chování uživatelsky definovaných typů.</span><span class="sxs-lookup"><span data-stu-id="8ec35-249">Q# 0.3 introduces a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="8ec35-250">Uživatelsky definované typy jsou považovány za zabalenou verzi základního typu, nikoli jako podtyp.</span><span class="sxs-lookup"><span data-stu-id="8ec35-250">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="8ec35-251">To znamená, že hodnota uživatelsky definovaného typu není použitelná, pokud je očekávána hodnota základního typu.</span><span class="sxs-lookup"><span data-stu-id="8ec35-251">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>

### <a name="functors"></a><span data-ttu-id="8ec35-252">Funktory</span><span class="sxs-lookup"><span data-stu-id="8ec35-252">Functors</span></span>

<span data-ttu-id="8ec35-253">Funktor v Q # je objekt pro vytváření, který definuje novou operaci z jiné operace.</span><span class="sxs-lookup"><span data-stu-id="8ec35-253">A functor in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="8ec35-254">Funktory má přístup k implementaci základní operace při definování implementace nové operace.</span><span class="sxs-lookup"><span data-stu-id="8ec35-254">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="8ec35-255">Proto může funktory provádět složitější funkce než tradiční funkce vyšší úrovně.</span><span class="sxs-lookup"><span data-stu-id="8ec35-255">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span>

<span data-ttu-id="8ec35-256">Funktory v systému typů Q # není reprezentace.</span><span class="sxs-lookup"><span data-stu-id="8ec35-256">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="8ec35-257">V současné době není možné je navazovat na proměnnou nebo předat jako argumenty.</span><span class="sxs-lookup"><span data-stu-id="8ec35-257">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="8ec35-258">Funktor se používá k tomu, že se použije na operaci a vrátí novou operaci.</span><span class="sxs-lookup"><span data-stu-id="8ec35-258">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="8ec35-259">Například operace, která je výsledkem použití `Adjoint` funktor na operaci `Y`, je zapsána jako `Adjoint Y`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-259">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="8ec35-260">Nová operace se pak může vyvolávat jako jakákoli jiná operace.</span><span class="sxs-lookup"><span data-stu-id="8ec35-260">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="8ec35-261">Proto `Adjoint Y(q1)` pro vytvoření nové operace použít sousedící funktor k operaci `Y` a tuto novou operaci použije na `q1`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-261">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>

<span data-ttu-id="8ec35-262">Podobně `Controlled X(controls, target)` pro vygenerování nové operace použít kontrolované funktor k operaci `X` a tato nová operace se aplikuje na `controls` a `target`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-262">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

<span data-ttu-id="8ec35-263">Dvě standardní funktory ve Q # jsou `Adjoint` a `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-263">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

#### <a name="adjoint"></a><span data-ttu-id="8ec35-264">Sousednít</span><span class="sxs-lookup"><span data-stu-id="8ec35-264">Adjoint</span></span>

<span data-ttu-id="8ec35-265">V případě náročných výpočetních operací je sousední operace operace složitá sdružená operace.</span><span class="sxs-lookup"><span data-stu-id="8ec35-265">In quantum computing, the adjoint of an operation is the complex conjugate transpose of the operation.</span></span>
<span data-ttu-id="8ec35-266">Pro operace, které implementují operátor s jednou jednotkou, je sousední osoba inverzní k operaci.</span><span class="sxs-lookup"><span data-stu-id="8ec35-266">For operations that implement a unitary operator, the adjoint is the inverse of the operation.</span></span>
<span data-ttu-id="8ec35-267">Pro jednoduchou operaci, která pouze vyvolá sekvenci dalších operací v rámci sady qubits, mohou být sousedníci vypočítáni použitím adjoints dílčích operací na stejném qubits v obráceném pořadí.</span><span class="sxs-lookup"><span data-stu-id="8ec35-267">For a simple operation that just invokes a sequence of other unitary operations on a set of qubits, the adjoint may be computed by applying the adjoints of the sub-operations on the same qubits, in the reverse sequence.</span></span>

<span data-ttu-id="8ec35-268">Při použití výrazu operace může být pomocí `Adjoint` funktor vytvořen nový výraz operace.</span><span class="sxs-lookup"><span data-stu-id="8ec35-268">Given an operation expression, a new operation expression may be formed using the `Adjoint` functor.</span></span>
<span data-ttu-id="8ec35-269">Například `Adjoint QFT` určí souseda operace `QFT`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-269">For instance, `Adjoint QFT` designates the adjoint of the `QFT` operation.</span></span>
<span data-ttu-id="8ec35-270">Nová operace má stejný podpis a typ jako základní operace.</span><span class="sxs-lookup"><span data-stu-id="8ec35-270">The new operation has the same signature and type as the base operation.</span></span>
<span data-ttu-id="8ec35-271">Konkrétně Nová operace také umožňuje `Adjoint`a povolí `Controlled` pouze v případě, že došlo k základní operaci.</span><span class="sxs-lookup"><span data-stu-id="8ec35-271">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>

<span data-ttu-id="8ec35-272">Sousední funktor je svou vlastní invertovaná; To znamená, že `Adjoint Adjoint Op` je vždy stejné jako `Op`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-272">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled"></a><span data-ttu-id="8ec35-273">Kontrol</span><span class="sxs-lookup"><span data-stu-id="8ec35-273">Controlled</span></span>

<span data-ttu-id="8ec35-274">Řízená verze operace je nová operace, která efektivně aplikuje základní operaci pouze v případě, že všechny qubits ovládacího prvku jsou v zadaném stavu.</span><span class="sxs-lookup"><span data-stu-id="8ec35-274">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="8ec35-275">Pokud je qubits ovládacího prvku na pozici, pak je základní operace použita v souvislém umístění na příslušné straně.</span><span class="sxs-lookup"><span data-stu-id="8ec35-275">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="8ec35-276">Proto se pro generování entanglement často používají kontrolované operace.</span><span class="sxs-lookup"><span data-stu-id="8ec35-276">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="8ec35-277">V rámci Q # mají řízené verze vždycky převzít pole qubits ovládacího prvku a zadaný stav je vždycky pro všechny kontrolní qubits ve stavu výpočet-(`PauliZ`) `One`, $ \ket{1}$.</span><span class="sxs-lookup"><span data-stu-id="8ec35-277">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
<span data-ttu-id="8ec35-278">Řízení založené na dalších stavech lze dosáhnout použitím příslušné jednotkové operace na qubits ovládacího prvku před řízenou operací a následným použitím inverzních operací po kontrolované operaci.</span><span class="sxs-lookup"><span data-stu-id="8ec35-278">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
<span data-ttu-id="8ec35-279">Například použití operace `X` na qubit ovládacího prvku před a po kontrolované operaci způsobí, že operace bude řídit stav `Zero` ($ \ket{0}$) pro tento qubit; použití operace `H` před a poté bude řídit stav `One` `PauliX`, což je-1 eigenvalue z Pauli X, $ \ket{-} \mathrel{: =} (\ket{0}-\ket{1})/\sqrt{2}$ místo `PauliZ` `One` stavu.</span><span class="sxs-lookup"><span data-stu-id="8ec35-279">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="8ec35-280">Při použití výrazu operace může být pomocí `Controlled` funktor vytvořen nový výraz operace.</span><span class="sxs-lookup"><span data-stu-id="8ec35-280">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="8ec35-281">Signatura nové operace vychází z podpisu původní operace.</span><span class="sxs-lookup"><span data-stu-id="8ec35-281">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="8ec35-282">Typ výsledku je stejný, ale vstupní typ je dvě n-tice s polem qubit, které obsahuje ovládací qubit (y) ovládacího prvku jako první prvek a argumenty původní operace jako druhý prvek.</span><span class="sxs-lookup"><span data-stu-id="8ec35-282">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="8ec35-283">Nová operace podporuje `Controlled`a bude podporovat `Adjoint` pouze v případě, že původní operace proběhla.</span><span class="sxs-lookup"><span data-stu-id="8ec35-283">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="8ec35-284">V případě, že původní operace trvala pouze jeden argument, budou se sem přicházet ekvivalenty singleton řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="8ec35-284">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="8ec35-285">`Controlled X` je například řízená verze `X` operace.</span><span class="sxs-lookup"><span data-stu-id="8ec35-285">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span>
<span data-ttu-id="8ec35-286">`X` má `(Qubit => Unit is Adj + Ctl)`typu, takže `Controlled X` má typ `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; vzhledem k rovnosti řazené kolekce členů singleton je to stejné jako `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-286">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="8ec35-287">Pokud základní operace trvala několik argumentů, nezapomeňte do závorek uzavřít odpovídající argumenty kontrolované verze operace v závorkách, aby je bylo možné převést na řazenou kolekci členů.</span><span class="sxs-lookup"><span data-stu-id="8ec35-287">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="8ec35-288">`Controlled Rz` je například řízená verze `Rz` operace.</span><span class="sxs-lookup"><span data-stu-id="8ec35-288">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span>
<span data-ttu-id="8ec35-289">`Rz` má `((Double, Qubit) => Unit is Adj + Ctl)`typu, takže `Controlled Rz` má typ `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-289">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="8ec35-290">Proto by `Controlled Rz(controls, (0.1, target))` bylo platné vyvolání `Controlled Rz` (Poznačte si závorky kolem `0.1, target`).</span><span class="sxs-lookup"><span data-stu-id="8ec35-290">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="8ec35-291">Jako další příklad můžete `CNOT(control, target)` implementovat jako `Controlled X([control], target)`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-291">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="8ec35-292">Pokud by cíl měl být řízen 2 qubits řízení (CCNOT), můžeme použít příkaz `Controlled X([control1, control2], target)`.</span><span class="sxs-lookup"><span data-stu-id="8ec35-292">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

### <a name="examples"></a><span data-ttu-id="8ec35-293">Příklady</span><span class="sxs-lookup"><span data-stu-id="8ec35-293">Examples</span></span>

<span data-ttu-id="8ec35-294">Tento příklad operace Q # přichází z ukázky [měření](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) .</span><span class="sxs-lookup"><span data-stu-id="8ec35-294">This example of a Q# operation comes from the [Measurement](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) sample.</span></span> <span data-ttu-id="8ec35-295">V rámci operací můžeme přidělovat qubits a využívat operace na těchto qubits, jako jsou `H` a `X`:</span><span class="sxs-lookup"><span data-stu-id="8ec35-295">Within operations, we can allocate qubits and use quantum operations on those qubits such as `H` and `X`:</span></span>

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit() : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit
            set result = M(qubit);      // Measure the qubit
            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

<span data-ttu-id="8ec35-296">Tento příklad funkce pochází z ukázky [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="8ec35-296">This example of a function comes from the [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) sample.</span></span> <span data-ttu-id="8ec35-297">Obsahuje čistě klasický kód.</span><span class="sxs-lookup"><span data-stu-id="8ec35-297">It contains purely classical code.</span></span> <span data-ttu-id="8ec35-298">Můžete vidět, že na rozdíl od výše uvedeného příkladu nejsou přiděleny žádné qubits a nepoužívají se žádné operace.</span><span class="sxs-lookup"><span data-stu-id="8ec35-298">You can see that, unlike the example above, no qubits are allocated, and no quantum operations are used.</span></span>

```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function PointwiseProduct(left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

<span data-ttu-id="8ec35-299">Je také možné předat funkci qubits ke zpracování, jako v tomto příkladu z ukázky [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) .</span><span class="sxs-lookup"><span data-stu-id="8ec35-299">It is also possible for a function to be passed qubits for processing, as in this example from the [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) sample.</span></span> <span data-ttu-id="8ec35-300">Qubits se předávají do funkce a používají se ke zpracování, i když se v žádném okamžiku nezměnily stavy qubit.</span><span class="sxs-lookup"><span data-stu-id="8ec35-300">Qubits are passed to the function and used for processing, although at no point are the qubit states themselves modified.</span></span>

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates(
    qubits : Qubit[], 
    masks : MCMTMask[]) 
: MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```
