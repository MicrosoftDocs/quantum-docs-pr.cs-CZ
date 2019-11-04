---
title: Výrazy | Microsoft Docs
description: Výrazy
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 09d493df4e1178fee1f7a5946cfda2f411111006
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185201"
---
# <a name="expressions"></a><span data-ttu-id="95e6a-103">Výrazy</span><span class="sxs-lookup"><span data-stu-id="95e6a-103">Expressions</span></span>

## <a name="grouping"></a><span data-ttu-id="95e6a-104">Sloučení</span><span class="sxs-lookup"><span data-stu-id="95e6a-104">Grouping</span></span>

<span data-ttu-id="95e6a-105">V případě libovolného výrazu je stejný výraz uzavřený v závorkách výraz stejného typu.</span><span class="sxs-lookup"><span data-stu-id="95e6a-105">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="95e6a-106">`(7)` je například výraz `Int`, `([1,2,3])` je výraz typu `Int`s a `((1,2))` je výraz typu `(Int, Int)`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-106">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="95e6a-107">Ekvivalenci mezi jednoduchými hodnotami a řazenými kolekcemi členů s jedním prvkem popsanými v [modelu typu](xref:microsoft.quantum.language.type-model#tuple-types) odebere nejednoznačnost mezi `(6)` jako skupinu a `(6)` jako řazenou kolekci členů s jedním prvkem.</span><span class="sxs-lookup"><span data-stu-id="95e6a-107">The equivalence between simple values and single-element tuples described in [the type model](xref:microsoft.quantum.language.type-model#tuple-types) removes the ambiguity between `(6)` as a group and `(6)` as a single-element tuple.</span></span>

## <a name="symbols"></a><span data-ttu-id="95e6a-108">Symboly</span><span class="sxs-lookup"><span data-stu-id="95e6a-108">Symbols</span></span>

<span data-ttu-id="95e6a-109">Název vázaného symbolu nebo přiřazený k hodnotě typu `'T` je výraz typu `'T`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-109">The name of a symbol bound or assigned to a value of type `'T` is an expression of type `'T`.</span></span>
<span data-ttu-id="95e6a-110">Například pokud je symbol `count` svázán s celočíselnou hodnotou `5`, pak `count` je celočíselný výraz.</span><span class="sxs-lookup"><span data-stu-id="95e6a-110">For instance, if the symbol `count` is bound to the integer value `5`, then `count` is an integer expression.</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="95e6a-111">Číselné výrazy</span><span class="sxs-lookup"><span data-stu-id="95e6a-111">Numeric Expressions</span></span>

<span data-ttu-id="95e6a-112">Číselné výrazy jsou výrazy typu `Int`, `BigInt`nebo `Double`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-112">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="95e6a-113">To znamená, že jsou buď celá čísla, nebo čísla s plovoucí desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="95e6a-113">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="95e6a-114">literály `Int` v Q # jsou identické s celočíselnými literály v C#, s tím rozdílem, že nejsou vyžadovány žádné koncové čárky "l" nebo "l" (nebo povoleny).</span><span class="sxs-lookup"><span data-stu-id="95e6a-114">`Int` literals in Q# are identical to integer literals in C#, except that no trailing "l" or "L" is required (or allowed).</span></span>
<span data-ttu-id="95e6a-115">V uvedeném pořadí jsou podporována šestnáctková a binární celá čísla s předponou 0x a 0b.</span><span class="sxs-lookup"><span data-stu-id="95e6a-115">Hexadecimal and binary integers are supported with a "0x" and "0b" prefix respectively.</span></span>

<span data-ttu-id="95e6a-116">literály `BigInt` v Q # jsou identické s velkými celočíselnými řetězci v .NET s koncovým řetězcem "l" nebo "L".</span><span class="sxs-lookup"><span data-stu-id="95e6a-116">`BigInt` literals in Q# are identical to big integer strings in .NET, with a trailing "l" or "L".</span></span>
<span data-ttu-id="95e6a-117">Předpona "0x" je podporována hexadecimálními velkými čísly.</span><span class="sxs-lookup"><span data-stu-id="95e6a-117">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="95e6a-118">Následující jsou tedy všechna platná použití `BigInt` literály:</span><span class="sxs-lookup"><span data-stu-id="95e6a-118">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="95e6a-119">literály `Double` v Q # jsou identické s dvojitými literály v C#, s tím rozdílem, že nejsou vyžadovány žádné koncové znaky "d" nebo "d" (nebo povoleny).</span><span class="sxs-lookup"><span data-stu-id="95e6a-119">`Double` literals in Q# are identical to double literals in C#, except that no trailing "d" or "D" is required (or allowed).</span></span>

<span data-ttu-id="95e6a-120">Vzhledem k výrazu pole libovolného typu elementu může být výraz `Int` vytvořen pomocí předdefinované funkce `Length` a výraz pole uzavřený v závorkách, `(` a `)`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-120">Given an array expression of any element type, an `Int` expression may be formed using the `Length` built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="95e6a-121">Například pokud je `a` svázána s polem, `Length(a)` je celočíselný výraz.</span><span class="sxs-lookup"><span data-stu-id="95e6a-121">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="95e6a-122">Je-li `b` pole celých čísel, `Int[][]`a `Length(b)` je počet dílčích polí v `b`a `Length(b[1])` je počet celých čísel ve druhém dílčím poli v `b`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-122">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="95e6a-123">Pro vytvoření nového číselného výrazu lze použít binární operátory `+`, `-`, `*`a `/`, které jsou zadány dvěma číselnými výrazy stejného typu.</span><span class="sxs-lookup"><span data-stu-id="95e6a-123">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="95e6a-124">Typ nového výrazu bude stejný jako u typů výrazů prvků.</span><span class="sxs-lookup"><span data-stu-id="95e6a-124">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="95e6a-125">Zadaným dvěma celočíselnými výrazy, binární operátor `^` (napájení) lze použít k vytvoření nového celočíselného výrazu.</span><span class="sxs-lookup"><span data-stu-id="95e6a-125">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="95e6a-126">Podobně `^` lze použít se dvěma dvojitými výrazy k vytvoření nového dvojitého výrazu.</span><span class="sxs-lookup"><span data-stu-id="95e6a-126">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="95e6a-127">Nakonec `^` možné použít s velkým celým číslem na levé straně a celé číslo na pravé straně k vytvoření nového výrazu Big Integer.</span><span class="sxs-lookup"><span data-stu-id="95e6a-127">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="95e6a-128">V takovém případě se druhý parametr musí vejít do 32 bitů; v takovém případě se vyvolá Běhová chyba.</span><span class="sxs-lookup"><span data-stu-id="95e6a-128">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="95e6a-129">Předané dva celočíselné nebo velké celočíselné výrazy mohou být tvořeny výrazem `%` (modulo), `&&&` (bitových a), `|||` (bitových nebo) nebo `^^^` (bitových operátorů XOR).</span><span class="sxs-lookup"><span data-stu-id="95e6a-129">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="95e6a-130">Pro vytvoření nového výrazu stejného typu, který je na levé straně, se dá použít buď výraz celého čísla nebo Big Integer, a na pravé straně výraz typu Integer vpravo, `<<<` (aritmetický levý SHIFT) nebo `>>>` (aritmetický posun). vyjádření.</span><span class="sxs-lookup"><span data-stu-id="95e6a-130">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="95e6a-131">Druhý parametr (velikost posunu) pro operaci posunu musí být větší nebo roven nule. chování pro záporné hodnoty posunutí není definováno.</span><span class="sxs-lookup"><span data-stu-id="95e6a-131">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="95e6a-132">Velikost SHIFT pro buď operaci posunutí musí být také do 32 bitů. v takovém případě se vyvolá Běhová chyba.</span><span class="sxs-lookup"><span data-stu-id="95e6a-132">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="95e6a-133">Pokud číslo, které má být posunuto, je celé číslo, hodnota posunutí je interpretována `mod 64`; To znamená, že posun 1 a Shift 65 mají stejný účinek.</span><span class="sxs-lookup"><span data-stu-id="95e6a-133">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="95e6a-134">Pro celočíselné i velké celočíselné hodnoty jsou posunuty aritmetické operace.</span><span class="sxs-lookup"><span data-stu-id="95e6a-134">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="95e6a-135">Posunutí záporné hodnoty doleva nebo doprava bude mít za následek záporné číslo.</span><span class="sxs-lookup"><span data-stu-id="95e6a-135">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="95e6a-136">To znamená, že posun jednoho kroku doleva nebo doprava je přesně stejný jako násobení nebo dělení 2, v uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="95e6a-136">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="95e6a-137">Celočíselné dělení a celočíselné zbytky se řídí stejným chováním jako C#záporná čísla.</span><span class="sxs-lookup"><span data-stu-id="95e6a-137">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="95e6a-138">To znamená, že `a % b` vždycky budou stejné znaménko jako `a`a `b * (a / b) + a % b` se vždycky rovná `a`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-138">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="95e6a-139">Například:</span><span class="sxs-lookup"><span data-stu-id="95e6a-139">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="95e6a-140">5</span><span class="sxs-lookup"><span data-stu-id="95e6a-140">5</span></span> | <span data-ttu-id="95e6a-141">2</span><span class="sxs-lookup"><span data-stu-id="95e6a-141">2</span></span> | <span data-ttu-id="95e6a-142">2</span><span class="sxs-lookup"><span data-stu-id="95e6a-142">2</span></span> | <span data-ttu-id="95e6a-143">1\. místo</span><span class="sxs-lookup"><span data-stu-id="95e6a-143">1</span></span>
 <span data-ttu-id="95e6a-144">5</span><span class="sxs-lookup"><span data-stu-id="95e6a-144">5</span></span> | <span data-ttu-id="95e6a-145">– 2</span><span class="sxs-lookup"><span data-stu-id="95e6a-145">-2</span></span> | <span data-ttu-id="95e6a-146">– 2</span><span class="sxs-lookup"><span data-stu-id="95e6a-146">-2</span></span> | <span data-ttu-id="95e6a-147">1\. místo</span><span class="sxs-lookup"><span data-stu-id="95e6a-147">1</span></span>
 <span data-ttu-id="95e6a-148">-5</span><span class="sxs-lookup"><span data-stu-id="95e6a-148">-5</span></span> | <span data-ttu-id="95e6a-149">2</span><span class="sxs-lookup"><span data-stu-id="95e6a-149">2</span></span> | <span data-ttu-id="95e6a-150">– 2</span><span class="sxs-lookup"><span data-stu-id="95e6a-150">-2</span></span> | <span data-ttu-id="95e6a-151">– 1</span><span class="sxs-lookup"><span data-stu-id="95e6a-151">-1</span></span>
 <span data-ttu-id="95e6a-152">-5</span><span class="sxs-lookup"><span data-stu-id="95e6a-152">-5</span></span> | <span data-ttu-id="95e6a-153">– 2</span><span class="sxs-lookup"><span data-stu-id="95e6a-153">-2</span></span> | <span data-ttu-id="95e6a-154">2</span><span class="sxs-lookup"><span data-stu-id="95e6a-154">2</span></span> | <span data-ttu-id="95e6a-155">– 1</span><span class="sxs-lookup"><span data-stu-id="95e6a-155">-1</span></span>

