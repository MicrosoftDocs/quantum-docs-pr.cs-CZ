---
title: Výrazy vQ#
description: Pochopte, jak zadat, odkazovat a kombinovat konstanty, proměnné, operátory, operace a funkce jako výrazy v Q# .
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
no-loc:
- Q#
- $$v
ms.openlocfilehash: b6cc97dfee05dc843e213e84f17043714a8a9656
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869609"
---
# <a name="expressions-in-no-locq"></a><span data-ttu-id="8098b-103">Výrazy vQ#</span><span class="sxs-lookup"><span data-stu-id="8098b-103">Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="8098b-104">Číselné výrazy</span><span class="sxs-lookup"><span data-stu-id="8098b-104">Numeric Expressions</span></span>

<span data-ttu-id="8098b-105">Číselné výrazy jsou výrazy typu `Int` , `BigInt` nebo `Double` .</span><span class="sxs-lookup"><span data-stu-id="8098b-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="8098b-106">To znamená, že jsou buď celá čísla, nebo čísla s plovoucí desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="8098b-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="8098b-107">`Int`literály v Q# jsou zapsány jako sekvence číslic.</span><span class="sxs-lookup"><span data-stu-id="8098b-107">`Int` literals in Q# are written as a sequence of digits.</span></span>
<span data-ttu-id="8098b-108">Šestnáctková a binární celá čísla jsou podporována a zapsána `0x` `0b` předponou a v uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="8098b-108">Hexadecimal and binary integers are supported and written with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="8098b-109">`BigInt`literály v Q# mají koncovou `l` nebo `L` příponu.</span><span class="sxs-lookup"><span data-stu-id="8098b-109">`BigInt` literals in Q# have a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="8098b-110">Hexadecimální Velká celá čísla jsou podporována a napsána předponou "0x".</span><span class="sxs-lookup"><span data-stu-id="8098b-110">Hexadecimal big integers are supported and written with a "0x" prefix.</span></span>
<span data-ttu-id="8098b-111">Následující jsou tedy všechna platná použití `BigInt` literálů:</span><span class="sxs-lookup"><span data-stu-id="8098b-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="8098b-112">`Double`literály v jsou čísla s plovoucí desetinnou čárkou Q# napsaná pomocí desítkových číslic.</span><span class="sxs-lookup"><span data-stu-id="8098b-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="8098b-113">Je možné je zapsat s desetinnou čárkou nebo bez nich, `.` nebo exponenciální částí označenou písmenem "e" nebo "e" (po které jsou platné pouze možné záporné znaménko a desítkové číslice).</span><span class="sxs-lookup"><span data-stu-id="8098b-113">They can be written with or without a decimal point, `.`, or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="8098b-114">Níže jsou uvedené platné `Double` literály: `0.0` , `1.2e5` , `1e-5` .</span><span class="sxs-lookup"><span data-stu-id="8098b-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="8098b-115">Vzhledem k výrazu pole libovolného typu elementu můžete vytvořit `Int` výraz pomocí [`Length`](xref:microsoft.quantum.core.length) předdefinované funkce a výraz pole uzavřený v závorkách.</span><span class="sxs-lookup"><span data-stu-id="8098b-115">Given an array expression of any element type, you can form an `Int` expression using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses.</span></span>
<span data-ttu-id="8098b-116">Například pokud `a` je svázána s polem, pak `Length(a)` je celočíselný výraz.</span><span class="sxs-lookup"><span data-stu-id="8098b-116">For example, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="8098b-117">Pokud `b` je pole polí celých čísel, `Int[][]` , pak `Length(b)` je počet dílčích polí v a `b` `Length(b[1])` je počet celých čísel ve druhém dílčím poli v `b` .</span><span class="sxs-lookup"><span data-stu-id="8098b-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="8098b-118">Zadané dva číselné výrazy stejného typu, binární operátory `+` ,, `-` `*` a `/` mohou být použity k vytvoření nového číselného výrazu.</span><span class="sxs-lookup"><span data-stu-id="8098b-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="8098b-119">Typ nového výrazu je stejný jako u typů výrazů prvků.</span><span class="sxs-lookup"><span data-stu-id="8098b-119">The type of the new expression is the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="8098b-120">Zadaným dvěma celočíselnými výrazy, použijte binární operátor `^` (napájení) k vytvoření nového celočíselného výrazu.</span><span class="sxs-lookup"><span data-stu-id="8098b-120">Given two integer expressions, use the binary operator `^` (power) to form a new integer expression.</span></span>
<span data-ttu-id="8098b-121">Podobně můžete také použít `^` se dvěma dvojitými výrazy k vytvoření nového dvojitého výrazu.</span><span class="sxs-lookup"><span data-stu-id="8098b-121">Similarly, you can also use `^` with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="8098b-122">Nakonec můžete použít `^` s velkým celým číslem na levé straně a celé číslo na pravé straně k vytvoření nového výrazu Big Integer.</span><span class="sxs-lookup"><span data-stu-id="8098b-122">Finally, you can use `^` with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="8098b-123">V takovém případě se druhý parametr musí vejít do 32 bitů; v takovém případě vyvolá chybu za běhu.</span><span class="sxs-lookup"><span data-stu-id="8098b-123">In this case, the second parameter must fit into 32 bits; if not, it raises a runtime error.</span></span>

<span data-ttu-id="8098b-124">Dané dva celočíselné nebo velké celočíselné výrazy, tvoří nový celočíselný nebo velký celočíselný výraz pomocí `%` operátorů (modulo), `&&&` (bitové a), `|||` (bitových nebo) nebo `^^^` (bitových operátorů XOR).</span><span class="sxs-lookup"><span data-stu-id="8098b-124">Given two integer or big integer expressions, form a new integer or big integer expression using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="8098b-125">`<<<` `>>>` Pro vytvoření nového výrazu stejného typu, který je stejný jako výraz na levé straně, použijte operátor Integer nebo Big Integer na levé straně a výraz celého čísla na pravé straně.</span><span class="sxs-lookup"><span data-stu-id="8098b-125">Given either an integer or big integer expression on the left, and an integer expression on the right, use the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="8098b-126">Druhý parametr (velikost posunu) pro operaci posunu musí být větší nebo roven nule. chování pro záporné hodnoty posunutí není definováno.</span><span class="sxs-lookup"><span data-stu-id="8098b-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="8098b-127">Velikost SHIFT pro buď operaci posunutí musí být také do 32 bitů. v takovém případě vyvolá chybu za běhu.</span><span class="sxs-lookup"><span data-stu-id="8098b-127">The shift amount for either shift operation must also fit into 32 bits; if not, it raises a runtime error.</span></span>
<span data-ttu-id="8098b-128">Pokud je číslo posunuto jako celé číslo, je hodnota posunutí interpretována `mod 64` ; to znamená, že posun 1 a posun 65 mají stejný účinek.</span><span class="sxs-lookup"><span data-stu-id="8098b-128">If the number shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="8098b-129">Pro celočíselné i velké celočíselné hodnoty jsou posunuty aritmetické operace.</span><span class="sxs-lookup"><span data-stu-id="8098b-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="8098b-130">Posunutí záporné hodnoty buď vlevo nebo vpravo, vede k zápornému číslu.</span><span class="sxs-lookup"><span data-stu-id="8098b-130">Shifting a negative value either left or right results in a negative number.</span></span>
<span data-ttu-id="8098b-131">To znamená, že posun jednoho kroku doleva nebo doprava je stejný jako vynásobení nebo dělení 2, v uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="8098b-131">That is, shifting one step to the left or right is the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="8098b-132">Celočíselné dělení a celočíselné zbytky se řídí stejným chováním pro záporná čísla jako C#.</span><span class="sxs-lookup"><span data-stu-id="8098b-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="8098b-133">To znamená, že `a % b` vždy má stejné znaménko jako `a` a `b * (a / b) + a % b` vždy se rovná `a` .</span><span class="sxs-lookup"><span data-stu-id="8098b-133">That is, `a % b` always has the same sign as `a`, and `b * (a / b) + a % b` always equals `a`.</span></span>
<span data-ttu-id="8098b-134">Příklad:</span><span class="sxs-lookup"><span data-stu-id="8098b-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="8098b-135">5</span><span class="sxs-lookup"><span data-stu-id="8098b-135">5</span></span> | <span data-ttu-id="8098b-136">2</span><span class="sxs-lookup"><span data-stu-id="8098b-136">2</span></span> | <span data-ttu-id="8098b-137">2</span><span class="sxs-lookup"><span data-stu-id="8098b-137">2</span></span> | <span data-ttu-id="8098b-138">1</span><span class="sxs-lookup"><span data-stu-id="8098b-138">1</span></span>
 <span data-ttu-id="8098b-139">5</span><span class="sxs-lookup"><span data-stu-id="8098b-139">5</span></span> | <span data-ttu-id="8098b-140">-2</span><span class="sxs-lookup"><span data-stu-id="8098b-140">-2</span></span> | <span data-ttu-id="8098b-141">-2</span><span class="sxs-lookup"><span data-stu-id="8098b-141">-2</span></span> | <span data-ttu-id="8098b-142">1</span><span class="sxs-lookup"><span data-stu-id="8098b-142">1</span></span>
 <span data-ttu-id="8098b-143">-5</span><span class="sxs-lookup"><span data-stu-id="8098b-143">-5</span></span> | <span data-ttu-id="8098b-144">2</span><span class="sxs-lookup"><span data-stu-id="8098b-144">2</span></span> | <span data-ttu-id="8098b-145">-2</span><span class="sxs-lookup"><span data-stu-id="8098b-145">-2</span></span> | <span data-ttu-id="8098b-146">-1</span><span class="sxs-lookup"><span data-stu-id="8098b-146">-1</span></span>
 <span data-ttu-id="8098b-147">-5</span><span class="sxs-lookup"><span data-stu-id="8098b-147">-5</span></span> | <span data-ttu-id="8098b-148">-2</span><span class="sxs-lookup"><span data-stu-id="8098b-148">-2</span></span> | <span data-ttu-id="8098b-149">2</span><span class="sxs-lookup"><span data-stu-id="8098b-149">2</span></span> | <span data-ttu-id="8098b-150">-1</span><span class="sxs-lookup"><span data-stu-id="8098b-150">-1</span></span>