<span data-ttu-id="95e6a-156">Dělení velkých celých čísel a Modulus funguje stejným způsobem.</span><span class="sxs-lookup"><span data-stu-id="95e6a-156">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="95e6a-157">V případě libovolného číselného výrazu může být nový výraz vytvořen pomocí operátoru `-` unární.</span><span class="sxs-lookup"><span data-stu-id="95e6a-157">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="95e6a-158">Nový výraz bude stejného typu jako výraz prvku.</span><span class="sxs-lookup"><span data-stu-id="95e6a-158">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="95e6a-159">S ohledem na libovolný celočíselný nebo velký celočíselný výraz může být nový výraz stejného typu vytvořen pomocí unárního operátoru `~~~` (bitový doplněk).</span><span class="sxs-lookup"><span data-stu-id="95e6a-159">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="95e6a-160">Logické výrazy</span><span class="sxs-lookup"><span data-stu-id="95e6a-160">Boolean Expressions</span></span>

<span data-ttu-id="95e6a-161">Dvě `Bool` hodnoty literálu jsou `true` a `false`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-161">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="95e6a-162">Vzhledem k jakýmkoli dvěma výrazům stejného primitivního typu lze použít binární operátory `==` a `!=` k vytvoření výrazu `Bool`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-162">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="95e6a-163">Výraz bude true, pokud jsou dva výrazy (odp.) stejné.</span><span class="sxs-lookup"><span data-stu-id="95e6a-163">The expression will be true if the two expressions are (resp. are not) equal.</span></span>

<span data-ttu-id="95e6a-164">Hodnoty uživatelsky definovaných typů nelze porovnat, lze porovnat pouze jejich hodnoty.</span><span class="sxs-lookup"><span data-stu-id="95e6a-164">Values of user-defined types may not be compared, only their values can be compared.</span></span> <span data-ttu-id="95e6a-165">Například:</span><span class="sxs-lookup"><span data-stu-id="95e6a-165">For example,</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="95e6a-166">Porovnání rovnosti pro hodnoty `Qubit` je rovnost identity; To znamená, zda dva výrazy identifikují stejný qubit.</span><span class="sxs-lookup"><span data-stu-id="95e6a-166">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="95e6a-167">Stav obou qubits se neshoduje, nepoužívá se, neměří ani nemění pomocí tohoto porovnání.</span><span class="sxs-lookup"><span data-stu-id="95e6a-167">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="95e6a-168">Porovnání rovnosti pro hodnoty `Double` může být zavádějící z důvodu zaoblení efektů.</span><span class="sxs-lookup"><span data-stu-id="95e6a-168">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="95e6a-169">`49.0 * (1.0/49.0) != 1.0`například.</span><span class="sxs-lookup"><span data-stu-id="95e6a-169">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="95e6a-170">V případě jakýchkoli dvou číselných výrazů lze použít binární operátory `>`, `<`, `>=`a `<=` k vytvoření nového logického výrazu, který má hodnotu true, pokud je první výraz v tomto pořadí větší než, menší než, větší než nebo rovno nebo je menší nebo rovno druhému výrazu.</span><span class="sxs-lookup"><span data-stu-id="95e6a-170">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="95e6a-171">V případě jakýchkoli dvou logických výrazů lze použít binární operátory `and` a `or` k vytvoření nového logického výrazu, který má hodnotu true, pokud jsou oba výrazy (odp. buď nebo oba) pravdivé.</span><span class="sxs-lookup"><span data-stu-id="95e6a-171">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="95e6a-172">S ohledem na jakýkoliv logický výraz lze použít unární operátor `not` k vytvoření nového logického výrazu, který je true, pokud je výraz prvku false.</span><span class="sxs-lookup"><span data-stu-id="95e6a-172">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="95e6a-173">Řetězcové výrazy</span><span class="sxs-lookup"><span data-stu-id="95e6a-173">String Expressions</span></span>

<span data-ttu-id="95e6a-174">Q # povoluje použití řetězců v příkazu `fail` a ve funkci `Log` Standard.</span><span class="sxs-lookup"><span data-stu-id="95e6a-174">Q# allows strings to be used in the `fail` statement and the `Log` standard function.</span></span>

<span data-ttu-id="95e6a-175">Řetězce v Q # jsou buď literály nebo interpolované řetězce.</span><span class="sxs-lookup"><span data-stu-id="95e6a-175">Strings in Q# are either literals or interpolated strings.</span></span>
<span data-ttu-id="95e6a-176">Řetězcové literály jsou podobně jako jednoduché řetězcové literály ve většině jazyků: sekvence znaků Unicode uzavřená v dvojitých uvozovkách, `"`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-176">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="95e6a-177">Uvnitř řetězce je možné znak zpětného lomítka `\` použít k úniku znaku dvojité uvozovky a vložení nového řádku jako `\n`, návratu na začátek jako `\r`a kartu jako `\t`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-177">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="95e6a-178">Např.:</span><span class="sxs-lookup"><span data-stu-id="95e6a-178">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```

<span data-ttu-id="95e6a-179">Syntaxe Q # pro interpolování řetězců je podmnožinou syntaxe C# 7,0; Q # nepodporuje doslovné (Multi-line) interpolované řetězce.</span><span class="sxs-lookup"><span data-stu-id="95e6a-179">The Q# syntax for string interpolations is a subset of the C# 7.0 syntax; Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="95e6a-180">Viz [*interpolované řetězce*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) pro C# syntaxi.</span><span class="sxs-lookup"><span data-stu-id="95e6a-180">See [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) for the C# syntax.</span></span>

<span data-ttu-id="95e6a-181">Výrazy uvnitř interpolované řetězce následují syntaxe Q #, nikoli C# syntaxe.</span><span class="sxs-lookup"><span data-stu-id="95e6a-181">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>
<span data-ttu-id="95e6a-182">Libovolný platný výraz Q # se může objevit v interpolované řetězci.</span><span class="sxs-lookup"><span data-stu-id="95e6a-182">Any valid Q# expression may appear in an interpolated string.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="95e6a-183">Výrazy qubit</span><span class="sxs-lookup"><span data-stu-id="95e6a-183">Qubit Expressions</span></span>

<span data-ttu-id="95e6a-184">Jedinými `Qubit` výrazy jsou symboly, které jsou vázány na `Qubit` hodnoty nebo prvky pole `Qubit` polí.</span><span class="sxs-lookup"><span data-stu-id="95e6a-184">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="95e6a-185">Neexistují žádné `Qubit` literály.</span><span class="sxs-lookup"><span data-stu-id="95e6a-185">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="95e6a-186">Výrazy Pauli</span><span class="sxs-lookup"><span data-stu-id="95e6a-186">Pauli Expressions</span></span>

<span data-ttu-id="95e6a-187">Čtyři `Pauli` hodnoty, `PauliI`, `PauliX`, `PauliY`a `PauliZ`, jsou všechny platné výrazy `Pauli`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-187">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="95e6a-188">Kromě toho jediné `Pauli` výrazy jsou symboly, které jsou vázány na `Pauli` hodnoty nebo prvky pole `Pauli` polí.</span><span class="sxs-lookup"><span data-stu-id="95e6a-188">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="95e6a-189">Výsledné výrazy</span><span class="sxs-lookup"><span data-stu-id="95e6a-189">Result Expressions</span></span>

<span data-ttu-id="95e6a-190">Dvě `Result` hodnoty, `One` a `Zero`, jsou platné `Result` výrazy.</span><span class="sxs-lookup"><span data-stu-id="95e6a-190">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="95e6a-191">Kromě toho jediné `Result` výrazy jsou symboly, které jsou vázány na `Result` hodnoty nebo prvky pole `Result` polí.</span><span class="sxs-lookup"><span data-stu-id="95e6a-191">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="95e6a-192">Konkrétně Všimněte si, že `One` není stejná jako celé číslo `1`a mezi nimi není přímý převod.</span><span class="sxs-lookup"><span data-stu-id="95e6a-192">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="95e6a-193">Totéž platí pro `Zero` a `0`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-193">The same is true for `Zero` and `0`.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="95e6a-194">Výrazy rozsahu</span><span class="sxs-lookup"><span data-stu-id="95e6a-194">Range Expressions</span></span>

<span data-ttu-id="95e6a-195">Pro všechny tři `Int` výrazy `start`, `step`a `stop`je `start .. step .. stop` výraz rozsahu, jehož prvním prvkem je `start`, druhý prvek je `start+step`, třetí prvek je `start+step+step`atd., dokud nebude předán `stop`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-195">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="95e6a-196">Rozsah může být prázdný, pokud je například `step` kladný a `stop < start`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-196">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="95e6a-197">Poslední prvek rozsahu bude `stop`, pokud rozdíl mezi `start` a `stop` je integrální násobek `step`; To znamená, že rozsah je zahrnut na obou koncích.</span><span class="sxs-lookup"><span data-stu-id="95e6a-197">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="95e6a-198">Pro všechny dva `Int` výrazy `start` a `stop`je `start .. stop` výraz rozsahu, který se rovná `start .. 1 .. stop`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-198">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="95e6a-199">Všimněte si, že implicitní `step` je + 1, i když `stop` je menší než `start`; v takovém případě je rozsah prázdný.</span><span class="sxs-lookup"><span data-stu-id="95e6a-199">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="95e6a-200">Mezi příklady oblastí patří:</span><span class="sxs-lookup"><span data-stu-id="95e6a-200">Some example ranges are:</span></span>

- <span data-ttu-id="95e6a-201">`1..3` je rozsah 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="95e6a-201">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="95e6a-202">`2..2..5` je rozsah 2, 4.</span><span class="sxs-lookup"><span data-stu-id="95e6a-202">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="95e6a-203">`2..2..6` je rozsah 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="95e6a-203">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="95e6a-204">`6..-2..2` je rozsah 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="95e6a-204">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="95e6a-205">`2..1` je prázdný rozsah.</span><span class="sxs-lookup"><span data-stu-id="95e6a-205">`2..1` is the empty range.</span></span>
- <span data-ttu-id="95e6a-206">`2..6..7` je rozsah 2.</span><span class="sxs-lookup"><span data-stu-id="95e6a-206">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="95e6a-207">`2..2..1` je prázdný rozsah.</span><span class="sxs-lookup"><span data-stu-id="95e6a-207">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="95e6a-208">`1..-1..2` je prázdný rozsah.</span><span class="sxs-lookup"><span data-stu-id="95e6a-208">`1..-1..2` is the empty range.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="95e6a-209">Výrazy, které se mají volat</span><span class="sxs-lookup"><span data-stu-id="95e6a-209">Callable Expressions</span></span>

<span data-ttu-id="95e6a-210">Volatelné literály je název operace nebo funkce definované v oboru kompilace.</span><span class="sxs-lookup"><span data-stu-id="95e6a-210">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="95e6a-211">Například `X` je literál operace, který odkazuje na standardní knihovnu `X` operace a `Message` je literál funkce, který odkazuje na `Message` funkci standardní knihovny.</span><span class="sxs-lookup"><span data-stu-id="95e6a-211">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="95e6a-212">Pokud operace podporuje `Adjoint` funktor, `Adjoint op` je výraz operace.</span><span class="sxs-lookup"><span data-stu-id="95e6a-212">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="95e6a-213">Podobně pokud operace podporuje `Controlled` funktor, `Controlled op` je výraz operace.</span><span class="sxs-lookup"><span data-stu-id="95e6a-213">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="95e6a-214">Typy těchto výrazů jsou zadány v [funktory](xref:microsoft.quantum.language.type-model#functors).</span><span class="sxs-lookup"><span data-stu-id="95e6a-214">The types of these expressions are specified in [Functors](xref:microsoft.quantum.language.type-model#functors).</span></span>

<span data-ttu-id="95e6a-215">Funktory (`Adjoint` a `Controlled`) sváže více než všechny ostatní operátory, s výjimkou operátoru Unwrap `!` a pole Indexing `[]`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-215">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[]`.</span></span>
<span data-ttu-id="95e6a-216">Níže jsou uvedené všechny právní a za předpokladu, že operace podporují funktory, který se používá:</span><span class="sxs-lookup"><span data-stu-id="95e6a-216">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

<span data-ttu-id="95e6a-217">Dá se použít jako hodnota, která se dá použít jako hodnota, řekněme, že se přiřadí proměnné nebo přejdou na jinou možnou volat.</span><span class="sxs-lookup"><span data-stu-id="95e6a-217">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="95e6a-218">V tomto případě musí být v případě, že je možné volat parametry typu, zadány jako součást hodnoty, kterou lze volat.</span><span class="sxs-lookup"><span data-stu-id="95e6a-218">In this case, if the callable has type parameters, they must be provided as part of the callable value.</span></span>
<span data-ttu-id="95e6a-219">Hodnota, která se nedá volat, nemůže mít nespecifikované parametry typu.</span><span class="sxs-lookup"><span data-stu-id="95e6a-219">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="95e6a-220">Pokud `Fun` například funkce s podpisovým `'T1->Unit`:</span><span class="sxs-lookup"><span data-stu-id="95e6a-220">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="95e6a-221">Volat výrazy vyvolání</span><span class="sxs-lookup"><span data-stu-id="95e6a-221">Callable Invocation Expressions</span></span>