<span data-ttu-id="8098b-151">Operace dělení velkých celých čísel a zbytků fungují stejným způsobem.</span><span class="sxs-lookup"><span data-stu-id="8098b-151">Big integer division and modulus operations work the same way.</span></span>

<span data-ttu-id="8098b-152">S ohledem na libovolný číselný výraz můžete vytvořit nový výraz pomocí `-` unárního operátoru.</span><span class="sxs-lookup"><span data-stu-id="8098b-152">Given any numeric expression, you can form a new expression using the `-` unary operator.</span></span>
<span data-ttu-id="8098b-153">Nový výraz je stejného typu jako výraz prvku.</span><span class="sxs-lookup"><span data-stu-id="8098b-153">The new expression is the same type as the constituent expression.</span></span>

<span data-ttu-id="8098b-154">S ohledem na libovolný celočíselný nebo velký celočíselný výraz můžete vytvořit nový výraz stejného typu pomocí `~~~` unárního operátoru (bitového doplňku).</span><span class="sxs-lookup"><span data-stu-id="8098b-154">Given any integer or big integer expression, you can form a new expression of the same type using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="8098b-155">Výrazy logických hodnot</span><span class="sxs-lookup"><span data-stu-id="8098b-155">Boolean Expressions</span></span>

<span data-ttu-id="8098b-156">Dvě `Bool` hodnoty literálu jsou `true` a `false` .</span><span class="sxs-lookup"><span data-stu-id="8098b-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="8098b-157">Vzhledem k jakýmkoliv dvěma výrazům stejného primitivního typu lze `==` `!=` použít binární operátory a k vytvoření `Bool` výrazu.</span><span class="sxs-lookup"><span data-stu-id="8098b-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="8098b-158">Výraz má hodnotu true, pokud jsou dva výrazy stejné a false, pokud ne.</span><span class="sxs-lookup"><span data-stu-id="8098b-158">The expression is true if the two expressions are equal and false if not.</span></span>

<span data-ttu-id="8098b-159">Hodnoty uživatelsky definovaných typů nelze porovnat, lze porovnat pouze jejich nezabalené hodnoty.</span><span class="sxs-lookup"><span data-stu-id="8098b-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="8098b-160">Například pomocí operátoru "Unwrap" `!` (popsaný v podrobnostech [v Q# typech ](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span><span class="sxs-lookup"><span data-stu-id="8098b-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="8098b-161">Porovnání rovnosti pro `Qubit` hodnoty je rovnost identity; to znamená, zda dva výrazy identifikují stejný qubit.</span><span class="sxs-lookup"><span data-stu-id="8098b-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="8098b-162">Stavy těchto dvou qubits se neshodují, přistupovaly nebo nemění pomocí tohoto porovnání.</span><span class="sxs-lookup"><span data-stu-id="8098b-162">The states of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="8098b-163">Porovnání rovnosti pro `Double` hodnoty může být zavádějící z důvodu zaoblení efektů.</span><span class="sxs-lookup"><span data-stu-id="8098b-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="8098b-164">Například, `49.0 * (1.0/49.0) != 1.0`.</span><span class="sxs-lookup"><span data-stu-id="8098b-164">For example, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="8098b-165">Vzhledem k tomu, že jsou zadány dva číselné výrazy, binární operátory `>` , `<` , `>=` a lze `<=` použít k vytvoření nového logického výrazu, který je true, pokud je první výraz v tomto pořadí větší než, menší než nebo roven nebo menší nebo roven druhému výrazu.</span><span class="sxs-lookup"><span data-stu-id="8098b-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="8098b-166">U všech dvou logických výrazů použijte `and` binární operátor pro vytvoření nového logického výrazu, který je true, pokud jsou oba výrazy pravdivé.</span><span class="sxs-lookup"><span data-stu-id="8098b-166">Given any two Boolean expressions, use the `and` binary operator to construct a new Boolean expression that is true if both of the two expressions are true.</span></span> <span data-ttu-id="8098b-167">Podobně použití `or` operátoru vytvoří výraz, který má hodnotu true, pokud má jeden z obou výrazů hodnotu true.</span><span class="sxs-lookup"><span data-stu-id="8098b-167">Likewise, using the `or` operator creates an expression that is true if either of the two expressions is true.</span></span>

<span data-ttu-id="8098b-168">S ohledem na logický výraz `not` může být unární operátor použit k vytvoření nového logického výrazu, který je true, pokud je výraz prvku false.</span><span class="sxs-lookup"><span data-stu-id="8098b-168">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="8098b-169">Řetězcové výrazy</span><span class="sxs-lookup"><span data-stu-id="8098b-169">String expressions</span></span>

<span data-ttu-id="8098b-170">Q#povoluje použití řetězců v `fail` příkazu (vysvětleno v [toku řízení](xref:microsoft.quantum.guide.controlflow#fail-statement)) a ve [`Message`](xref:microsoft.quantum.intrinsic.message) funkci Standard.</span><span class="sxs-lookup"><span data-stu-id="8098b-170">Q# allows strings to be used in the `fail` statement (explained in [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span> <span data-ttu-id="8098b-171">Konkrétní chování druhé závisí na simulátoru, který se používá, ale obvykle zapisuje zprávu do hostitelské konzole při volání během Q# programu.</span><span class="sxs-lookup"><span data-stu-id="8098b-171">The specific behavior of the latter depends on the simulator used but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="8098b-172">Řetězce v Q# jsou buď literály, nebo interpolované řetězce.</span><span class="sxs-lookup"><span data-stu-id="8098b-172">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="8098b-173">Řetězcové literály jsou podobně jako jednoduché řetězcové literály ve většině jazyků: sekvence znaků Unicode uzavřených v uvozovkách `" "` .</span><span class="sxs-lookup"><span data-stu-id="8098b-173">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double-quotes `" "`.</span></span>
<span data-ttu-id="8098b-174">V řetězci použijte znak zpětného lomítka `\` k úniku znaku dvojité uvozovky ( `\"` ) nebo k vložení nového řádku (), návratu na začátek řádku `\n` ( `\r` ) nebo tabulátoru ( `\t` ).</span><span class="sxs-lookup"><span data-stu-id="8098b-174">Inside of a string, use the backslash character `\` to escape a double-quote character (`\"`), or to insert a new-line ( `\n` ), a carriage return (`\r`), or a tab (`\t`).</span></span>
<span data-ttu-id="8098b-175">Příklad:</span><span class="sxs-lookup"><span data-stu-id="8098b-175">For example:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="8098b-176">Interpolované řetězce</span><span class="sxs-lookup"><span data-stu-id="8098b-176">Interpolated strings</span></span>

<span data-ttu-id="8098b-177">Q#Syntaxe pro řetězcové interpolace je podmnožinou syntaxe jazyka C#.</span><span class="sxs-lookup"><span data-stu-id="8098b-177">The Q# syntax for string interpolations is a subset of the C# syntax.</span></span> <span data-ttu-id="8098b-178">Níže jsou uvedené klíčové body, které se týkají Q# :</span><span class="sxs-lookup"><span data-stu-id="8098b-178">Following are the key points as they pertain to Q#:</span></span>

* <span data-ttu-id="8098b-179">Pro identifikaci řetězcového literálu jako interpolované řetězce, předřaďte ho `$` symbolem.</span><span class="sxs-lookup"><span data-stu-id="8098b-179">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="8098b-180">Mezi znakem `$` a `"` , který začíná řetězcovým literálem, nesmí být mezera.</span><span class="sxs-lookup"><span data-stu-id="8098b-180">There can be no white space between the `$` and the `"` that starts a string literal.</span></span>