<span data-ttu-id="95e6a-222">Vzhledem k volání (operace nebo funkce) a výrazu řazené kolekce členů na vstupním typu signatury, která se dá volat, může být výraz vyvolání vytvořen připojením výrazu řazené kolekce členů k výrazu, který je k volání.</span><span class="sxs-lookup"><span data-stu-id="95e6a-222">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="95e6a-223">Typ výrazu vyvolání je výstupní typ signatury, kterou chcete volat.</span><span class="sxs-lookup"><span data-stu-id="95e6a-223">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="95e6a-224">Například pokud `Op` je operace s podpisovým `((Int, Qubit) => Double)`, `Op(3, qubit1)` je výraz typu `Double`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-224">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="95e6a-225">Podobně, pokud je `Sin` funkce s podpisovým `(Double -> Double)`, `Sin(0.1)` je výraz typu `Double`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-225">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="95e6a-226">Nakonec, pokud je `Builder` funkce se signaturou `(Int -> (Int -> Int))`, `Builder(3)` je funkce z do int.</span><span class="sxs-lookup"><span data-stu-id="95e6a-226">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="95e6a-227">Vyvolání výsledku výrazu s možností volání vyžaduje navíc pár závorek kolem volání.</span><span class="sxs-lookup"><span data-stu-id="95e6a-227">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="95e6a-228">Proto pokud chcete vyvolat výsledek volání `Builder` z předchozího odstavce, správná syntaxe je:</span><span class="sxs-lookup"><span data-stu-id="95e6a-228">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="95e6a-229">Při vyvolání typu, který se dá volat, se skutečné parametry typu můžou zadat v lomených závorkách `<` a `>` po možném výrazu.</span><span class="sxs-lookup"><span data-stu-id="95e6a-229">When invoking a type-parameterized callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="95e6a-230">To je obvykle zbytečné, protože kompilátor Q # odvodí skutečné typy.</span><span class="sxs-lookup"><span data-stu-id="95e6a-230">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="95e6a-231">Je vyžadován pro částečnou aplikaci (viz níže), pokud je argument typu bez parametrů ponechán neurčen.</span><span class="sxs-lookup"><span data-stu-id="95e6a-231">It is required for partial application (see below) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="95e6a-232">Někdy je to užitečné i při předávání operací s různými funktory, které jsou schopné volat.</span><span class="sxs-lookup"><span data-stu-id="95e6a-232">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="95e6a-233">Pokud má například `Func` `('T1, 'T2, 'T1) -> 'T2`signatury, `Op1` a `Op2` mají podpis `(Qubit[] => Unit is Adj)`a `Op3` má `(Qubit[] => Unit)`signatury, aby vyvolal `Func` s `Op1` jako první argument, `Op2` jako druhý a `Op3` jako třetí:</span><span class="sxs-lookup"><span data-stu-id="95e6a-233">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="95e6a-234">Specifikace typu je povinná, protože `Op3` a `Op1` mají různé typy, takže kompilátor bude považovat za dvojznačný bez specifikace.</span><span class="sxs-lookup"><span data-stu-id="95e6a-234">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>

### <a name="partial-application"></a><span data-ttu-id="95e6a-235">Částečná aplikace</span><span class="sxs-lookup"><span data-stu-id="95e6a-235">Partial Application</span></span>

<span data-ttu-id="95e6a-236">S ohledem na výraz, který lze volat, lze vytvořit novou voláním podmnožiny argumentů, které lze volat.</span><span class="sxs-lookup"><span data-stu-id="95e6a-236">Given a callable expression, a new callable may be created by providing a subset of the arguments to the callable.</span></span>
<span data-ttu-id="95e6a-237">Tato metoda se nazývá _Částečná aplikace_.</span><span class="sxs-lookup"><span data-stu-id="95e6a-237">This is called _partial application_.</span></span>

<span data-ttu-id="95e6a-238">V Q # je částečně aplikovaná metoda volání vyjádřena zapsáním normálního výrazu vyvolání, ale pomocí podtržítka, `_`pro neurčené argumenty.</span><span class="sxs-lookup"><span data-stu-id="95e6a-238">In Q#, a partially applied callable is expressed by writing a normal invocation expression, but using an underscore, `_`, for the unspecified arguments.</span></span>
<span data-ttu-id="95e6a-239">Výsledná volat má stejný typ výsledku jako základní volat a stejné specializace pro operace.</span><span class="sxs-lookup"><span data-stu-id="95e6a-239">The resulting callable has the same result type as the base callable, and the same specializations for operations.</span></span>
<span data-ttu-id="95e6a-240">Vstupní typ částečné aplikace je jednoduše původní typ, ze kterého byly odebrány zadané argumenty.</span><span class="sxs-lookup"><span data-stu-id="95e6a-240">The input type of the partial application is simply the original type with the specified arguments removed.</span></span>

<span data-ttu-id="95e6a-241">Pokud se proměnlivá proměnná předává jako zadaný argument při vytváření částečné aplikace, použije se aktuální hodnota proměnné.</span><span class="sxs-lookup"><span data-stu-id="95e6a-241">If a mutable variable is passed as a specified argument when creating a partial application, the current value of the variable is used.</span></span>
<span data-ttu-id="95e6a-242">Změna hodnoty proměnné následně nebude mít vliv na částečnou aplikaci.</span><span class="sxs-lookup"><span data-stu-id="95e6a-242">Changing the value of the variable afterward will not impact the partial application.</span></span>

<span data-ttu-id="95e6a-243">Například pokud `Op` má typ `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span><span class="sxs-lookup"><span data-stu-id="95e6a-243">For example, if `Op` has type `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span></span>

- <span data-ttu-id="95e6a-244">`Op(5,(_,_))` má `(((Qubit,Qubit), Double) => Unit is Adj)`typu, a proto má `Op(5,_)`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-244">`Op(5,(_,_))` has type `(((Qubit,Qubit), Double) => Unit is Adj)`, and so has `Op(5,_)`.</span></span>
- <span data-ttu-id="95e6a-245">`Op(_,(_,1.0))` má `((Int, (Qubit,Qubit)) => Unit is Adj)`typu.</span><span class="sxs-lookup"><span data-stu-id="95e6a-245">`Op(_,(_,1.0))` has type `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span></span>
- <span data-ttu-id="95e6a-246">`Op(_,((q1,q2),_))` má `((Int,Double) => Unit is Adj)`typu.</span><span class="sxs-lookup"><span data-stu-id="95e6a-246">`Op(_,((q1,q2),_))` has type `((Int,Double) => Unit is Adj)`.</span></span>
   <span data-ttu-id="95e6a-247">Všimněte si, že se tady používá ekvivalenci typu Singleton v řazené kolekci členů.</span><span class="sxs-lookup"><span data-stu-id="95e6a-247">Note that we have applied singleton tuple equivalence here.</span></span>

<span data-ttu-id="95e6a-248">Pokud má částečně použité volání metody typu, které kompilátor nemůže odvodit, musí být k dispozici na webu vyvolání.</span><span class="sxs-lookup"><span data-stu-id="95e6a-248">If the partially-applied callable has type parameters that cannot be inferred by the compiler, they must be provided at the invocation site.</span></span>
<span data-ttu-id="95e6a-249">Částečná aplikace nemůže mít nespecifikované parametry typu.</span><span class="sxs-lookup"><span data-stu-id="95e6a-249">The partial application cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="95e6a-250">Například pokud `Op` má typ `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span><span class="sxs-lookup"><span data-stu-id="95e6a-250">For example, if `Op` has type `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span></span>

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a><span data-ttu-id="95e6a-251">Rekurze</span><span class="sxs-lookup"><span data-stu-id="95e6a-251">Recursion</span></span>

<span data-ttu-id="95e6a-252">Je možné, že volat v Q # můžou být přímo nebo nepřímo rekurzivní.</span><span class="sxs-lookup"><span data-stu-id="95e6a-252">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="95e6a-253">To znamená, že operace nebo funkce může volat sám sebe nebo může volat jinou metodu, kterou přímo nebo nepřímo volá operaci, kterou lze volat.</span><span class="sxs-lookup"><span data-stu-id="95e6a-253">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="95e6a-254">Existují dva důležité komentáře k použití rekurze, ale:</span><span class="sxs-lookup"><span data-stu-id="95e6a-254">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="95e6a-255">Použití rekurze v operacích může být v konfliktu s některými optimalizacemi.</span><span class="sxs-lookup"><span data-stu-id="95e6a-255">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="95e6a-256">To může mít zásadní vliv na dobu provádění algoritmu.</span><span class="sxs-lookup"><span data-stu-id="95e6a-256">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="95e6a-257">Při provádění na skutečném zařízení ve formátu paměti může být prostor zásobníku omezený a důkladná rekurze může vést k chybě za běhu.</span><span class="sxs-lookup"><span data-stu-id="95e6a-257">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="95e6a-258">Konkrétně kompilátor Q # a modul runtime neidentifikují a optimalizují koncovou rekurzi.</span><span class="sxs-lookup"><span data-stu-id="95e6a-258">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="95e6a-259">Výrazy řazené kolekce členů</span><span class="sxs-lookup"><span data-stu-id="95e6a-259">Tuple Expressions</span></span>

<span data-ttu-id="95e6a-260">Literál řazené kolekce členů je sekvence výrazů prvků příslušného typu oddělených čárkami, které jsou uzavřeny v `(` a `)`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-260">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="95e6a-261">Například `(1, One)` je výraz `(Int, Result)`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-261">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="95e6a-262">Kromě literálů jsou jedinými výrazy řazené kolekce členů symboly, které jsou vázány na hodnoty řazené kolekce členů, prvky pole řazené kolekce členů a volání, která vrací řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="95e6a-262">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="95e6a-263">Výrazy uživatelsky definovaného typu</span><span class="sxs-lookup"><span data-stu-id="95e6a-263">User-Defined Type Expressions</span></span>

<span data-ttu-id="95e6a-264">Literál uživatelsky definovaného typu se skládá z názvu typu následovaného literálem řazené kolekce členů základního typu řazené kolekce členů typu.</span><span class="sxs-lookup"><span data-stu-id="95e6a-264">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="95e6a-265">Například pokud `IntPair` je uživatelem definovaný typ založený na `(Int, Int)`, pak `IntPair(2,3)` být platným literálem tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="95e6a-265">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2,3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="95e6a-266">Kromě literálů jsou jedinými výrazy uživatelsky definovaného typu symboly, které jsou vázány na hodnoty daného typu, prvky pole polí daného typu a volání, která vrací tento typ.</span><span class="sxs-lookup"><span data-stu-id="95e6a-266">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="95e6a-267">Rozbalit výrazy</span><span class="sxs-lookup"><span data-stu-id="95e6a-267">Unwrap Expressions</span></span>

<span data-ttu-id="95e6a-268">V Q # je operátorem rozbalení znak koncového vykřičníku `!`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-268">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="95e6a-269">Například pokud `IntPair` je uživatelem definovaný typ s podkladovým typem `(Int, Int)`a `s` byla proměnná s hodnotou `IntPair(2,3)`, `s!` `(2,3)`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-269">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2,3)`, then `s!` would be `(2,3)`.</span></span>

<span data-ttu-id="95e6a-270">Pro uživatelsky definované typy definované v jiných uživatelsky definovaných typech.</span><span class="sxs-lookup"><span data-stu-id="95e6a-270">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="95e6a-271">operátor rozbalení může být opakován; například `s!!` označuje dvakrát nezabalenou hodnotu `s`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-271">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="95e6a-272">Proto pokud `WrappedPair` je uživatelem definovaný typ s podkladovým typem `IntPair`a `t` je proměnná s hodnotou `WrappedPair(IntPair(1,2))`, `t!!` `(1,2)`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-272">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="95e6a-273">Operátor `!` má vyšší prioritu než všechny ostatní operátory kromě `[]` pro indexování pole a vytváření řezů.</span><span class="sxs-lookup"><span data-stu-id="95e6a-273">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="95e6a-274">umístění vazby `!` a `[]`. To znamená, `a[i]![3]` by měly být čteny jako `((a[i])!)[3]`: přebírat `i`"th elementu `a`, rozbalíte ho a pak získáme třetí prvek nezabalené hodnoty (který musí být pole).</span><span class="sxs-lookup"><span data-stu-id="95e6a-274">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="95e6a-275">Priorita operátoru `!` má jeden dopad, který nemusí být zřejmý.</span><span class="sxs-lookup"><span data-stu-id="95e6a-275">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="95e6a-276">Vrátí-li funkce nebo operace hodnotu, která je poté nezabalena, musí být volání funkce nebo operace uzavřena v závorkách, aby se argumenty řazené kolekce členů navázaly na volání, nikoli na rozbalení.</span><span class="sxs-lookup"><span data-stu-id="95e6a-276">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="95e6a-277">Například:</span><span class="sxs-lookup"><span data-stu-id="95e6a-277">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="95e6a-278">Výrazy Array</span><span class="sxs-lookup"><span data-stu-id="95e6a-278">Array Expressions</span></span>

<span data-ttu-id="95e6a-279">Literál pole je sekvence jednoho nebo více výrazů prvků, které jsou odděleny čárkami a uzavřeny v `[` a `]`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-279">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="95e6a-280">Všechny elementy musí být kompatibilní se stejným typem.</span><span class="sxs-lookup"><span data-stu-id="95e6a-280">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="95e6a-281">Je-li běžný typ prvku typ operace nebo funkce, všechny prvky musí mít stejné vstupní a výstupní typy.</span><span class="sxs-lookup"><span data-stu-id="95e6a-281">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="95e6a-282">Typ elementu pole bude podporovat všechny funktory, které jsou podporovány všemi prvky.</span><span class="sxs-lookup"><span data-stu-id="95e6a-282">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="95e6a-283">Například pokud jsou `Qubit[] => Unit``Op1`, `Op2`a `Op3`, ale `Op1` podporuje `Adjoint`, `Op2` podporuje `Controlled`a `Op3` podporuje obojí:</span><span class="sxs-lookup"><span data-stu-id="95e6a-283">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="95e6a-284">`[Op1, Op2]` je pole `(Qubit[] => Unit)`ch operací.</span><span class="sxs-lookup"><span data-stu-id="95e6a-284">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="95e6a-285">`[Op1, Op3]` je pole `(Qubit[] => Unit is Adj)`ch operací.</span><span class="sxs-lookup"><span data-stu-id="95e6a-285">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="95e6a-286">`[Op2, Op3]` je pole `(Qubit[] => Unit is Ctl)`ch operací.</span><span class="sxs-lookup"><span data-stu-id="95e6a-286">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="95e6a-287">Prázdné literály pole, `[]`, nejsou povoleny.</span><span class="sxs-lookup"><span data-stu-id="95e6a-287">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="95e6a-288">Místo toho, aby používaly `new ★[0]`, kde `★` jako zástupný symbol pro vhodný typ, umožňuje vytvořit požadované pole s nulovou délkou.</span><span class="sxs-lookup"><span data-stu-id="95e6a-288">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="95e6a-289">Zadáním dvou polí stejného typu lze pomocí binárního operátoru `+` vytvořit nové pole, které je zřetězením dvou polí.</span><span class="sxs-lookup"><span data-stu-id="95e6a-289">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="95e6a-290">Například `[1,2,3] + [4,5,6]` je `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-290">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="95e6a-291">Vytvoření pole</span><span class="sxs-lookup"><span data-stu-id="95e6a-291">Array Creation</span></span>

<span data-ttu-id="95e6a-292">Když je zadán typ a výraz `Int`, operátor `new` lze použít k přidělení nového pole dané velikosti.</span><span class="sxs-lookup"><span data-stu-id="95e6a-292">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="95e6a-293">`new Int[i+1]` by například přidělila nové pole `Int` s `i+1` elementy.</span><span class="sxs-lookup"><span data-stu-id="95e6a-293">For instance, `new Int[i+1]` would allocate a new `Int` array with `i+1` elements.</span></span>