* <span data-ttu-id="8098b-181">Následuje základní příklad použití [`Message`](xref:microsoft.quantum.intrinsic.message) funkce pro zápis výsledku měření do konzoly spolu s ostatními Q# výrazy.</span><span class="sxs-lookup"><span data-stu-id="8098b-181">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* <span data-ttu-id="8098b-182">Libovolný platný Q# výraz se může objevit v interpolované řetězci.</span><span class="sxs-lookup"><span data-stu-id="8098b-182">Any valid Q# expression may appear in an interpolated string.</span></span>

* <span data-ttu-id="8098b-183">Výrazy uvnitř interpolované řetězce následují Q# syntax, nikoli syntaxe jazyka C#.</span><span class="sxs-lookup"><span data-stu-id="8098b-183">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span> <span data-ttu-id="8098b-184">Nejvýraznějším rozdílem je, že Q# nepodporují doslovné (víceřádkové) interpolované řetězce.</span><span class="sxs-lookup"><span data-stu-id="8098b-184">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>

<span data-ttu-id="8098b-185">Další podrobnosti o syntaxi jazyka C# naleznete v tématu [*interpolované řetězce*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span><span class="sxs-lookup"><span data-stu-id="8098b-185">For more details about the C# syntax, see [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>

## <a name="range-expressions"></a><span data-ttu-id="8098b-186">Výrazy rozsahu</span><span class="sxs-lookup"><span data-stu-id="8098b-186">Range Expressions</span></span>

<span data-ttu-id="8098b-187">S ohledem `Int` na tři výrazy `start` , `step` , a `stop` , výraz `start .. step .. stop` je výraz rozsahu, jehož prvním prvkem je `start` , druhý prvek je, `start+step` třetí prvek je `start+step+step` a tak dále, dokud `stop` nepředáte.</span><span class="sxs-lookup"><span data-stu-id="8098b-187">Given any three `Int` expressions `start`, `step`, and `stop`, the expression `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, and so on, until you pass `stop`.</span></span>
<span data-ttu-id="8098b-188">Rozsah může být prázdný, pokud `step` je například kladný a `stop < start` .</span><span class="sxs-lookup"><span data-stu-id="8098b-188">A range may be empty if, for example, `step` is positive and `stop < start`.</span></span>

<span data-ttu-id="8098b-189">Rozsah je zahrnut na obou koncích.</span><span class="sxs-lookup"><span data-stu-id="8098b-189">The range is inclusive at both ends.</span></span> <span data-ttu-id="8098b-190">To znamená, že pokud rozdíl mezi `start` a `stop` je celočíselný násobek `step` , bude poslední prvek rozsahu `stop` .</span><span class="sxs-lookup"><span data-stu-id="8098b-190">That is, if the difference between `start` and `stop` is an integer multiple of `step`, the last element of the range will be `stop`.</span></span>

<span data-ttu-id="8098b-191">Při daných dvou `Int` výrazech `start` a `stop` výraz `start .. stop` je výraz rozsahu, který je roven `start .. 1 .. stop` .</span><span class="sxs-lookup"><span data-stu-id="8098b-191">Given any two `Int` expressions `start` and `stop`, the expression `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="8098b-192">Všimněte si, že předpokládaná `step` je + 1, i když `stop` je menší než `start` ; v takovém případě je rozsah prázdný.</span><span class="sxs-lookup"><span data-stu-id="8098b-192">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="8098b-193">Mezi příklady oblastí patří:</span><span class="sxs-lookup"><span data-stu-id="8098b-193">Some example ranges are:</span></span>

- <span data-ttu-id="8098b-194">`1..3`je rozsah 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="8098b-194">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="8098b-195">`2..2..5`je rozsah 2, 4.</span><span class="sxs-lookup"><span data-stu-id="8098b-195">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="8098b-196">`2..2..6`je rozsah 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="8098b-196">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="8098b-197">`6..-2..2`je rozsah 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="8098b-197">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="8098b-198">`2..1`je prázdný rozsah.</span><span class="sxs-lookup"><span data-stu-id="8098b-198">`2..1` is the empty range.</span></span>
- <span data-ttu-id="8098b-199">`2..6..7`je rozsah 2.</span><span class="sxs-lookup"><span data-stu-id="8098b-199">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="8098b-200">`2..2..1`je prázdný rozsah.</span><span class="sxs-lookup"><span data-stu-id="8098b-200">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="8098b-201">`1..-1..2`je prázdný rozsah.</span><span class="sxs-lookup"><span data-stu-id="8098b-201">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="8098b-202">Výrazy qubit</span><span class="sxs-lookup"><span data-stu-id="8098b-202">Qubit Expressions</span></span>

<span data-ttu-id="8098b-203">Jediné `Qubit` výrazy jsou symboly, které jsou vázány na `Qubit` hodnoty nebo prvky pole `Qubit` polí.</span><span class="sxs-lookup"><span data-stu-id="8098b-203">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="8098b-204">Neexistují žádné `Qubit` literály.</span><span class="sxs-lookup"><span data-stu-id="8098b-204">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="8098b-205">Výrazy Pauli</span><span class="sxs-lookup"><span data-stu-id="8098b-205">Pauli Expressions</span></span>

<span data-ttu-id="8098b-206">Čtyři `Pauli` hodnoty, `PauliI` ,, `PauliX` `PauliY` a `PauliZ` , jsou platné `Pauli` výrazy.</span><span class="sxs-lookup"><span data-stu-id="8098b-206">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="8098b-207">Kromě toho jsou jedinými `Pauli` výrazy symboly, které jsou vázány na `Pauli` hodnoty nebo prvky pole `Pauli` polí.</span><span class="sxs-lookup"><span data-stu-id="8098b-207">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="8098b-208">Výsledné výrazy</span><span class="sxs-lookup"><span data-stu-id="8098b-208">Result Expressions</span></span>

<span data-ttu-id="8098b-209">Dvě `Result` hodnoty `One` a `Zero` jsou platné `Result` výrazy.</span><span class="sxs-lookup"><span data-stu-id="8098b-209">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="8098b-210">Kromě toho jsou jedinými `Result` výrazy symboly, které jsou vázány na `Result` hodnoty nebo prvky pole `Result` polí.</span><span class="sxs-lookup"><span data-stu-id="8098b-210">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="8098b-211">Konkrétně si všimněte, že není `One` stejný jako celé číslo `1` a mezi nimi není přímý převod.</span><span class="sxs-lookup"><span data-stu-id="8098b-211">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="8098b-212">Totéž platí pro `Zero` a `0` .</span><span class="sxs-lookup"><span data-stu-id="8098b-212">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="8098b-213">Výrazy řazené kolekce členů</span><span class="sxs-lookup"><span data-stu-id="8098b-213">Tuple Expressions</span></span>

<span data-ttu-id="8098b-214">Literál řazené kolekce členů je sekvence výrazů prvků příslušného typu oddělených čárkami, které jsou uzavřeny v závorkách.</span><span class="sxs-lookup"><span data-stu-id="8098b-214">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in parentheses.</span></span>
<span data-ttu-id="8098b-215">Například `(1, One)` je `(Int, Result)` výraz.</span><span class="sxs-lookup"><span data-stu-id="8098b-215">For example, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="8098b-216">Kromě literálů jsou jedinými výrazy řazené kolekce členů symboly, které jsou vázány na hodnoty řazené kolekce členů, prvky pole řazené kolekce členů a volání, která vrací řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="8098b-216">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="8098b-217">Výrazy uživatelsky definovaného typu</span><span class="sxs-lookup"><span data-stu-id="8098b-217">User-Defined Type Expressions</span></span>