<span data-ttu-id="95e6a-294">Prvky nového pole jsou inicializovány na výchozí hodnotu závislou na typu.</span><span class="sxs-lookup"><span data-stu-id="95e6a-294">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="95e6a-295">Ve většině případů se jedná o nějakou odchylku nuly.</span><span class="sxs-lookup"><span data-stu-id="95e6a-295">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="95e6a-296">Pro qubits a volat, které jsou odkazy na entity, neexistuje přiměřená výchozí hodnota.</span><span class="sxs-lookup"><span data-stu-id="95e6a-296">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="95e6a-297">Proto pro tyto typy je výchozí hodnota neplatný odkaz, který nelze použít, aniž by došlo k chybě za běhu.</span><span class="sxs-lookup"><span data-stu-id="95e6a-297">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="95e6a-298">To se podobá odkazu s hodnotou null v jazycích, C# jako je například nebo Java.</span><span class="sxs-lookup"><span data-stu-id="95e6a-298">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="95e6a-299">Pole obsahující qubits nebo volat musí být správně inicializována s jinými než výchozími hodnotami, aby bylo možné jejich prvky bezpečně použít.</span><span class="sxs-lookup"><span data-stu-id="95e6a-299">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="95e6a-300">Vhodné inicializační rutiny lze nalézt v <xref:microsoft.quantum.arrays>.</span><span class="sxs-lookup"><span data-stu-id="95e6a-300">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="95e6a-301">Výchozí hodnoty pro každý typ jsou:</span><span class="sxs-lookup"><span data-stu-id="95e6a-301">The default values for each type are:</span></span>

<span data-ttu-id="95e6a-302">Typ</span><span class="sxs-lookup"><span data-stu-id="95e6a-302">Type</span></span> | <span data-ttu-id="95e6a-303">Výchozí</span><span class="sxs-lookup"><span data-stu-id="95e6a-303">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="95e6a-304">_Neplatný qubit_</span><span class="sxs-lookup"><span data-stu-id="95e6a-304">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="95e6a-305">Prázdný rozsah `1..1..0`</span><span class="sxs-lookup"><span data-stu-id="95e6a-305">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="95e6a-306">_Neplatný volat_</span><span class="sxs-lookup"><span data-stu-id="95e6a-306">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="95e6a-307">Typy řazené kolekce členů jsou inicializovány elementem po prvku.</span><span class="sxs-lookup"><span data-stu-id="95e6a-307">Tuple types are initialized element-by-element.</span></span>


### <a name="jagged-arrays"></a><span data-ttu-id="95e6a-308">Vícenásobná pole</span><span class="sxs-lookup"><span data-stu-id="95e6a-308">Jagged Arrays</span></span>

<span data-ttu-id="95e6a-309">Vícenásobné pole, někdy označované jako "pole polí", je pole, jehož prvky jsou pole.</span><span class="sxs-lookup"><span data-stu-id="95e6a-309">A jagged array, sometimes called an "array of arrays", is an array whose elements are arrays.</span></span> <span data-ttu-id="95e6a-310">Prvky vícenásobného pole mohou mít různé velikosti.</span><span class="sxs-lookup"><span data-stu-id="95e6a-310">The elements of a jagged array can be of different sizes.</span></span> <span data-ttu-id="95e6a-311">Následující příklad ukazuje, jak deklarovat a inicializovat vícenásobné pole reprezentující tabulku násobení.</span><span class="sxs-lookup"><span data-stu-id="95e6a-311">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

```qsharp
let N = 4;
mutable multiplicationTable = new Int[][N];
for (i in 1..N) {

    mutable row = new Int[i];
    for (j in 1..i) {
        set row w/= j-1 <- i * j;
    }
    set multiplicationTable w/= i-1 <- row;
}
```


### <a name="array-slices"></a><span data-ttu-id="95e6a-312">Řezy pole</span><span class="sxs-lookup"><span data-stu-id="95e6a-312">Array Slices</span></span>

<span data-ttu-id="95e6a-313">S ohledem na výraz pole a výraz `Range` může být výraz New vytvořen pomocí operátoru `[` a `]`ho průřezu pole.</span><span class="sxs-lookup"><span data-stu-id="95e6a-313">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="95e6a-314">Nový výraz bude stejný jako typ pole a bude obsahovat položky pole indexované prvky `Range`v pořadí definovaném `Range`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-314">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="95e6a-315">Například pokud je `a` svázán s polem `Double`s, pak `a[3..-1..0]` je výraz `Double[]`, který obsahuje první čtyři prvky `a`, ale v obráceném pořadí, jak jsou uvedeny v `a`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-315">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="95e6a-316">Pokud je `Range` prázdné, bude výsledný řez pole nulovou délkou.</span><span class="sxs-lookup"><span data-stu-id="95e6a-316">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="95e6a-317">Pokud výraz pole není jednoduchý identifikátor, musí být uzavřen závorky, aby bylo možné vytvořit řezy.</span><span class="sxs-lookup"><span data-stu-id="95e6a-317">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="95e6a-318">Například pokud `a` a `b` jsou pole `Int`s, řez z zřetězení by byl vyjádřen jako:</span><span class="sxs-lookup"><span data-stu-id="95e6a-318">For instance, if `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

<span data-ttu-id="95e6a-319">Všechna pole v Q # jsou založená na nule.</span><span class="sxs-lookup"><span data-stu-id="95e6a-319">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="95e6a-320">To znamená, že první prvek pole `a` je vždy `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-320">That is, the first element of an array `a` is always `a[0]`.</span></span>

<span data-ttu-id="95e6a-321">Od naší verze 0,8 podporujeme kontextové výrazy pro průřezy rozsahu.</span><span class="sxs-lookup"><span data-stu-id="95e6a-321">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="95e6a-322">Konkrétně je možné vynechat počáteční a koncové hodnoty rozsahu v kontextu výrazu průřezu rozsahu.</span><span class="sxs-lookup"><span data-stu-id="95e6a-322">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="95e6a-323">V takovém případě kompilátor použije následující pravidla k odvodit zamýšlené oddělovače pro daný rozsah.</span><span class="sxs-lookup"><span data-stu-id="95e6a-323">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="95e6a-324">Pokud je třeba počáteční hodnota rozsahu vynechána, pak odvozená počáteční hodnota.</span><span class="sxs-lookup"><span data-stu-id="95e6a-324">For example, if the range start value is omitted, then the inferred start value</span></span> 
- <span data-ttu-id="95e6a-325">je nula, pokud není zadán žádný krok, nebo je zadaný krok kladný a</span><span class="sxs-lookup"><span data-stu-id="95e6a-325">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="95e6a-326">je délka pole v průřezu minus jedna, pokud je zadaný krok záporný.</span><span class="sxs-lookup"><span data-stu-id="95e6a-326">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="95e6a-327">Pokud je hodnota konec rozsahu vynechána, pak odvozená koncová hodnota</span><span class="sxs-lookup"><span data-stu-id="95e6a-327">If the range end value is omitted, then the inferred end value</span></span> 
- <span data-ttu-id="95e6a-328">je délka pole řezu minus jedna, pokud není zadán žádný krok, nebo je zadaný krok kladný a</span><span class="sxs-lookup"><span data-stu-id="95e6a-328">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="95e6a-329">je nula, pokud je zadaný krok záporný.</span><span class="sxs-lookup"><span data-stu-id="95e6a-329">is zero if the specified step is negative.</span></span> 

```qsharp
let arr = [1,2,3,4,5,6];
let slice1  = arr[3...];      // slice1 is [4,5,6];
let slice2  = arr[0..2...];   // slice2 is [1,3,5];
let slice3  = arr[...2];      // slice3 is [1,2,3];
let slice4  = arr[...2..3];   // slice4 is [1,3];
let slice5  = arr[...2...];   // slice5 is [1,3,5];
let slice7  = arr[4..-2...];  // slice7 is [5,3,1];
let slice8  = arr[...-1..3];  // slice8 is [6,5,4];
let slice9  = arr[...-1...];  // slice9 is [6,5,4,3,2,1];
let slice10 = arr[...];       // slice10 is [1,2,3,4,5,6];
```

## <a name="array-element-expressions"></a><span data-ttu-id="95e6a-330">Výrazy prvků pole</span><span class="sxs-lookup"><span data-stu-id="95e6a-330">Array Element Expressions</span></span>