<span data-ttu-id="8098b-218">Literál uživatelsky definovaného typu se skládá z názvu typu následovaného literálem řazené kolekce členů základního typu řazené kolekce členů typu.</span><span class="sxs-lookup"><span data-stu-id="8098b-218">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="8098b-219">Například pokud `IntPair` je uživatelem definovaný typ založený na `(Int, Int)` , pak `IntPair(2, 3)` je platný literál tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="8098b-219">For example, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` is a valid literal of that type.</span></span>

<span data-ttu-id="8098b-220">Kromě literálů jsou jedinými výrazy uživatelsky definovaného typu symboly, které jsou vázány na hodnoty daného typu, prvky pole polí daného typu a volání, která vrací tento typ.</span><span class="sxs-lookup"><span data-stu-id="8098b-220">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="8098b-221">Rozbalit výrazy</span><span class="sxs-lookup"><span data-stu-id="8098b-221">Unwrap Expressions</span></span>

<span data-ttu-id="8098b-222">V Q# , operátor rozbalení je koncovým vykřičníkem `!` .</span><span class="sxs-lookup"><span data-stu-id="8098b-222">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="8098b-223">Například pokud `IntPair` je uživatelem definovaný typ s podkladovým typem `(Int, Int)` a `s` je proměnná s hodnotou `IntPair(2, 3)` , pak `s!` je `(2, 3)` .</span><span class="sxs-lookup"><span data-stu-id="8098b-223">For example, if `IntPair` is a user-defined type with the underlying type `(Int, Int)` and `s` is a variable with value `IntPair(2, 3)`, then `s!` is `(2, 3)`.</span></span>

<span data-ttu-id="8098b-224">Pro uživatelsky definované typy definované v jiných uživatelsky definovaných typech můžete zopakovat operátor rozbalení.</span><span class="sxs-lookup"><span data-stu-id="8098b-224">For user-defined types defined in terms of other user-defined types, you can repeat the unwrap operator.</span></span> <span data-ttu-id="8098b-225">Například `s!!` označuje zdvojnásobení nezabalenou hodnotu `s` .</span><span class="sxs-lookup"><span data-stu-id="8098b-225">For example, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="8098b-226">Proto, pokud `WrappedPair` je uživatelem definovaný typ s podkladovým typem `IntPair` , a `t` je proměnná s hodnotou `WrappedPair(IntPair(1,2))` , pak `t!!` je `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="8098b-226">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` is `(1,2)`.</span></span>

<span data-ttu-id="8098b-227">`!`Operátor má vyšší prioritu než všechny ostatní operátory, kromě `[]` indexace pole a řezů.</span><span class="sxs-lookup"><span data-stu-id="8098b-227">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="8098b-228">`!`a dá se `[]` vytvořit vazba. to znamená, že je `a[i]![3]` čten jako `((a[i])!)[3]` : Vezměte `i` element elementu `a` , rozbalíte ho a potom Získejte třetí prvek nezabalené hodnoty (který musí být pole).</span><span class="sxs-lookup"><span data-stu-id="8098b-228">`!` and `[]` bind positionally; that is, `a[i]![3]` is read as `((a[i])!)[3]`: take the `i`th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="8098b-229">Priorita `!` operátoru má jeden dopad, který nemusí být zřejmý.</span><span class="sxs-lookup"><span data-stu-id="8098b-229">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="8098b-230">Vrátí-li funkce nebo operace hodnotu, která je poté nezabalena, musí být volání funkce nebo operace uzavřena v závorkách, aby se argumenty řazené kolekce členů navázaly na volání, nikoli na rozbalení.</span><span class="sxs-lookup"><span data-stu-id="8098b-230">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="8098b-231">Příklad:</span><span class="sxs-lookup"><span data-stu-id="8098b-231">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="8098b-232">Výrazy Array</span><span class="sxs-lookup"><span data-stu-id="8098b-232">Array Expressions</span></span>

<span data-ttu-id="8098b-233">Literál pole je sekvence jednoho nebo více výrazů prvků oddělených čárkami, které jsou uzavřeny v hranatých závorkách `[]` .</span><span class="sxs-lookup"><span data-stu-id="8098b-233">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in square brackets `[]`.</span></span>
<span data-ttu-id="8098b-234">Všechny elementy musí být kompatibilní se stejným typem.</span><span class="sxs-lookup"><span data-stu-id="8098b-234">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="8098b-235">Pokud jsou zadána dvě pole stejného typu, použijte binární `+` operátor pro vytvoření nového pole, které je zřetězením dvou polí.</span><span class="sxs-lookup"><span data-stu-id="8098b-235">Given two arrays of the same type, use the binary `+` operator to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="8098b-236">Příklad: `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="8098b-236">For example, `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="8098b-237">Vytvoření pole</span><span class="sxs-lookup"><span data-stu-id="8098b-237">Array Creation</span></span>

<span data-ttu-id="8098b-238">Pro zadání typu a `Int` výrazu použijte `new` operátor k přidělení nového pole dané velikosti.</span><span class="sxs-lookup"><span data-stu-id="8098b-238">Given a type and an `Int` expression, use the `new` operator to allocate a new array of the given size.</span></span>
<span data-ttu-id="8098b-239">Například `new Int[i + 1]` přidělí nové `Int` pole `i + 1` elementům.</span><span class="sxs-lookup"><span data-stu-id="8098b-239">For example, `new Int[i + 1]` allocates a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="8098b-240">Prázdné literály pole, například `[]` , nejsou povoleny.</span><span class="sxs-lookup"><span data-stu-id="8098b-240">Empty array literals, such as `[]`, are not allowed.</span></span>
<span data-ttu-id="8098b-241">Místo toho můžete vytvořit pole s nulovou délkou pomocí `new T[0]` , kde `T` je zástupný symbol pro vhodný typ.</span><span class="sxs-lookup"><span data-stu-id="8098b-241">Instead, you can create an array of length zero by using `new T[0]`, where `T` is a placeholder for a suitable type.</span></span>

<span data-ttu-id="8098b-242">Prvky nového pole se inicializují do výchozí hodnoty závislé na typu.</span><span class="sxs-lookup"><span data-stu-id="8098b-242">The elements of a new array initialize to a type-dependent default value.</span></span>
<span data-ttu-id="8098b-243">Ve většině případů se jedná o určitou variaci nula.</span><span class="sxs-lookup"><span data-stu-id="8098b-243">In most cases, this is some variation of zero.</span></span>

<span data-ttu-id="8098b-244">Pro qubits a volat, které jsou odkazy na entity, neexistuje přiměřená výchozí hodnota.</span><span class="sxs-lookup"><span data-stu-id="8098b-244">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="8098b-245">Proto pro tyto typy je výchozí hodnota neplatný odkaz, který nelze použít, aniž by došlo k chybě za běhu, podobně jako odkaz s hodnotou null v jazycích, jako je C# nebo Java.</span><span class="sxs-lookup"><span data-stu-id="8098b-245">Thus, for these types, the default is an invalid reference that you cannot use without causing a runtime error, similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="8098b-246">Pole obsahující qubits nebo volat musí být inicializována s jinými než výchozími hodnotami, aby bylo možné jejich prvky bezpečně použít.</span><span class="sxs-lookup"><span data-stu-id="8098b-246">Arrays containing qubits or callables must be initialized with non-default values before you can use their elements safely.</span></span> <span data-ttu-id="8098b-247">Vhodné inicializační rutiny naleznete v tématu <xref:microsoft.quantum.arrays> .</span><span class="sxs-lookup"><span data-stu-id="8098b-247">For suitable initialization routines, see <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="8098b-248">Výchozí hodnoty pro každý typ jsou:</span><span class="sxs-lookup"><span data-stu-id="8098b-248">The default values for each type are:</span></span>

<span data-ttu-id="8098b-249">Typ</span><span class="sxs-lookup"><span data-stu-id="8098b-249">Type</span></span> | <span data-ttu-id="8098b-250">Výchozí</span><span class="sxs-lookup"><span data-stu-id="8098b-250">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="8098b-251">_Neplatný qubit_</span><span class="sxs-lookup"><span data-stu-id="8098b-251">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="8098b-252">Prázdný rozsah`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="8098b-252">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="8098b-253">_Neplatný volat_</span><span class="sxs-lookup"><span data-stu-id="8098b-253">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="8098b-254">Typy řazené kolekce členů inicializují element po prvku.</span><span class="sxs-lookup"><span data-stu-id="8098b-254">Tuple types initialize element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="8098b-255">Prvky pole</span><span class="sxs-lookup"><span data-stu-id="8098b-255">Array Elements</span></span>

<span data-ttu-id="8098b-256">Pro výraz pole a `Int` výraz vytvořte nový výraz pomocí operátoru elementu pole `[]` .</span><span class="sxs-lookup"><span data-stu-id="8098b-256">Given an array expression and an `Int` expression, form a new expression using the array element operator `[]`.</span></span>
<span data-ttu-id="8098b-257">Nový výraz je stejného typu jako typ prvku pole.</span><span class="sxs-lookup"><span data-stu-id="8098b-257">The new expression is the same type as the element type of the array.</span></span>
<span data-ttu-id="8098b-258">Například pokud `a` je svázán s polem typu `Double` , pak `a[4]` je `Double` výraz.</span><span class="sxs-lookup"><span data-stu-id="8098b-258">For example, if `a` is bound to an array of type `Double`, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="8098b-259">Pokud výraz pole není jednoduchý identifikátor, je nutné jej uzavřít do závorek pro výběr elementu.</span><span class="sxs-lookup"><span data-stu-id="8098b-259">If the array expression is not a simple identifier, you must enclose it in parentheses to select an element.</span></span>
<span data-ttu-id="8098b-260">Například pokud `a` a `b` jsou obě pole typu `Int` , je prvek z zřetězení vyjádřen jako:</span><span class="sxs-lookup"><span data-stu-id="8098b-260">For example, if `a` and `b` are both arrays of type `Int`, an element from the concatenation is expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="8098b-261">Všechna pole v Q# jsou založená na nule.</span><span class="sxs-lookup"><span data-stu-id="8098b-261">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="8098b-262">To znamená, že první prvek pole `a` je vždy `a[0]` .</span><span class="sxs-lookup"><span data-stu-id="8098b-262">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="8098b-263">Řezy pole</span><span class="sxs-lookup"><span data-stu-id="8098b-263">Array Slices</span></span>

<span data-ttu-id="8098b-264">Při zadání výrazu pole a `Range` výrazu se vytvoří nový výraz s použitím operátoru řezu array `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="8098b-264">Given an array expression and a `Range` expression, form a new expression using the array slice operator `[ ]`.</span></span>
<span data-ttu-id="8098b-265">Nový výraz je stejného typu jako pole a obsahuje položky pole indexované prvky `Range` , v pořadí definovaném `Range` .</span><span class="sxs-lookup"><span data-stu-id="8098b-265">The new expression is the same type as the array and contains the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="8098b-266">Například pokud `a` je svázán s polem typu `Double` , pak `a[3..-1..0]` je `Double[]` výraz, který obsahuje první čtyři prvky, `a` ale v obráceném pořadí, jak jsou uvedeny v `a` .</span><span class="sxs-lookup"><span data-stu-id="8098b-266">For example, if `a` is bound to an array of type `Double`, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="8098b-267">Pokud `Range` je hodnota prázdná, pak výsledný řez pole má nulovou délku.</span><span class="sxs-lookup"><span data-stu-id="8098b-267">If the `Range` is empty, then the resulting array slice is zero length.</span></span>

<span data-ttu-id="8098b-268">Stejně jako u odkazů na prvky pole, pokud výraz pole není jednoduchý identifikátor, je nutné jej uzavřít do závorek a vytvořit jeho výřez.</span><span class="sxs-lookup"><span data-stu-id="8098b-268">Just as with referencing array elements, if the array expression is not a simple identifier, you must enclose it in parentheses to slice it.</span></span>
<span data-ttu-id="8098b-269">Například pokud `a` a `b` jsou obě pole typu `Int` , řez z zřetězení je vyjádřen jako:</span><span class="sxs-lookup"><span data-stu-id="8098b-269">For example, if `a` and `b` are both arrays of type `Int`, a slice from the concatenation is expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="8098b-270">Odvozené počáteční/koncové hodnoty</span><span class="sxs-lookup"><span data-stu-id="8098b-270">Inferred start/end values</span></span>

<span data-ttu-id="8098b-271">Od naší [verze 0,8](xref:microsoft.quantum.relnotes)podporujeme kontextové výrazy pro průřezy rozsahu.</span><span class="sxs-lookup"><span data-stu-id="8098b-271">Starting with our [0.8 release](xref:microsoft.quantum.relnotes), we support contextual expressions for range slicing.</span></span> <span data-ttu-id="8098b-272">Konkrétně můžete vynechat počáteční a koncové hodnoty rozsahu v kontextu výrazu dělení rozsahu.</span><span class="sxs-lookup"><span data-stu-id="8098b-272">In particular, you may omit range start and end values in the context of a range slicing expression.</span></span> <span data-ttu-id="8098b-273">V takovém případě kompilátor použije následující pravidla pro odvození zamýšlených oddělovačů pro rozsah:</span><span class="sxs-lookup"><span data-stu-id="8098b-273">In that case, the compiler applies the following rules to infer the intended delimiters for the range:</span></span>

* <span data-ttu-id="8098b-274">Pokud je hodnota *začátek* rozsahu vynechána, pak odvozená počáteční hodnota.</span><span class="sxs-lookup"><span data-stu-id="8098b-274">If the range *start* value is omitted, then the inferred start value</span></span>
  * <span data-ttu-id="8098b-275">je nula, pokud není zadán žádný krok, nebo je zadaný krok kladný.</span><span class="sxs-lookup"><span data-stu-id="8098b-275">is zero if no step is specified or the specified step is positive.</span></span>  
  * <span data-ttu-id="8098b-276">je délka pole řezu minus jedna, pokud je zadaný krok záporný.</span><span class="sxs-lookup"><span data-stu-id="8098b-276">is the length of the sliced array minus one if the specified step is negative.</span></span>

* <span data-ttu-id="8098b-277">Pokud je hodnota *konec* rozsahu vynechána, pak odvozená koncová hodnota</span><span class="sxs-lookup"><span data-stu-id="8098b-277">If the range *end* value is omitted, then the inferred end value</span></span>
  * <span data-ttu-id="8098b-278">je délka pole řezu minus jedna, pokud není zadán žádný krok, nebo je zadaný krok kladný.</span><span class="sxs-lookup"><span data-stu-id="8098b-278">is the length of the sliced array minus one if no step is specified or the specified step is positive.</span></span>
  * <span data-ttu-id="8098b-279">je nula, pokud je zadaný krok záporný.</span><span class="sxs-lookup"><span data-stu-id="8098b-279">is zero if the specified step is negative.</span></span>

<span data-ttu-id="8098b-280">Tady je několik příkladů:</span><span class="sxs-lookup"><span data-stu-id="8098b-280">Some examples are:</span></span>

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="8098b-281">Výrazy kopírování a aktualizace</span><span class="sxs-lookup"><span data-stu-id="8098b-281">Copy-and-Update Expressions</span></span>

<span data-ttu-id="8098b-282">Vzhledem k tomu, že všechny Q# typy jsou typy hodnot (s qubits, které pobírají trochu speciální role), tvoří kopii "kopie", když je hodnota svázána se symbolem nebo při převázání symbolu.</span><span class="sxs-lookup"><span data-stu-id="8098b-282">Since all Q# types are value types (with the qubits taking a somewhat special role), formally a "copy" is created when a value is bound to a symbol or when a symbol is rebound.</span></span> <span data-ttu-id="8098b-283">To znamená, že chování Q# je stejné jako při vytvoření kopie pomocí operátoru přiřazení.</span><span class="sxs-lookup"><span data-stu-id="8098b-283">That is to say, the behavior of Q# is the same as if a copy were created using an assignment operator.</span></span> 

<span data-ttu-id="8098b-284">Samozřejmě jsou v praxi v případě potřeby znovu vytvořeny pouze příslušné součásti.</span><span class="sxs-lookup"><span data-stu-id="8098b-284">Of course, in practice, only the relevant pieces are recreated as needed.</span></span> <span data-ttu-id="8098b-285">To má vliv na to, jak kopírujete pole, protože není možné aktualizovat položky pole.</span><span class="sxs-lookup"><span data-stu-id="8098b-285">This affects how you copy arrays because it is not possible to update array items.</span></span> <span data-ttu-id="8098b-286">Chcete-li upravit existující pole, je nutné využít mechanismus *kopírování a aktualizace* .</span><span class="sxs-lookup"><span data-stu-id="8098b-286">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="8098b-287">Můžete vytvořit nové pole z existujícího pole pomocí výrazů *kopírování a aktualizace* , které používají operátory `w/` a `<-` .</span><span class="sxs-lookup"><span data-stu-id="8098b-287">You can create a new array from an existing array via *copy-and-update* expressions, which use the operators `w/` and `<-`.</span></span>
<span data-ttu-id="8098b-288">Výraz kopírování a aktualizace je výrazem formuláře `expression1 w/ expression2 <- expression3` , kde</span><span class="sxs-lookup"><span data-stu-id="8098b-288">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where</span></span>

* <span data-ttu-id="8098b-289">`expression1`musí být typu `T[]` pro nějaký typ `T` .</span><span class="sxs-lookup"><span data-stu-id="8098b-289">`expression1` must be type `T[]` for some type `T`.</span></span>
* <span data-ttu-id="8098b-290">`expression2`definuje, které indexy v poli určeném `expression1` pro úpravy mají být upraveny.</span><span class="sxs-lookup"><span data-stu-id="8098b-290">`expression2` defines which indices in the array specified in `expression1` to modify.</span></span> <span data-ttu-id="8098b-291">`expression2`musí být buď Type, `Int` nebo type `Range` .</span><span class="sxs-lookup"><span data-stu-id="8098b-291">`expression2` must be either type `Int` or type `Range`.</span></span>
* <span data-ttu-id="8098b-292">`expression3`je hodnota, která se používá k aktualizaci prvků v `expression1` , v závislosti na indexech zadaných v `expression2` .</span><span class="sxs-lookup"><span data-stu-id="8098b-292">`expression3` is the value(s) used to update elements in `expression1`, based on the indices specified in `expression2`.</span></span> <span data-ttu-id="8098b-293">Pokud `expression2` je typ `Int` , `expression3` musí být typ `T` .</span><span class="sxs-lookup"><span data-stu-id="8098b-293">If `expression2` is type `Int`, `expression3` must be type `T`.</span></span> <span data-ttu-id="8098b-294">Pokud `expression2` je typ `Range` , `expression3` musí být typ `T[]` .</span><span class="sxs-lookup"><span data-stu-id="8098b-294">If `expression2` is type `Range`, `expression3` must be type `T[]`.</span></span>

<span data-ttu-id="8098b-295">Například výraz kopírování a aktualizace `arr w/ idx <- value` vytvoří nové pole se všemi prvky nastavenými na odpovídající prvky v `arr` , s výjimkou prvků určených parametrem `idx` , který je nastaven na hodnotu (y) v `value` .</span><span class="sxs-lookup"><span data-stu-id="8098b-295">For example, the copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding elements in `arr`, except for the element(s) specified by `idx`, which is set to the value(s) in `value`.</span></span> 

<span data-ttu-id="8098b-296">Zadané `arr` pole obsahuje `[0,1,2,3]` , pak</span><span class="sxs-lookup"><span data-stu-id="8098b-296">Given `arr` contains the array `[0,1,2,3]`, then</span></span> 

- <span data-ttu-id="8098b-297">`arr w/ 0 <- 10`je pole `[10,1,2,3]` .</span><span class="sxs-lookup"><span data-stu-id="8098b-297">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="8098b-298">`arr w/ 2 <- 10`je pole `[0,1,10,3]` .</span><span class="sxs-lookup"><span data-stu-id="8098b-298">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="8098b-299">`arr w/ 0..2..3 <- [10,12]`je pole `[10,1,12,3]` .</span><span class="sxs-lookup"><span data-stu-id="8098b-299">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="8098b-300">Výrazy kopírování a aktualizace pro pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="8098b-300">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="8098b-301">Podobné výrazy existují pro pojmenované položky v uživatelsky definovaných typech.</span><span class="sxs-lookup"><span data-stu-id="8098b-301">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="8098b-302">Zvažte například typ</span><span class="sxs-lookup"><span data-stu-id="8098b-302">For example, consider the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="8098b-303">Pokud `c` obsahuje hodnotu typu `Complex(1., -1.)` , pak `c w/ Re <- 0.` je výraz typu `Complex` , který je vyhodnocen jako `Complex(0., -1.)` .</span><span class="sxs-lookup"><span data-stu-id="8098b-303">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="8098b-304">Vícenásobná pole</span><span class="sxs-lookup"><span data-stu-id="8098b-304">Jagged Arrays</span></span>

<span data-ttu-id="8098b-305">Vícenásobné pole, někdy označované jako "pole polí", je pole, jehož prvky jsou pole.</span><span class="sxs-lookup"><span data-stu-id="8098b-305">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="8098b-306">Prvky vícenásobného pole mohou mít různé velikosti.</span><span class="sxs-lookup"><span data-stu-id="8098b-306">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="8098b-307">Následující příklad ukazuje, jak deklarovat a inicializovat vícenásobné pole reprezentující tabulku násobení.</span><span class="sxs-lookup"><span data-stu-id="8098b-307">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="8098b-308">Pole, která se mají volat</span><span class="sxs-lookup"><span data-stu-id="8098b-308">Arrays of callables</span></span> 

<span data-ttu-id="8098b-309">Můžete také vytvořit pole, které lze volat.</span><span class="sxs-lookup"><span data-stu-id="8098b-309">You can also create an array of callables.</span></span>

* <span data-ttu-id="8098b-310">Je-li běžný typ prvku typ operace nebo funkce, všechny prvky musí mít stejné vstupní a výstupní typy.</span><span class="sxs-lookup"><span data-stu-id="8098b-310">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
* <span data-ttu-id="8098b-311">Typ elementu pole podporuje všechny [funktory](xref:microsoft.quantum.guide.operationsfunctions) , které jsou podporovány všemi prvky.</span><span class="sxs-lookup"><span data-stu-id="8098b-311">The element type of the array supports any [functors](xref:microsoft.quantum.guide.operationsfunctions) that are supported by all of the elements.</span></span>
<span data-ttu-id="8098b-312">Například pokud `Op1` , `Op2` a `Op3` všechny jsou `Qubit[] => Unit` operace, ale `Op1` podporují `Adjoint` , `Op2` podporují `Controlled` a `Op3` podporují obojí:</span><span class="sxs-lookup"><span data-stu-id="8098b-312">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit` operations, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>
  * <span data-ttu-id="8098b-313">`[Op1, Op2]`je pole `(Qubit[] => Unit)` operací.</span><span class="sxs-lookup"><span data-stu-id="8098b-313">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
  * <span data-ttu-id="8098b-314">`[Op1, Op3]`je pole `(Qubit[] => Unit is Adj)` operací.</span><span class="sxs-lookup"><span data-stu-id="8098b-314">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
  * <span data-ttu-id="8098b-315">`[Op2, Op3]`je pole `(Qubit[] => Unit is Ctl)` operací.</span><span class="sxs-lookup"><span data-stu-id="8098b-315">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="8098b-316">Nicméně zatímco operace `(Qubit[] => Unit is Adj)` a `(Qubit[] => Unit is Ctl)` mají společný základní typ `(Qubit[] => Unit)` , *pole* těchto operací nesdílejí společný základní typ.</span><span class="sxs-lookup"><span data-stu-id="8098b-316">However, while the operations `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` have the common base type of `(Qubit[] => Unit)`, *arrays* of these operations do not share a common base type.</span></span>