<span data-ttu-id="95e6a-331">S ohledem na výraz pole a výraz `Int` může být výraz New vytvořen pomocí operátoru `[` a `]` elementu pole.</span><span class="sxs-lookup"><span data-stu-id="95e6a-331">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="95e6a-332">Nový výraz bude stejného typu jako typ prvku pole.</span><span class="sxs-lookup"><span data-stu-id="95e6a-332">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="95e6a-333">Pokud je například `a` svázán s polem `Double`s, pak `a[4]` je výraz `Double`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-333">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="95e6a-334">Pokud výraz pole není jednoduchý identifikátor, musí být uzavřen závorky, aby bylo možné vybrat prvek.</span><span class="sxs-lookup"><span data-stu-id="95e6a-334">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to select an element.</span></span>
<span data-ttu-id="95e6a-335">Například pokud `a` a `b` jsou pole `Int`s, prvek ze zřetězení by byl vyjádřen jako:</span><span class="sxs-lookup"><span data-stu-id="95e6a-335">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[13]
```

<span data-ttu-id="95e6a-336">Všechna pole v Q # jsou založená na nule.</span><span class="sxs-lookup"><span data-stu-id="95e6a-336">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="95e6a-337">To znamená, že první prvek pole `a` je vždy `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-337">That is, the first element of an array `a` is always `a[0]`.</span></span>


## <a name="copy-and-update-expressions"></a><span data-ttu-id="95e6a-338">Výrazy kopírování a aktualizace</span><span class="sxs-lookup"><span data-stu-id="95e6a-338">Copy-and-Update Expressions</span></span>

<span data-ttu-id="95e6a-339">Nová pole je možné vytvořit z existujících pomocí výrazů kopírování a aktualizace.</span><span class="sxs-lookup"><span data-stu-id="95e6a-339">New arrays can be created from existing ones via copy-and-update expressions.</span></span>
<span data-ttu-id="95e6a-340">Výraz kopírování a aktualizace je výrazem `expression1 w/ expression2 <- expression3`formuláře, kde `expression1` musí být typu `T[]` pro určitý typ `T`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-340">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span> <span data-ttu-id="95e6a-341">Druhý `expression2` definuje indexy prvků, které mají být upraveny v porovnání s polem v `expression1` a musí být buď typu `Int`, nebo typu `Range`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-341">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span> <span data-ttu-id="95e6a-342">Pokud je `expression2` typu `Int`, `expression3` musí být typu `T`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-342">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="95e6a-343">Pokud je `expression2` typu `Range`, `expression3` musí být typu `T[]`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-343">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="95e6a-344">Výraz kopie a aktualizace `arr w/ idx <- value` vytvoří nové pole se všemi prvky nastavenými na odpovídající prvek v `arr`, s výjimkou elementů v `idx`, které jsou nastaveny na jeden nebo s v `value`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-344">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="95e6a-345">Pokud například `arr` obsahuje `[0,1,2,3]`pole, pak</span><span class="sxs-lookup"><span data-stu-id="95e6a-345">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="95e6a-346">`arr w/ 0 <- 10` je pole `[10,1,2,3]`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-346">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="95e6a-347">`arr w/ 2 <- 10` je pole `[0,1,10,3]`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-347">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="95e6a-348">`arr w/ 0..2..3 <- [10,12]` je pole `[10,1,12,3]`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-348">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

<span data-ttu-id="95e6a-349">Podobné výrazy existují pro pojmenované položky v uživatelsky definovaných typech.</span><span class="sxs-lookup"><span data-stu-id="95e6a-349">Similar expressions exist for named items in user-defined types.</span></span> <span data-ttu-id="95e6a-350">Zvažte například typ.</span><span class="sxs-lookup"><span data-stu-id="95e6a-350">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="95e6a-351">Pokud `c` obsahuje hodnotu typu `Complex(1.,-1.)`a pak `c w/ Re <- 0.` je výraz typu `Complex`, který je vyhodnocen jako `Complex(0.,-1.)`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-351">If `c` contains the value of type `Complex(1.,-1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0.,-1.)`.</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="95e6a-352">Podmíněné výrazy</span><span class="sxs-lookup"><span data-stu-id="95e6a-352">Conditional Expressions</span></span>

<span data-ttu-id="95e6a-353">Vzhledem k dvěma dalším výrazům stejného typu a logickému výrazu může být podmíněný výraz vytvořen pomocí otazníku `?` a svislým pruhem `|`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-353">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="95e6a-354">`a==b ? c | d`například.</span><span class="sxs-lookup"><span data-stu-id="95e6a-354">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="95e6a-355">V tomto příkladu bude hodnota podmíněného výrazu `c`, pokud má `a==b` hodnotu true a `d`, pokud má hodnotu false.</span><span class="sxs-lookup"><span data-stu-id="95e6a-355">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

<span data-ttu-id="95e6a-356">Tyto dva výrazy mohou být vyhodnoceny na operace, které mají stejné vstupy a výstupy, ale podporují různé funktory.</span><span class="sxs-lookup"><span data-stu-id="95e6a-356">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="95e6a-357">V tomto případě typ podmíněného výrazu je operace s těmito vstupy a výstupy, které podporují všechny funktory Podporované oběma výrazy.</span><span class="sxs-lookup"><span data-stu-id="95e6a-357">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="95e6a-358">Například pokud jsou `Qubit[]=>Unit``Op1`, `Op2`a `Op3`, ale `Op1` podporuje `Adjoint`, `Op2` podporuje `Controlled`a `Op3` podporuje obojí:</span><span class="sxs-lookup"><span data-stu-id="95e6a-358">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="95e6a-359">`flag ? Op1 | Op2` je operace `(Qubit[] => Unit)`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-359">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="95e6a-360">`flag ? Op1 | Op3` je operace `(Qubit[] => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-360">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="95e6a-361">`flag ? Op2 | Op3` je operace `(Qubit[] => Unit is Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-361">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="95e6a-362">Pokud jeden ze dvou možných výsledných výrazů zahrnuje volání funkce nebo operace, bude toto volání provedeno pouze v případě, že je výsledkem ta, která bude hodnotou volání.</span><span class="sxs-lookup"><span data-stu-id="95e6a-362">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="95e6a-363">Například v případě `a==b ? C(qs) | D(qs)`, pokud je `a==b` true, bude vyvolána operace `C`, a pokud je hodnota false, bude vyvolána pouze `D`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-363">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="95e6a-364">To se podobá krátkodobému okruhu v jiných jazycích.</span><span class="sxs-lookup"><span data-stu-id="95e6a-364">This is similar to short-circuiting in other languages.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="95e6a-365">Priorita operátorů</span><span class="sxs-lookup"><span data-stu-id="95e6a-365">Operator Precedence</span></span>

<span data-ttu-id="95e6a-366">Všechny binární operátory jsou asociativní zprava, s výjimkou `^`.</span><span class="sxs-lookup"><span data-stu-id="95e6a-366">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="95e6a-367">Hranaté závorky, `[` a `]`pro průřezy pole a indexování se sváže před jakýmkoli operátorem.</span><span class="sxs-lookup"><span data-stu-id="95e6a-367">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="95e6a-368">Funktory `Adjoint` a vazba `Controlled` po vyřazení pole, ale před všemi ostatními operátory.</span><span class="sxs-lookup"><span data-stu-id="95e6a-368">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="95e6a-369">Kulaté závorky pro operace a volání funkce se také vážou před libovolným operátorem, ale po vyřazení a funktory pole.</span><span class="sxs-lookup"><span data-stu-id="95e6a-369">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="95e6a-370">Operátory v pořadí podle priority, od nejvyšších po nejnižší:</span><span class="sxs-lookup"><span data-stu-id="95e6a-370">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="95e6a-371">Operátor</span><span class="sxs-lookup"><span data-stu-id="95e6a-371">Operator</span></span> | <span data-ttu-id="95e6a-372">Aritou</span><span class="sxs-lookup"><span data-stu-id="95e6a-372">Arity</span></span> | <span data-ttu-id="95e6a-373">Popis</span><span class="sxs-lookup"><span data-stu-id="95e6a-373">Description</span></span> | <span data-ttu-id="95e6a-374">Typy operandů</span><span class="sxs-lookup"><span data-stu-id="95e6a-374">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="95e6a-375">koncový `!`</span><span class="sxs-lookup"><span data-stu-id="95e6a-375">trailing `!`</span></span> | <span data-ttu-id="95e6a-376">Unární</span><span class="sxs-lookup"><span data-stu-id="95e6a-376">Unary</span></span> | <span data-ttu-id="95e6a-377">Rozbalení</span><span class="sxs-lookup"><span data-stu-id="95e6a-377">Unwrap</span></span> | <span data-ttu-id="95e6a-378">Libovolný uživatelsky definovaný typ</span><span class="sxs-lookup"><span data-stu-id="95e6a-378">Any user-defined type</span></span>
 <span data-ttu-id="95e6a-379">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="95e6a-379">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="95e6a-380">Unární</span><span class="sxs-lookup"><span data-stu-id="95e6a-380">Unary</span></span> | <span data-ttu-id="95e6a-381">Numerický negativní, bitový doplněk, logická negace</span><span class="sxs-lookup"><span data-stu-id="95e6a-381">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="95e6a-382">`Int`, `BigInt` nebo `Double` pro `-`, `Int` nebo `BigInt` pro `~~~``Bool`</span><span class="sxs-lookup"><span data-stu-id="95e6a-382">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="95e6a-383">Tvaru</span><span class="sxs-lookup"><span data-stu-id="95e6a-383">Binary</span></span> | <span data-ttu-id="95e6a-384">Celočíselný výkon</span><span class="sxs-lookup"><span data-stu-id="95e6a-384">Integer power</span></span> | <span data-ttu-id="95e6a-385">`Int` nebo `BigInt` pro základní `Int` pro exponent</span><span class="sxs-lookup"><span data-stu-id="95e6a-385">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="95e6a-386">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="95e6a-386">`/`, `*`, `%`</span></span> | <span data-ttu-id="95e6a-387">Tvaru</span><span class="sxs-lookup"><span data-stu-id="95e6a-387">Binary</span></span> | <span data-ttu-id="95e6a-388">Dělení, násobení, celočíselné zbytky</span><span class="sxs-lookup"><span data-stu-id="95e6a-388">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="95e6a-389">`Int`, `BigInt` nebo `Double` pro `/` a `*``Int` nebo `BigInt` pro `%`</span><span class="sxs-lookup"><span data-stu-id="95e6a-389">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="95e6a-390">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="95e6a-390">`+`, `-`</span></span> | <span data-ttu-id="95e6a-391">Tvaru</span><span class="sxs-lookup"><span data-stu-id="95e6a-391">Binary</span></span> | <span data-ttu-id="95e6a-392">Sčítání nebo řetězce a zřetězení polí, odčítání</span><span class="sxs-lookup"><span data-stu-id="95e6a-392">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="95e6a-393">`Int`, `BigInt` nebo `Double`, navíc `String` nebo libovolný typ pole pro `+`</span><span class="sxs-lookup"><span data-stu-id="95e6a-393">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="95e6a-394">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="95e6a-394">`<<<`, `>>>`</span></span> | <span data-ttu-id="95e6a-395">Tvaru</span><span class="sxs-lookup"><span data-stu-id="95e6a-395">Binary</span></span> | <span data-ttu-id="95e6a-396">Levý SHIFT, posun doprava</span><span class="sxs-lookup"><span data-stu-id="95e6a-396">Left shift, right shift</span></span> | <span data-ttu-id="95e6a-397">`Int` nebo `BigInt`</span><span class="sxs-lookup"><span data-stu-id="95e6a-397">`Int` or `BigInt`</span></span>
 <span data-ttu-id="95e6a-398">`<`, `<=`, `>``>=`</span><span class="sxs-lookup"><span data-stu-id="95e6a-398">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="95e6a-399">Tvaru</span><span class="sxs-lookup"><span data-stu-id="95e6a-399">Binary</span></span> | <span data-ttu-id="95e6a-400">Méně než, méně než nebo-rovno, větší než, větší než nebo rovno, větší než nebo rovno</span><span class="sxs-lookup"><span data-stu-id="95e6a-400">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="95e6a-401">`Int`, `BigInt` nebo `Double`</span><span class="sxs-lookup"><span data-stu-id="95e6a-401">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="95e6a-402">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="95e6a-402">`==`, `!=`</span></span> | <span data-ttu-id="95e6a-403">Tvaru</span><span class="sxs-lookup"><span data-stu-id="95e6a-403">Binary</span></span> | <span data-ttu-id="95e6a-404">rovná se, nerovná se porovnávání</span><span class="sxs-lookup"><span data-stu-id="95e6a-404">equal, not-equal comparisons</span></span> | <span data-ttu-id="95e6a-405">jakýkoli primitivní typ</span><span class="sxs-lookup"><span data-stu-id="95e6a-405">any primitive type</span></span>
 `&&&` | <span data-ttu-id="95e6a-406">Tvaru</span><span class="sxs-lookup"><span data-stu-id="95e6a-406">Binary</span></span> | <span data-ttu-id="95e6a-407">Bitový operátor AND</span><span class="sxs-lookup"><span data-stu-id="95e6a-407">Bitwise AND</span></span> | <span data-ttu-id="95e6a-408">`Int` nebo `BigInt`</span><span class="sxs-lookup"><span data-stu-id="95e6a-408">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="95e6a-409">Tvaru</span><span class="sxs-lookup"><span data-stu-id="95e6a-409">Binary</span></span> | <span data-ttu-id="95e6a-410">Bitový operátor XOR</span><span class="sxs-lookup"><span data-stu-id="95e6a-410">Bitwise XOR</span></span> | <span data-ttu-id="95e6a-411">`Int` nebo `BigInt`</span><span class="sxs-lookup"><span data-stu-id="95e6a-411">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="95e6a-412">Tvaru</span><span class="sxs-lookup"><span data-stu-id="95e6a-412">Binary</span></span> | <span data-ttu-id="95e6a-413">Bitový operátor OR</span><span class="sxs-lookup"><span data-stu-id="95e6a-413">Bitwise OR</span></span> | <span data-ttu-id="95e6a-414">`Int` nebo `BigInt`</span><span class="sxs-lookup"><span data-stu-id="95e6a-414">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="95e6a-415">Tvaru</span><span class="sxs-lookup"><span data-stu-id="95e6a-415">Binary</span></span> | <span data-ttu-id="95e6a-416">Logický operátor AND</span><span class="sxs-lookup"><span data-stu-id="95e6a-416">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="95e6a-417">Tvaru</span><span class="sxs-lookup"><span data-stu-id="95e6a-417">Binary</span></span> | <span data-ttu-id="95e6a-418">Logický operátor OR</span><span class="sxs-lookup"><span data-stu-id="95e6a-418">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="95e6a-419">Binární/Ternární</span><span class="sxs-lookup"><span data-stu-id="95e6a-419">Binary/Ternary</span></span> | <span data-ttu-id="95e6a-420">Operátor rozsahu</span><span class="sxs-lookup"><span data-stu-id="95e6a-420">Range operator</span></span> | `Int`
 <span data-ttu-id="95e6a-421">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="95e6a-421">`?` `|`</span></span> | <span data-ttu-id="95e6a-422">Ternární</span><span class="sxs-lookup"><span data-stu-id="95e6a-422">Ternary</span></span> | <span data-ttu-id="95e6a-423">Podmíněné</span><span class="sxs-lookup"><span data-stu-id="95e6a-423">Conditional</span></span> | <span data-ttu-id="95e6a-424">`Bool` na levé straně</span><span class="sxs-lookup"><span data-stu-id="95e6a-424">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="95e6a-425">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="95e6a-425">`w/` `<-`</span></span> | <span data-ttu-id="95e6a-426">Ternární</span><span class="sxs-lookup"><span data-stu-id="95e6a-426">Ternary</span></span> | <span data-ttu-id="95e6a-427">Kopírování a aktualizace</span><span class="sxs-lookup"><span data-stu-id="95e6a-427">Copy-and-update</span></span> | <span data-ttu-id="95e6a-428">viz [výrazy pro kopírování a aktualizaci](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="95e6a-428">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>