<span data-ttu-id="8098b-317">Například `[[Op1], [Op2]]` by aktuálně vyvolala chybu, protože se pokusí vytvořit pole dvou nekompatibilních typů polí `(Qubit[] => Unit is Adj)[]` a `(Qubit[] => Unit is Ctl)[]` .</span><span class="sxs-lookup"><span data-stu-id="8098b-317">For example, `[[Op1], [Op2]]` would currently raise an error because it attempts to create an array of the two incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>

<span data-ttu-id="8098b-318">Další informace o tom, jak volat, najdete v tématu věnovaném vydaným [výrazům](#callable-expressions) na této stránce nebo [operacích a funkcích v Q# ](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="8098b-318">For more information on callables, see [Callable expressions](#callable-expressions)  on this page or [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="8098b-319">Podmíněné výrazy</span><span class="sxs-lookup"><span data-stu-id="8098b-319">Conditional Expressions</span></span>

<span data-ttu-id="8098b-320">Vzhledem k dvěma výrazům stejného typu a logickému výrazu tvoří podmíněný výraz pomocí otazníku, `?` a svislého panelu `|` .</span><span class="sxs-lookup"><span data-stu-id="8098b-320">Given two expressions of the same type and a Boolean expression, form a conditional expression using the question mark, `?`, and the vertical bar `|`.</span></span> <span data-ttu-id="8098b-321">Je `a==b ? c | d` -li zadána hodnota podmíněného výrazu, má hodnotu `c` true a je-li hodnota `a==b` `d` false.</span><span class="sxs-lookup"><span data-stu-id="8098b-321">Given `a==b ? c | d`, the value of the conditional expression is `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="8098b-322">Podmíněné výrazy s volat</span><span class="sxs-lookup"><span data-stu-id="8098b-322">Conditional expressions with callables</span></span>

<span data-ttu-id="8098b-323">Podmíněné výrazy mohou být vyhodnoceny na operace, které mají stejné vstupy a výstupy, ale podporují různé funktory.</span><span class="sxs-lookup"><span data-stu-id="8098b-323">Conditional expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span> <span data-ttu-id="8098b-324">V tomto případě typ podmíněného výrazu je operace se vstupy a výstupy, které podporují libovolný funktory podporovaný oběma výrazy.</span><span class="sxs-lookup"><span data-stu-id="8098b-324">In this case, the type of the conditional expression is an operation with inputs and outputs that support any functors supported by both expressions.</span></span>
<span data-ttu-id="8098b-325">Například pokud `Op1` , `Op2` a `Op3` jsou všechny `Qubit[]=>Unit` , ale `Op1` podporují `Adjoint` , `Op2` podporují `Controlled` a `Op3` podporují obojí:</span><span class="sxs-lookup"><span data-stu-id="8098b-325">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="8098b-326">`flag ? Op1 | Op2`je `(Qubit[] => Unit)` operace.</span><span class="sxs-lookup"><span data-stu-id="8098b-326">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="8098b-327">`flag ? Op1 | Op3`je `(Qubit[] => Unit is Adj)` operace.</span><span class="sxs-lookup"><span data-stu-id="8098b-327">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="8098b-328">`flag ? Op2 | Op3`je `(Qubit[] => Unit is Ctl)` operace.</span><span class="sxs-lookup"><span data-stu-id="8098b-328">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="8098b-329">Pokud jeden ze dvou možných výsledných výrazů zahrnuje volání funkce nebo operace, provede toto volání pouze v případě, že je tento výsledek ten, který je hodnotou volání.</span><span class="sxs-lookup"><span data-stu-id="8098b-329">If either of the two possible result expressions include a function or operation call, that call only takes place if that result is the one that is the value of the call.</span></span> <span data-ttu-id="8098b-330">Například `a==b ? C(qs) | D(qs)` Pokud `a==b` má hodnotu true, `C` je vyvolána operace, a pokud je hodnota false, bude `D` vyvolána pouze operace.</span><span class="sxs-lookup"><span data-stu-id="8098b-330">For example, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true, then the `C` operation is invoked, and if it is false then only the `D` operation is invoked.</span></span> <span data-ttu-id="8098b-331">Tento přístup je podobný jako u *krátkých okruhů* v jiných jazycích.</span><span class="sxs-lookup"><span data-stu-id="8098b-331">This approach is similar to *short-circuiting* in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="8098b-332">Výrazy, které se mají volat</span><span class="sxs-lookup"><span data-stu-id="8098b-332">Callable Expressions</span></span>

<span data-ttu-id="8098b-333">Volatelné literály je název operace nebo funkce definované v oboru kompilace.</span><span class="sxs-lookup"><span data-stu-id="8098b-333">A callable literal is the name of an operation or function defined in the compilation scope.</span></span> <span data-ttu-id="8098b-334">Například `X` je literál operace, který odkazuje na standardní `X` operace knihovny a `Message` je literál funkce, který odkazuje na standardní `Message` funkci knihovny.</span><span class="sxs-lookup"><span data-stu-id="8098b-334">For example, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="8098b-335">Pokud operace podporuje `Adjoint` funktor, pak `Adjoint op` je výraz operace.</span><span class="sxs-lookup"><span data-stu-id="8098b-335">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="8098b-336">Podobně platí, že pokud operace podporuje `Controlled` funktor, pak `Controlled op` je výraz operace.</span><span class="sxs-lookup"><span data-stu-id="8098b-336">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="8098b-337">Další informace o typech těchto výrazů naleznete v tématu [specializace operací volání](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span><span class="sxs-lookup"><span data-stu-id="8098b-337">For more information about the types of these expressions, see [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="8098b-338">Funktory ( `Adjoint` a `Controlled` ) sváže více než všechny ostatní operátory, s výjimkou operátoru Unwrap `!` a pole s indexem `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="8098b-338">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[ ]`.</span></span>
<span data-ttu-id="8098b-339">Následující všechny jsou tedy platné, za předpokladu, že operace podporují funktory použité:</span><span class="sxs-lookup"><span data-stu-id="8098b-339">Thus, the following are all valid, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="8098b-340">Výrazy s parametry, které je typu volat</span><span class="sxs-lookup"><span data-stu-id="8098b-340">Type-parameterized callable expressions</span></span>

<span data-ttu-id="8098b-341">Můžete použít literál, který lze volat jako hodnotu, například pro přiřazení k proměnné nebo předání na jinou možnost, která se dá volat.</span><span class="sxs-lookup"><span data-stu-id="8098b-341">You can use a callable literal as a value, for example, to assign it to a variable or pass it to another callable.</span></span> <span data-ttu-id="8098b-342">V takovém případě, pokud je možné volat [parametry typu](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), je nutné zadat parametry jako součást hodnoty, kterou lze volat.</span><span class="sxs-lookup"><span data-stu-id="8098b-342">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), you must provide the parameters as part of the callable value.</span></span>

<span data-ttu-id="8098b-343">Hodnota, která se nedá volat, nemůže mít nespecifikované parametry typu.</span><span class="sxs-lookup"><span data-stu-id="8098b-343">A callable value cannot have any unspecified type parameters.</span></span> <span data-ttu-id="8098b-344">Například pokud `Fun` je funkce s podpisem `'T1->Unit` :</span><span class="sxs-lookup"><span data-stu-id="8098b-344">For example, if `Fun` is a function with the signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="8098b-345">Volat výrazy vyvolání</span><span class="sxs-lookup"><span data-stu-id="8098b-345">Callable Invocation Expressions</span></span>

<span data-ttu-id="8098b-346">Vzhledem k výrazu, který je možné volat (operace nebo funkce) a výrazu řazené kolekce členů vstupního typu signatury, můžete vytvořit *výraz volání* připojením výrazu řazené kolekce členů k výrazu, který je k volání.</span><span class="sxs-lookup"><span data-stu-id="8098b-346">Given a callable expression (operation or function) and a tuple expression of the input type of the callable's signature, you can form an *invocation expression* by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="8098b-347">Typ výrazu vyvolání je výstupní typ signatury, kterou chcete volat.</span><span class="sxs-lookup"><span data-stu-id="8098b-347">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="8098b-348">Například pokud `Op` je operace s podpisem `((Int, Qubit) => Double)` , `Op(3, qubit1)` je výraz typu `Double` .</span><span class="sxs-lookup"><span data-stu-id="8098b-348">For example, if `Op` is an operation with the signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="8098b-349">Podobně, pokud `Sin` je funkce s signaturou `(Double -> Double)` , `Sin(0.1)` je výraz typu `Double` .</span><span class="sxs-lookup"><span data-stu-id="8098b-349">Similarly, if `Sin` is a function with the signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="8098b-350">Nakonec, pokud `Builder` je funkce s signaturou `(Int -> (Int -> Int))` , pak `Builder(3)` je funkce z `Int` na `Int` .</span><span class="sxs-lookup"><span data-stu-id="8098b-350">Finally, if `Builder` is a function with the signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from `Int` to `Int`.</span></span>

<span data-ttu-id="8098b-351">Vyvolání výsledku výrazu s možností volání vyžaduje navíc pár závorek kolem volání.</span><span class="sxs-lookup"><span data-stu-id="8098b-351">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="8098b-352">Proto pokud chcete vyvolat výsledek volání `Builder` z předchozího odstavce, správná syntaxe je:</span><span class="sxs-lookup"><span data-stu-id="8098b-352">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="8098b-353">Při vyvolání [typu](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) , který je možné volat, můžete zadat skutečné parametry typu v rámci lomených závorek `< >` po volání.</span><span class="sxs-lookup"><span data-stu-id="8098b-353">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, you can specify the actual type parameters within angle brackets `< >` after the callable expression.</span></span>
<span data-ttu-id="8098b-354">Tato akce je obvykle zbytečná, protože Q# kompilátor odvodí skutečné typy.</span><span class="sxs-lookup"><span data-stu-id="8098b-354">This action is usually unnecessary as the Q# compiler infers the actual types.</span></span>
<span data-ttu-id="8098b-355">Nicméně *je* vyžadován pro [částečnou aplikaci](xref:microsoft.quantum.guide.operationsfunctions#partial-application) , pokud je argument typu bez parametrů ponechán neurčen.</span><span class="sxs-lookup"><span data-stu-id="8098b-355">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="8098b-356">To je užitečné také při předávání operací s různými funktory, které jsou schopné volat.</span><span class="sxs-lookup"><span data-stu-id="8098b-356">It is also useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="8098b-357">Například pokud `Func` má signatura `('T1, 'T2, 'T1) -> 'T2` a má signaturu `Op1` `Op2` `(Qubit[] => Unit is Adj)` a `Op3` má signaturu, `(Qubit[] => Unit)` pro vyvolání `Func` `Op1` jako první argument jako `Op2` druhý a `Op3` jako třetí:</span><span class="sxs-lookup"><span data-stu-id="8098b-357">For example, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="8098b-358">Specifikace typu je povinná `Op3` , protože a `Op1` má jiné typy, takže kompilátor bude považovat za dvojznačný bez specifikace.</span><span class="sxs-lookup"><span data-stu-id="8098b-358">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="8098b-359">Priorita operátorů</span><span class="sxs-lookup"><span data-stu-id="8098b-359">Operator Precedence</span></span>

* <span data-ttu-id="8098b-360">Všechny binární operátory jsou asociativní zprava, s výjimkou `^` .</span><span class="sxs-lookup"><span data-stu-id="8098b-360">All binary operators are right-associative, except for `^`.</span></span>

* <span data-ttu-id="8098b-361">Hranaté závorky, `[ ]` pro průřezy a indexování polí vytvořte vazby před libovolným operátorem.</span><span class="sxs-lookup"><span data-stu-id="8098b-361">Brackets, `[ ]`, for array slicing and indexing, bind before any operator.</span></span>

* <span data-ttu-id="8098b-362">Funktory `Adjoint` a `Controlled` BIND po vyřazení pole, ale před všemi ostatními operátory.</span><span class="sxs-lookup"><span data-stu-id="8098b-362">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

* <span data-ttu-id="8098b-363">Kulaté závorky pro operace a volání funkce se také vážou před libovolným operátorem, ale po vyřazení a funktory pole.</span><span class="sxs-lookup"><span data-stu-id="8098b-363">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="8098b-364">Q#operátory v pořadí podle priority, od nejvyšších po nejnižší:</span><span class="sxs-lookup"><span data-stu-id="8098b-364">Q# operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="8098b-365">Operátor</span><span class="sxs-lookup"><span data-stu-id="8098b-365">Operator</span></span> | <span data-ttu-id="8098b-366">Aritou</span><span class="sxs-lookup"><span data-stu-id="8098b-366">Arity</span></span> | <span data-ttu-id="8098b-367">Popis</span><span class="sxs-lookup"><span data-stu-id="8098b-367">Description</span></span> | <span data-ttu-id="8098b-368">Typy operandů</span><span class="sxs-lookup"><span data-stu-id="8098b-368">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="8098b-369">koncové`!`</span><span class="sxs-lookup"><span data-stu-id="8098b-369">trailing `!`</span></span> | <span data-ttu-id="8098b-370">Unární</span><span class="sxs-lookup"><span data-stu-id="8098b-370">Unary</span></span> | <span data-ttu-id="8098b-371">Rozbalení</span><span class="sxs-lookup"><span data-stu-id="8098b-371">Unwrap</span></span> | <span data-ttu-id="8098b-372">Libovolný uživatelsky definovaný typ</span><span class="sxs-lookup"><span data-stu-id="8098b-372">Any user-defined type</span></span>
 <span data-ttu-id="8098b-373">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="8098b-373">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="8098b-374">Unární</span><span class="sxs-lookup"><span data-stu-id="8098b-374">Unary</span></span> | <span data-ttu-id="8098b-375">Numerický negativní, bitový doplněk, logická negace</span><span class="sxs-lookup"><span data-stu-id="8098b-375">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="8098b-376">`Int`, nebo pro, pro, `BigInt` `Double` `-` `Int` `BigInt` `~~~` `Bool` pro`not`</span><span class="sxs-lookup"><span data-stu-id="8098b-376">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="8098b-377">Binární</span><span class="sxs-lookup"><span data-stu-id="8098b-377">Binary</span></span> | <span data-ttu-id="8098b-378">Celočíselný výkon</span><span class="sxs-lookup"><span data-stu-id="8098b-378">Integer power</span></span> | <span data-ttu-id="8098b-379">`Int`nebo `BigInt` pro základ `Int` pro exponent</span><span class="sxs-lookup"><span data-stu-id="8098b-379">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="8098b-380">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="8098b-380">`/`, `*`, `%`</span></span> | <span data-ttu-id="8098b-381">Binární</span><span class="sxs-lookup"><span data-stu-id="8098b-381">Binary</span></span> | <span data-ttu-id="8098b-382">Dělení, násobení, celočíselné zbytky</span><span class="sxs-lookup"><span data-stu-id="8098b-382">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="8098b-383">`Int`, `BigInt` nebo `Double` pro `/` a `*` , `Int` nebo `BigInt` pro`%`</span><span class="sxs-lookup"><span data-stu-id="8098b-383">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="8098b-384">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="8098b-384">`+`, `-`</span></span> | <span data-ttu-id="8098b-385">Binární</span><span class="sxs-lookup"><span data-stu-id="8098b-385">Binary</span></span> | <span data-ttu-id="8098b-386">Sčítání nebo řetězce a zřetězení polí, odčítání</span><span class="sxs-lookup"><span data-stu-id="8098b-386">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="8098b-387">`Int`, `BigInt` nebo `Double` , navíc `String` nebo libovolný typ pole pro`+`</span><span class="sxs-lookup"><span data-stu-id="8098b-387">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="8098b-388">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="8098b-388">`<<<`, `>>>`</span></span> | <span data-ttu-id="8098b-389">Binární</span><span class="sxs-lookup"><span data-stu-id="8098b-389">Binary</span></span> | <span data-ttu-id="8098b-390">Levý SHIFT, posun doprava</span><span class="sxs-lookup"><span data-stu-id="8098b-390">Left shift, right shift</span></span> | <span data-ttu-id="8098b-391">`Int` nebo `BigInt`</span><span class="sxs-lookup"><span data-stu-id="8098b-391">`Int` or `BigInt`</span></span>
 <span data-ttu-id="8098b-392">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="8098b-392">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="8098b-393">Binární</span><span class="sxs-lookup"><span data-stu-id="8098b-393">Binary</span></span> | <span data-ttu-id="8098b-394">Méně než, méně než nebo-rovno, větší než, větší než nebo rovno, větší než nebo rovno</span><span class="sxs-lookup"><span data-stu-id="8098b-394">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="8098b-395">`Int`, `BigInt` nebo`Double`</span><span class="sxs-lookup"><span data-stu-id="8098b-395">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="8098b-396">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="8098b-396">`==`, `!=`</span></span> | <span data-ttu-id="8098b-397">Binární</span><span class="sxs-lookup"><span data-stu-id="8098b-397">Binary</span></span> | <span data-ttu-id="8098b-398">rovná se, nerovná se porovnávání</span><span class="sxs-lookup"><span data-stu-id="8098b-398">equal, not-equal comparisons</span></span> | <span data-ttu-id="8098b-399">jakýkoli primitivní typ</span><span class="sxs-lookup"><span data-stu-id="8098b-399">any primitive type</span></span>
 `&&&` | <span data-ttu-id="8098b-400">Binární</span><span class="sxs-lookup"><span data-stu-id="8098b-400">Binary</span></span> | <span data-ttu-id="8098b-401">Bitový operátor AND</span><span class="sxs-lookup"><span data-stu-id="8098b-401">Bitwise AND</span></span> | <span data-ttu-id="8098b-402">`Int` nebo `BigInt`</span><span class="sxs-lookup"><span data-stu-id="8098b-402">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="8098b-403">Binární</span><span class="sxs-lookup"><span data-stu-id="8098b-403">Binary</span></span> | <span data-ttu-id="8098b-404">Bitový operátor XOR</span><span class="sxs-lookup"><span data-stu-id="8098b-404">Bitwise XOR</span></span> | <span data-ttu-id="8098b-405">`Int` nebo `BigInt`</span><span class="sxs-lookup"><span data-stu-id="8098b-405">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="8098b-406">Binární</span><span class="sxs-lookup"><span data-stu-id="8098b-406">Binary</span></span> | <span data-ttu-id="8098b-407">Bitový operátor OR</span><span class="sxs-lookup"><span data-stu-id="8098b-407">Bitwise OR</span></span> | <span data-ttu-id="8098b-408">`Int` nebo `BigInt`</span><span class="sxs-lookup"><span data-stu-id="8098b-408">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="8098b-409">Binární</span><span class="sxs-lookup"><span data-stu-id="8098b-409">Binary</span></span> | <span data-ttu-id="8098b-410">Logický operátor AND</span><span class="sxs-lookup"><span data-stu-id="8098b-410">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="8098b-411">Binární</span><span class="sxs-lookup"><span data-stu-id="8098b-411">Binary</span></span> | <span data-ttu-id="8098b-412">Logický operátor OR</span><span class="sxs-lookup"><span data-stu-id="8098b-412">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="8098b-413">Binární/Ternární</span><span class="sxs-lookup"><span data-stu-id="8098b-413">Binary/Ternary</span></span> | <span data-ttu-id="8098b-414">Operátor rozsahu</span><span class="sxs-lookup"><span data-stu-id="8098b-414">Range operator</span></span> | `Int`
 <span data-ttu-id="8098b-415">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="8098b-415">`?` `|`</span></span> | <span data-ttu-id="8098b-416">Ternární</span><span class="sxs-lookup"><span data-stu-id="8098b-416">Ternary</span></span> | <span data-ttu-id="8098b-417">Podmíněné</span><span class="sxs-lookup"><span data-stu-id="8098b-417">Conditional</span></span> | <span data-ttu-id="8098b-418">`Bool`na levé straně</span><span class="sxs-lookup"><span data-stu-id="8098b-418">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="8098b-419">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="8098b-419">`w/` `<-`</span></span> | <span data-ttu-id="8098b-420">Ternární</span><span class="sxs-lookup"><span data-stu-id="8098b-420">Ternary</span></span> | <span data-ttu-id="8098b-421">Kopírování a aktualizace</span><span class="sxs-lookup"><span data-stu-id="8098b-421">Copy-and-update</span></span> | <span data-ttu-id="8098b-422">Viz [výrazy pro kopírování a aktualizaci](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="8098b-422">See [Copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="8098b-423">Další kroky</span><span class="sxs-lookup"><span data-stu-id="8098b-423">Next steps</span></span>

<span data-ttu-id="8098b-424">Teď, když můžete pracovat s výrazy v Q# , přejděte k [operacím a funkcím Q# v](xref:microsoft.quantum.guide.operationsfunctions) , abyste se dozvěděli, jak definovat a volat operace a funkce.</span><span class="sxs-lookup"><span data-stu-id="8098b-424">Now that you can work with expressions in Q#, move on to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
