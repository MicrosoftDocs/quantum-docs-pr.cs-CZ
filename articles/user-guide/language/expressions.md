---
title: 'Výrazy typu v Q #'
description: 'Pochopte, jak zadat, odkazovat a kombinovat konstanty, proměnné, operátory, operace a funkce jako výrazy v Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: c4b2cc0bed44ffdfb191ba522d6526959e7c6708
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327301"
---
# <a name="type-expressions-in-q"></a><span data-ttu-id="60e84-103">Výrazy typu v Q #</span><span class="sxs-lookup"><span data-stu-id="60e84-103">Type Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="60e84-104">Číselné výrazy</span><span class="sxs-lookup"><span data-stu-id="60e84-104">Numeric Expressions</span></span>

<span data-ttu-id="60e84-105">Číselné výrazy jsou výrazy typu `Int` , `BigInt` nebo `Double` .</span><span class="sxs-lookup"><span data-stu-id="60e84-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="60e84-106">To znamená, že jsou buď celá čísla, nebo čísla s plovoucí desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="60e84-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="60e84-107">`Int`literály v Q # jsou zapsány jednoduše jako sekvence číslic.</span><span class="sxs-lookup"><span data-stu-id="60e84-107">`Int` literals in Q# are written simply as a sequence of digits.</span></span>
<span data-ttu-id="60e84-108">Šestnáctková a binární celá čísla jsou podporována `0x` `0b` předponou a v uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="60e84-108">Hexadecimal and binary integers are supported with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="60e84-109">`BigInt`literály v Q # jsou napsané s koncovým znakem `l` nebo `L` příponou.</span><span class="sxs-lookup"><span data-stu-id="60e84-109">`BigInt` literals in Q# are written with a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="60e84-110">Předpona "0x" je podporována hexadecimálními velkými čísly.</span><span class="sxs-lookup"><span data-stu-id="60e84-110">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="60e84-111">Následující jsou tedy všechna platná použití `BigInt` literálů:</span><span class="sxs-lookup"><span data-stu-id="60e84-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="60e84-112">`Double`literály v Q # jsou čísla s plovoucí desetinnou čárkou napsaná pomocí desítkových číslic.</span><span class="sxs-lookup"><span data-stu-id="60e84-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="60e84-113">Můžou se zapisovat pomocí desetinné čárky, `.` , nebo exponenciální části označené písmenem "e" nebo "e" (po tom, že jsou platné pouze možné záporné znaménko a desítkové číslice).</span><span class="sxs-lookup"><span data-stu-id="60e84-113">They can be written with a decimal point, `.`, and/or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="60e84-114">Níže jsou uvedené platné `Double` literály: `0.0` , `1.2e5` , `1e-5` .</span><span class="sxs-lookup"><span data-stu-id="60e84-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="60e84-115">Vzhledem k výrazu pole libovolného typu elementu `Int` může být výraz vytvořen pomocí [`Length`](xref:microsoft.quantum.core.length) předdefinované funkce s výrazem pole uzavřeným v závorkách `(` a `)` .</span><span class="sxs-lookup"><span data-stu-id="60e84-115">Given an array expression of any element type, an `Int` expression may be formed using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="60e84-116">Například pokud `a` je svázána s polem, pak `Length(a)` je celočíselný výraz.</span><span class="sxs-lookup"><span data-stu-id="60e84-116">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="60e84-117">Pokud `b` je pole polí celých čísel, `Int[][]` , pak `Length(b)` je počet dílčích polí v a `b` `Length(b[1])` je počet celých čísel ve druhém dílčím poli v `b` .</span><span class="sxs-lookup"><span data-stu-id="60e84-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="60e84-118">Zadané dva číselné výrazy stejného typu, binární operátory `+` ,, `-` `*` a `/` mohou být použity k vytvoření nového číselného výrazu.</span><span class="sxs-lookup"><span data-stu-id="60e84-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="60e84-119">Typ nového výrazu bude stejný jako u typů výrazů prvků.</span><span class="sxs-lookup"><span data-stu-id="60e84-119">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="60e84-120">Zadaným dvěma celočíselnými výrazy lze binární operátor `^` (napájení) použít k vytvoření nového celočíselného výrazu.</span><span class="sxs-lookup"><span data-stu-id="60e84-120">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="60e84-121">Podobně `^` lze použít se dvěma dvojitými výrazy pro vytvoření nového dvojitého výrazu.</span><span class="sxs-lookup"><span data-stu-id="60e84-121">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="60e84-122">Nakonec `^` lze použít s velkým celým číslem na levé straně a celým číslem na pravé straně k vytvoření nového výrazu Big Integer.</span><span class="sxs-lookup"><span data-stu-id="60e84-122">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="60e84-123">V takovém případě se druhý parametr musí vejít do 32 bitů; v takovém případě se vyvolá Běhová chyba.</span><span class="sxs-lookup"><span data-stu-id="60e84-123">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="60e84-124">Předané dva celočíselné nebo velké celočíselné výrazy mohou být vytvořeny pomocí `%` operátorů (modulo), `&&&` (bitové a), `|||` (bitových nebo) nebo `^^^` (bitových operátorů XOR).</span><span class="sxs-lookup"><span data-stu-id="60e84-124">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="60e84-125">Pro vytvoření nového výrazu stejného typu, který je použit jako levý výraz, lze použít buď celočíselný nebo velký celočíselný výraz na levé straně, a výraz typu Integer na pravé straně, `<<<` operátor (aritmetický levý SHIFT) nebo `>>>` (aritmetický posun Shift).</span><span class="sxs-lookup"><span data-stu-id="60e84-125">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="60e84-126">Druhý parametr (velikost posunu) pro operaci posunu musí být větší nebo roven nule. chování pro záporné hodnoty posunutí není definováno.</span><span class="sxs-lookup"><span data-stu-id="60e84-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="60e84-127">Velikost SHIFT pro buď operaci posunutí musí být také do 32 bitů. v takovém případě se vyvolá Běhová chyba.</span><span class="sxs-lookup"><span data-stu-id="60e84-127">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="60e84-128">Pokud číslo, které má být posunuto, je celé číslo, hodnota posunutí je interpretována `mod 64` ; to znamená, že posun 1 a posun 65 mají stejný účinek.</span><span class="sxs-lookup"><span data-stu-id="60e84-128">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="60e84-129">Pro celočíselné i velké celočíselné hodnoty jsou posunuty aritmetické operace.</span><span class="sxs-lookup"><span data-stu-id="60e84-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="60e84-130">Posunutí záporné hodnoty doleva nebo doprava bude mít za následek záporné číslo.</span><span class="sxs-lookup"><span data-stu-id="60e84-130">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="60e84-131">To znamená, že posun jednoho kroku doleva nebo doprava je přesně stejný jako násobení nebo dělení 2, v uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="60e84-131">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="60e84-132">Celočíselné dělení a celočíselné zbytky se řídí stejným chováním pro záporná čísla jako C#.</span><span class="sxs-lookup"><span data-stu-id="60e84-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="60e84-133">To znamená, že `a % b` vždy bude mít stejné znaménko jako `a` a `b * (a / b) + a % b` bude vždy rovno `a` .</span><span class="sxs-lookup"><span data-stu-id="60e84-133">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="60e84-134">Příklad:</span><span class="sxs-lookup"><span data-stu-id="60e84-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="60e84-135">5</span><span class="sxs-lookup"><span data-stu-id="60e84-135">5</span></span> | <span data-ttu-id="60e84-136">2</span><span class="sxs-lookup"><span data-stu-id="60e84-136">2</span></span> | <span data-ttu-id="60e84-137">2</span><span class="sxs-lookup"><span data-stu-id="60e84-137">2</span></span> | <span data-ttu-id="60e84-138">1</span><span class="sxs-lookup"><span data-stu-id="60e84-138">1</span></span>
 <span data-ttu-id="60e84-139">5</span><span class="sxs-lookup"><span data-stu-id="60e84-139">5</span></span> | <span data-ttu-id="60e84-140">-2</span><span class="sxs-lookup"><span data-stu-id="60e84-140">-2</span></span> | <span data-ttu-id="60e84-141">-2</span><span class="sxs-lookup"><span data-stu-id="60e84-141">-2</span></span> | <span data-ttu-id="60e84-142">1</span><span class="sxs-lookup"><span data-stu-id="60e84-142">1</span></span>
 <span data-ttu-id="60e84-143">-5</span><span class="sxs-lookup"><span data-stu-id="60e84-143">-5</span></span> | <span data-ttu-id="60e84-144">2</span><span class="sxs-lookup"><span data-stu-id="60e84-144">2</span></span> | <span data-ttu-id="60e84-145">-2</span><span class="sxs-lookup"><span data-stu-id="60e84-145">-2</span></span> | <span data-ttu-id="60e84-146">-1</span><span class="sxs-lookup"><span data-stu-id="60e84-146">-1</span></span>
 <span data-ttu-id="60e84-147">-5</span><span class="sxs-lookup"><span data-stu-id="60e84-147">-5</span></span> | <span data-ttu-id="60e84-148">-2</span><span class="sxs-lookup"><span data-stu-id="60e84-148">-2</span></span> | <span data-ttu-id="60e84-149">2</span><span class="sxs-lookup"><span data-stu-id="60e84-149">2</span></span> | <span data-ttu-id="60e84-150">-1</span><span class="sxs-lookup"><span data-stu-id="60e84-150">-1</span></span>

<span data-ttu-id="60e84-151">Dělení velkých celých čísel a Modulus funguje stejným způsobem.</span><span class="sxs-lookup"><span data-stu-id="60e84-151">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="60e84-152">V případě libovolného číselného výrazu může být výraz New vytvořen pomocí `-` unárního operátoru.</span><span class="sxs-lookup"><span data-stu-id="60e84-152">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="60e84-153">Nový výraz bude stejného typu jako výraz prvku.</span><span class="sxs-lookup"><span data-stu-id="60e84-153">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="60e84-154">S ohledem na libovolný celočíselný nebo velký celočíselný výraz může být nový výraz stejného typu vytvořen pomocí `~~~` unárního operátoru (bitového doplňku).</span><span class="sxs-lookup"><span data-stu-id="60e84-154">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="60e84-155">Výrazy logických hodnot</span><span class="sxs-lookup"><span data-stu-id="60e84-155">Boolean Expressions</span></span>

<span data-ttu-id="60e84-156">Dvě `Bool` hodnoty literálu jsou `true` a `false` .</span><span class="sxs-lookup"><span data-stu-id="60e84-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="60e84-157">Vzhledem k jakýmkoliv dvěma výrazům stejného primitivního typu lze `==` `!=` použít binární operátory a k vytvoření `Bool` výrazu.</span><span class="sxs-lookup"><span data-stu-id="60e84-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="60e84-158">Výraz bude true, pokud jsou dva výrazy stejné, a false, pokud ne.</span><span class="sxs-lookup"><span data-stu-id="60e84-158">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="60e84-159">Hodnoty uživatelsky definovaných typů nelze porovnat, lze porovnat pouze jejich nezabalené hodnoty.</span><span class="sxs-lookup"><span data-stu-id="60e84-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="60e84-160">Například pomocí operátoru "Unwrap" `!` (popsaný v podrobnostech na [typech v Q #](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span><span class="sxs-lookup"><span data-stu-id="60e84-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="60e84-161">Porovnání rovnosti pro `Qubit` hodnoty je rovnost identity; to znamená, zda dva výrazy identifikují stejný qubit.</span><span class="sxs-lookup"><span data-stu-id="60e84-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="60e84-162">Stav obou qubits se neshoduje, nepoužívá se, neměří ani nemění pomocí tohoto porovnání.</span><span class="sxs-lookup"><span data-stu-id="60e84-162">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="60e84-163">Porovnání rovnosti pro `Double` hodnoty může být zavádějící z důvodu zaoblení efektů.</span><span class="sxs-lookup"><span data-stu-id="60e84-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="60e84-164">Například `49.0 * (1.0/49.0) != 1.0` .</span><span class="sxs-lookup"><span data-stu-id="60e84-164">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="60e84-165">Vzhledem k tomu, že jsou zadány dva číselné výrazy, binární operátory `>` , `<` , `>=` a lze `<=` použít k vytvoření nového logického výrazu, který je true, pokud je první výraz v tomto pořadí větší než, menší než nebo roven nebo menší nebo roven druhému výrazu.</span><span class="sxs-lookup"><span data-stu-id="60e84-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="60e84-166">Za daných dvou logických výrazů lze `and` `or` binární operátory a použít k vytvoření nového logického výrazu, který má hodnotu true, pokud oba výrazy (odp. buď nebo obojí z) jsou pravdivé.</span><span class="sxs-lookup"><span data-stu-id="60e84-166">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="60e84-167">S ohledem na logický výraz `not` může být unární operátor použit k vytvoření nového logického výrazu, který je true, pokud je výraz prvku false.</span><span class="sxs-lookup"><span data-stu-id="60e84-167">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="60e84-168">Řetězcové výrazy</span><span class="sxs-lookup"><span data-stu-id="60e84-168">String Expressions</span></span>

<span data-ttu-id="60e84-169">Q # povoluje použití řetězců v `fail` příkazu (vysvětleno v [toku řízení](xref:microsoft.quantum.guide.controlflow#fail-statement)) a ve [`Message`](xref:microsoft.quantum.intrinsic.message) funkci Standard.</span><span class="sxs-lookup"><span data-stu-id="60e84-169">Q# allows strings to be used in the `fail` statement (explained at [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span>
<span data-ttu-id="60e84-170">Konkrétní chování druhé závisí na použitém simulátoru, ale obvykle zapisuje zprávu do hostitelské konzole při volání během programu Q #.</span><span class="sxs-lookup"><span data-stu-id="60e84-170">The specific behavior of the latter depends on the simulator being used, but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="60e84-171">Řetězce v Q # jsou buď literály nebo interpolované řetězce.</span><span class="sxs-lookup"><span data-stu-id="60e84-171">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="60e84-172">Řetězcové literály jsou podobně jako jednoduché řetězcové literály ve většině jazyků: sekvence znaků Unicode uzavřených do dvojitých uvozovek, `"` .</span><span class="sxs-lookup"><span data-stu-id="60e84-172">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="60e84-173">Uvnitř řetězce je možné znak zpětného lomítka `\` použít k úniku znaku dvojité uvozovky a vložit nový řádek jako znak návratu na začátek řádku `\n` `\r` a kartu jako `\t` .</span><span class="sxs-lookup"><span data-stu-id="60e84-173">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="60e84-174">Například:</span><span class="sxs-lookup"><span data-stu-id="60e84-174">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="60e84-175">Interpolované řetězce</span><span class="sxs-lookup"><span data-stu-id="60e84-175">Interpolated strings</span></span>

<span data-ttu-id="60e84-176">Syntaxe Q # pro řetězcové interpolace je podmnožinou syntaxe jazyka C#, ale je zde shrnuto klíčové body, které se týkají Q #.</span><span class="sxs-lookup"><span data-stu-id="60e84-176">The Q# syntax for string interpolations is a subset of the C# syntax, but we summarize here the key points as they pertain to Q#.</span></span>
<span data-ttu-id="60e84-177">Hlavní rozdíly jsou popsány níže.</span><span class="sxs-lookup"><span data-stu-id="60e84-177">The main distinctions are discussed below.</span></span>

<span data-ttu-id="60e84-178">Pro identifikaci řetězcového literálu jako interpolované řetězce, předřaďte ho `$` symbolem.</span><span class="sxs-lookup"><span data-stu-id="60e84-178">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span>
<span data-ttu-id="60e84-179">Mezi znakem `$` a `"` , který začíná řetězcovým literálem, nelze zadat prázdný znak.</span><span class="sxs-lookup"><span data-stu-id="60e84-179">You cannot have any white space between the `$`and the `"` that starts a string literal.</span></span>

<span data-ttu-id="60e84-180">Následuje základní příklad použití [`Message`](xref:microsoft.quantum.intrinsic.message) funkce k zápisu výsledku měření do konzoly spolu s dalšími výrazy Q #.</span><span class="sxs-lookup"><span data-stu-id="60e84-180">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
<span data-ttu-id="60e84-181">Libovolný platný výraz Q # se může objevit v interpolované řetězci.</span><span class="sxs-lookup"><span data-stu-id="60e84-181">Any valid Q# expression may appear in an interpolated string.</span></span>

<span data-ttu-id="60e84-182">Další podrobnosti o syntaxi jazyka C# lze nalézt v [*řetězci interpolované řetězce*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span><span class="sxs-lookup"><span data-stu-id="60e84-182">Further details on the C# syntax can be found at [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>
<span data-ttu-id="60e84-183">Nejvýraznějším rozdílem je, že Q # nepodporuje doslovné (víceřádkové) interpolované řetězce.</span><span class="sxs-lookup"><span data-stu-id="60e84-183">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="60e84-184">Výrazy uvnitř interpolované řetězce následují syntax Q #, nikoli syntaxe jazyka C#.</span><span class="sxs-lookup"><span data-stu-id="60e84-184">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="60e84-185">Výrazy rozsahu</span><span class="sxs-lookup"><span data-stu-id="60e84-185">Range Expressions</span></span>

<span data-ttu-id="60e84-186">S ohledem na tři `Int` výrazy `start` , `step` , `stop` a `start .. step .. stop` je výraz rozsahu, jehož prvním prvkem je `start` , druhý prvek je, `start+step` třetí prvek je `start+step+step` atd., dokud `stop` není předán.</span><span class="sxs-lookup"><span data-stu-id="60e84-186">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="60e84-187">Rozsah může být prázdný, pokud je instance například `step` pozitivní a `stop < start` .</span><span class="sxs-lookup"><span data-stu-id="60e84-187">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="60e84-188">Poslední prvek rozsahu bude, `stop` Pokud rozdíl mezi `start` a `stop` je integrální násobek `step` ; to znamená, že rozsah je zahrnut na obou koncích.</span><span class="sxs-lookup"><span data-stu-id="60e84-188">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="60e84-189">Při daných dvou `Int` výrazech `start` a `stop` `start .. stop` je výraz rozsahu, který je roven `start .. 1 .. stop` .</span><span class="sxs-lookup"><span data-stu-id="60e84-189">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="60e84-190">Všimněte si, že předpokládaná `step` je + 1, i když `stop` je menší než `start` ; v takovém případě je rozsah prázdný.</span><span class="sxs-lookup"><span data-stu-id="60e84-190">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="60e84-191">Mezi příklady oblastí patří:</span><span class="sxs-lookup"><span data-stu-id="60e84-191">Some example ranges are:</span></span>

- <span data-ttu-id="60e84-192">`1..3`je rozsah 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="60e84-192">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="60e84-193">`2..2..5`je rozsah 2, 4.</span><span class="sxs-lookup"><span data-stu-id="60e84-193">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="60e84-194">`2..2..6`je rozsah 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="60e84-194">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="60e84-195">`6..-2..2`je rozsah 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="60e84-195">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="60e84-196">`2..1`je prázdný rozsah.</span><span class="sxs-lookup"><span data-stu-id="60e84-196">`2..1` is the empty range.</span></span>
- <span data-ttu-id="60e84-197">`2..6..7`je rozsah 2.</span><span class="sxs-lookup"><span data-stu-id="60e84-197">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="60e84-198">`2..2..1`je prázdný rozsah.</span><span class="sxs-lookup"><span data-stu-id="60e84-198">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="60e84-199">`1..-1..2`je prázdný rozsah.</span><span class="sxs-lookup"><span data-stu-id="60e84-199">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="60e84-200">Výrazy qubit</span><span class="sxs-lookup"><span data-stu-id="60e84-200">Qubit Expressions</span></span>

<span data-ttu-id="60e84-201">Jediné `Qubit` výrazy jsou symboly, které jsou vázány na `Qubit` hodnoty nebo prvky pole `Qubit` polí.</span><span class="sxs-lookup"><span data-stu-id="60e84-201">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="60e84-202">Neexistují žádné `Qubit` literály.</span><span class="sxs-lookup"><span data-stu-id="60e84-202">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="60e84-203">Výrazy Pauli</span><span class="sxs-lookup"><span data-stu-id="60e84-203">Pauli Expressions</span></span>

<span data-ttu-id="60e84-204">Čtyři `Pauli` hodnoty, `PauliI` ,, `PauliX` `PauliY` a `PauliZ` , jsou platné `Pauli` výrazy.</span><span class="sxs-lookup"><span data-stu-id="60e84-204">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="60e84-205">Kromě toho jsou jedinými `Pauli` výrazy symboly, které jsou vázány na `Pauli` hodnoty nebo prvky pole `Pauli` polí.</span><span class="sxs-lookup"><span data-stu-id="60e84-205">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="60e84-206">Výsledné výrazy</span><span class="sxs-lookup"><span data-stu-id="60e84-206">Result Expressions</span></span>

<span data-ttu-id="60e84-207">Dvě `Result` hodnoty `One` a `Zero` jsou platné `Result` výrazy.</span><span class="sxs-lookup"><span data-stu-id="60e84-207">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="60e84-208">Kromě toho jsou jedinými `Result` výrazy symboly, které jsou vázány na `Result` hodnoty nebo prvky pole `Result` polí.</span><span class="sxs-lookup"><span data-stu-id="60e84-208">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="60e84-209">Konkrétně si všimněte, že není `One` stejný jako celé číslo `1` a mezi nimi není přímý převod.</span><span class="sxs-lookup"><span data-stu-id="60e84-209">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="60e84-210">Totéž platí pro `Zero` a `0` .</span><span class="sxs-lookup"><span data-stu-id="60e84-210">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="60e84-211">Výrazy řazené kolekce členů</span><span class="sxs-lookup"><span data-stu-id="60e84-211">Tuple Expressions</span></span>

<span data-ttu-id="60e84-212">Literál řazené kolekce členů je sekvence výrazů prvků příslušného typu, které jsou odděleny čárkami a uzavřeny v `(` a `)` .</span><span class="sxs-lookup"><span data-stu-id="60e84-212">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="60e84-213">Například `(1, One)` je `(Int, Result)` výraz.</span><span class="sxs-lookup"><span data-stu-id="60e84-213">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="60e84-214">Kromě literálů jsou jedinými výrazy řazené kolekce členů symboly, které jsou vázány na hodnoty řazené kolekce členů, prvky pole řazené kolekce členů a volání, která vrací řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="60e84-214">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="60e84-215">Výrazy uživatelsky definovaného typu</span><span class="sxs-lookup"><span data-stu-id="60e84-215">User-Defined Type Expressions</span></span>

<span data-ttu-id="60e84-216">Literál uživatelsky definovaného typu se skládá z názvu typu následovaného literálem řazené kolekce členů základního typu řazené kolekce členů typu.</span><span class="sxs-lookup"><span data-stu-id="60e84-216">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="60e84-217">Například pokud `IntPair` je uživatelem definovaný typ založený na `(Int, Int)` , pak `IntPair(2, 3)` by byl platným literálem tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="60e84-217">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="60e84-218">Kromě literálů jsou jedinými výrazy uživatelsky definovaného typu symboly, které jsou vázány na hodnoty daného typu, prvky pole polí daného typu a volání, která vrací tento typ.</span><span class="sxs-lookup"><span data-stu-id="60e84-218">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="60e84-219">Rozbalit výrazy</span><span class="sxs-lookup"><span data-stu-id="60e84-219">Unwrap Expressions</span></span>

<span data-ttu-id="60e84-220">V Q # se operátor rozbalení označuje jako koncová značka vykřičník `!` .</span><span class="sxs-lookup"><span data-stu-id="60e84-220">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="60e84-221">Například pokud `IntPair` je uživatelem definovaný typ s podkladovým typem `(Int, Int)` a `s` byl proměnnou s hodnotou `IntPair(2, 3)` , potom `s!` by byl `(2, 3)` .</span><span class="sxs-lookup"><span data-stu-id="60e84-221">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2, 3)`, then `s!` would be `(2, 3)`.</span></span>

<span data-ttu-id="60e84-222">Pro uživatelsky definované typy definované v jiných uživatelsky definovaných typech.</span><span class="sxs-lookup"><span data-stu-id="60e84-222">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="60e84-223">operátor rozbalení může být opakován; například `s!!` označuje zdvojnásobně nezabalenou hodnotu `s` .</span><span class="sxs-lookup"><span data-stu-id="60e84-223">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="60e84-224">Proto, pokud `WrappedPair` je uživatelem definovaný typ s podkladovým typem `IntPair` , a `t` je proměnná s hodnotou `WrappedPair(IntPair(1,2))` , potom `t!!` by byla `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="60e84-224">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="60e84-225">`!`Operátor má vyšší prioritu než všechny ostatní operátory, kromě `[]` indexace pole a řezů.</span><span class="sxs-lookup"><span data-stu-id="60e84-225">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="60e84-226">`!`a dá se `[]` vytvořit vazba. to znamená, že `a[i]![3]` by měl být čten jako `((a[i])!)[3]` : Vezměte `i` "element" `a` , rozbalíte ho a pak Získejte třetí prvek nezabalené hodnoty (který musí být pole).</span><span class="sxs-lookup"><span data-stu-id="60e84-226">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="60e84-227">Priorita `!` operátoru má jeden dopad, který nemusí být zřejmý.</span><span class="sxs-lookup"><span data-stu-id="60e84-227">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="60e84-228">Vrátí-li funkce nebo operace hodnotu, která je poté nezabalena, musí být volání funkce nebo operace uzavřena v závorkách, aby se argumenty řazené kolekce členů navázaly na volání, nikoli na rozbalení.</span><span class="sxs-lookup"><span data-stu-id="60e84-228">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="60e84-229">Příklad:</span><span class="sxs-lookup"><span data-stu-id="60e84-229">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="60e84-230">Výrazy Array</span><span class="sxs-lookup"><span data-stu-id="60e84-230">Array Expressions</span></span>

<span data-ttu-id="60e84-231">Literál pole je sekvence jednoho nebo více výrazů prvků, které jsou odděleny čárkami a uzavřeny v `[` a `]` .</span><span class="sxs-lookup"><span data-stu-id="60e84-231">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="60e84-232">Všechny elementy musí být kompatibilní se stejným typem.</span><span class="sxs-lookup"><span data-stu-id="60e84-232">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="60e84-233">Při zadání dvou polí stejného typu `+` může být binární operátor použit k vytvoření nového pole, které je zřetězením dvou polí.</span><span class="sxs-lookup"><span data-stu-id="60e84-233">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="60e84-234">Například `[1,2,3] + [4,5,6]` je `[1,2,3,4,5,6]` .</span><span class="sxs-lookup"><span data-stu-id="60e84-234">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="60e84-235">Vytvoření pole</span><span class="sxs-lookup"><span data-stu-id="60e84-235">Array Creation</span></span>

<span data-ttu-id="60e84-236">Pro daný typ a `Int` výraz lze `new` operátor použít k přidělení nového pole dané velikosti.</span><span class="sxs-lookup"><span data-stu-id="60e84-236">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="60e84-237">Například `new Int[i + 1]` by bylo přiděleno nové `Int` pole s `i + 1` prvky.</span><span class="sxs-lookup"><span data-stu-id="60e84-237">For instance, `new Int[i + 1]` would allocate a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="60e84-238">Prázdné literály pole, `[]` nejsou povoleny.</span><span class="sxs-lookup"><span data-stu-id="60e84-238">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="60e84-239">Místo toho použití `new ★[0]` , kde `★` je jako zástupný symbol pro vhodný typ, umožňuje vytvořit požadované pole s nulovou délkou.</span><span class="sxs-lookup"><span data-stu-id="60e84-239">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="60e84-240">Prvky nového pole jsou inicializovány na výchozí hodnotu závislou na typu.</span><span class="sxs-lookup"><span data-stu-id="60e84-240">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="60e84-241">Ve většině případů se jedná o nějakou odchylku nuly.</span><span class="sxs-lookup"><span data-stu-id="60e84-241">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="60e84-242">Pro qubits a volat, které jsou odkazy na entity, neexistuje přiměřená výchozí hodnota.</span><span class="sxs-lookup"><span data-stu-id="60e84-242">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="60e84-243">Proto pro tyto typy je výchozí hodnota neplatný odkaz, který nelze použít, aniž by došlo k chybě za běhu.</span><span class="sxs-lookup"><span data-stu-id="60e84-243">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="60e84-244">To se podobá odkazu s hodnotou null v jazycích, jako je C# nebo Java.</span><span class="sxs-lookup"><span data-stu-id="60e84-244">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="60e84-245">Pole obsahující qubits nebo volat musí být správně inicializována s jinými než výchozími hodnotami, aby bylo možné jejich prvky bezpečně použít.</span><span class="sxs-lookup"><span data-stu-id="60e84-245">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="60e84-246">Vhodné inicializační rutiny lze nalézt v <xref:microsoft.quantum.arrays> .</span><span class="sxs-lookup"><span data-stu-id="60e84-246">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="60e84-247">Výchozí hodnoty pro každý typ jsou:</span><span class="sxs-lookup"><span data-stu-id="60e84-247">The default values for each type are:</span></span>

<span data-ttu-id="60e84-248">Typ</span><span class="sxs-lookup"><span data-stu-id="60e84-248">Type</span></span> | <span data-ttu-id="60e84-249">Výchozí</span><span class="sxs-lookup"><span data-stu-id="60e84-249">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="60e84-250">_Neplatný qubit_</span><span class="sxs-lookup"><span data-stu-id="60e84-250">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="60e84-251">Prázdný rozsah`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="60e84-251">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="60e84-252">_Neplatný volat_</span><span class="sxs-lookup"><span data-stu-id="60e84-252">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="60e84-253">Typy řazené kolekce členů jsou inicializovány elementem po prvku.</span><span class="sxs-lookup"><span data-stu-id="60e84-253">Tuple types are initialized element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="60e84-254">Prvky pole</span><span class="sxs-lookup"><span data-stu-id="60e84-254">Array Elements</span></span>

<span data-ttu-id="60e84-255">S ohledem na výraz pole a `Int` výraz může být nový výraz vytvořen pomocí `[` `]` operátoru a elementu pole.</span><span class="sxs-lookup"><span data-stu-id="60e84-255">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="60e84-256">Nový výraz bude stejného typu jako typ prvku pole.</span><span class="sxs-lookup"><span data-stu-id="60e84-256">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="60e84-257">Například pokud `a` je svázán s polem `Double` s, pak `a[4]` je `Double` výraz.</span><span class="sxs-lookup"><span data-stu-id="60e84-257">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="60e84-258">Pokud výraz pole není jednoduchý identifikátor, musí být uzavřen v závorkách, aby bylo možné vybrat prvek.</span><span class="sxs-lookup"><span data-stu-id="60e84-258">If the array expression is not a simple identifier, it must be enclosed in parentheses in order to select an element.</span></span>
<span data-ttu-id="60e84-259">Například pokud `a` a `b` jsou obě pole třídy `Int` s, prvek ze zřetězení by byl vyjádřen jako:</span><span class="sxs-lookup"><span data-stu-id="60e84-259">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="60e84-260">Všechna pole v Q # jsou založená na nule.</span><span class="sxs-lookup"><span data-stu-id="60e84-260">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="60e84-261">To znamená, že první prvek pole `a` je vždy `a[0]` .</span><span class="sxs-lookup"><span data-stu-id="60e84-261">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="60e84-262">Řezy pole</span><span class="sxs-lookup"><span data-stu-id="60e84-262">Array Slices</span></span>

<span data-ttu-id="60e84-263">S ohledem na výraz pole a `Range` výraz může být výraz New vytvořen pomocí `[` `]` operátoru a řezu Array.</span><span class="sxs-lookup"><span data-stu-id="60e84-263">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="60e84-264">Nový výraz bude stejný jako typ pole a bude obsahovat položky pole indexované prvky `Range` , v pořadí definovaném `Range` .</span><span class="sxs-lookup"><span data-stu-id="60e84-264">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="60e84-265">Například pokud `a` je svázána s polem `Double` s, pak `a[3..-1..0]` je `Double[]` výraz, který obsahuje první čtyři prvky, `a` ale v obráceném pořadí, jak jsou uvedeny v `a` .</span><span class="sxs-lookup"><span data-stu-id="60e84-265">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="60e84-266">Pokud `Range` je pole prázdné, bude výsledný řez pole nulovou délkou.</span><span class="sxs-lookup"><span data-stu-id="60e84-266">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="60e84-267">Stejně jako u odkazů na prvky pole, pokud výraz pole není jednoduchý identifikátor, musí být uzavřeny závorky, aby bylo možné vytvořit řezy.</span><span class="sxs-lookup"><span data-stu-id="60e84-267">Just as with referencing array elements, if the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="60e84-268">Pokud `a` a `b` jsou obě pole typu `Int` s, řez z zřetězení by byl vyjádřen jako:</span><span class="sxs-lookup"><span data-stu-id="60e84-268">If `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="60e84-269">Odvozené počáteční/koncové hodnoty</span><span class="sxs-lookup"><span data-stu-id="60e84-269">Inferred start/end values</span></span>

<span data-ttu-id="60e84-270">Od naší verze 0,8 podporujeme kontextové výrazy pro průřezy rozsahu.</span><span class="sxs-lookup"><span data-stu-id="60e84-270">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="60e84-271">Konkrétně je možné vynechat počáteční a koncové hodnoty rozsahu v kontextu výrazu průřezu rozsahu.</span><span class="sxs-lookup"><span data-stu-id="60e84-271">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="60e84-272">V takovém případě kompilátor použije následující pravidla k odvodit zamýšlené oddělovače pro daný rozsah.</span><span class="sxs-lookup"><span data-stu-id="60e84-272">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="60e84-273">Pokud je třeba počáteční hodnota rozsahu vynechána, pak odvozená počáteční hodnota.</span><span class="sxs-lookup"><span data-stu-id="60e84-273">For example, if the range start value is omitted,  then the inferred start value</span></span> 
- <span data-ttu-id="60e84-274">je nula, pokud není zadán žádný krok, nebo je zadaný krok kladný a</span><span class="sxs-lookup"><span data-stu-id="60e84-274">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="60e84-275">je délka pole v průřezu minus jedna, pokud je zadaný krok záporný.</span><span class="sxs-lookup"><span data-stu-id="60e84-275">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="60e84-276">Pokud je hodnota konec rozsahu vynechána, pak odvozená koncová hodnota</span><span class="sxs-lookup"><span data-stu-id="60e84-276">If the range end value is omitted,  then the inferred end value</span></span> 
- <span data-ttu-id="60e84-277">je délka pole řezu minus jedna, pokud není zadán žádný krok, nebo je zadaný krok kladný a</span><span class="sxs-lookup"><span data-stu-id="60e84-277">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="60e84-278">je nula, pokud je zadaný krok záporný.</span><span class="sxs-lookup"><span data-stu-id="60e84-278">is zero if the specified step is negative.</span></span> 

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="60e84-279">Výrazy kopírování a aktualizace</span><span class="sxs-lookup"><span data-stu-id="60e84-279">Copy-and-Update Expressions</span></span>

<span data-ttu-id="60e84-280">Vzhledem k tomu, že všechny typy Q # jsou typy hodnot – s qubitsem, který vychází z trochu speciální role, je vytvořena "kopie", když je hodnota vázána na symbol, nebo když je symbol převázán.</span><span class="sxs-lookup"><span data-stu-id="60e84-280">Since all Q# types are value types — with the qubits taking a somewhat special role —formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="60e84-281">To znamená, že chování Q # je stejné jako při vytvoření kopie při přiřazení.</span><span class="sxs-lookup"><span data-stu-id="60e84-281">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span>
<span data-ttu-id="60e84-282">Samozřejmě v praxi jsou ve skutečnosti v případě potřeby znovu vytvořeny pouze relevantní součásti.</span><span class="sxs-lookup"><span data-stu-id="60e84-282">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

<span data-ttu-id="60e84-283">Konkrétně to zahrnuje také pole.</span><span class="sxs-lookup"><span data-stu-id="60e84-283">This in particular also includes arrays.</span></span>
<span data-ttu-id="60e84-284">Konkrétně není možné aktualizovat položky pole.</span><span class="sxs-lookup"><span data-stu-id="60e84-284">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="60e84-285">Chcete-li upravit existující pole, je nutné využít mechanismus *kopírování a aktualizace* .</span><span class="sxs-lookup"><span data-stu-id="60e84-285">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="60e84-286">Nová pole je možné vytvořit z existujících pomocí výrazů *kopírování a aktualizace* .</span><span class="sxs-lookup"><span data-stu-id="60e84-286">New arrays can be created from existing ones via *copy-and-update* expressions.</span></span>
<span data-ttu-id="60e84-287">Výraz kopírování a aktualizace je výrazem formuláře `expression1 w/ expression2 <- expression3` , kde `expression1` musí být typu `T[]` pro nějaký typ `T` .</span><span class="sxs-lookup"><span data-stu-id="60e84-287">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span>
<span data-ttu-id="60e84-288">Druhý `expression2` definuje indexy prvků, které mají být upraveny v porovnání s polem v `expression1` a musí být buď typu `Int` nebo typu `Range` .</span><span class="sxs-lookup"><span data-stu-id="60e84-288">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span>
<span data-ttu-id="60e84-289">Pokud `expression2` je typ `Int` , `expression3` musí být typu `T` .</span><span class="sxs-lookup"><span data-stu-id="60e84-289">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="60e84-290">Pokud `expression2` je typ `Range` , `expression3` musí být typu `T[]` .</span><span class="sxs-lookup"><span data-stu-id="60e84-290">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="60e84-291">Výraz kopírování a aktualizace `arr w/ idx <- value` vytvoří nové pole se všemi prvky nastavenými na odpovídající element v `arr` , s výjimkou elementů v `idx` , které jsou nastaveny na jeden (y) v `value` .</span><span class="sxs-lookup"><span data-stu-id="60e84-291">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="60e84-292">Například pokud `arr` obsahuje pole `[0,1,2,3]` , pak</span><span class="sxs-lookup"><span data-stu-id="60e84-292">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="60e84-293">`arr w/ 0 <- 10`je pole `[10,1,2,3]` .</span><span class="sxs-lookup"><span data-stu-id="60e84-293">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="60e84-294">`arr w/ 2 <- 10`je pole `[0,1,10,3]` .</span><span class="sxs-lookup"><span data-stu-id="60e84-294">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="60e84-295">`arr w/ 0..2..3 <- [10,12]`je pole `[10,1,12,3]` .</span><span class="sxs-lookup"><span data-stu-id="60e84-295">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="60e84-296">Výrazy kopírování a aktualizace pro pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="60e84-296">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="60e84-297">Podobné výrazy existují pro pojmenované položky v uživatelsky definovaných typech.</span><span class="sxs-lookup"><span data-stu-id="60e84-297">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="60e84-298">Zvažte například typ.</span><span class="sxs-lookup"><span data-stu-id="60e84-298">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="60e84-299">Pokud `c` obsahuje hodnotu typu `Complex(1., -1.)` , pak `c w/ Re <- 0.` je výraz typu `Complex` , který je vyhodnocen jako `Complex(0., -1.)` .</span><span class="sxs-lookup"><span data-stu-id="60e84-299">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="60e84-300">Vícenásobná pole</span><span class="sxs-lookup"><span data-stu-id="60e84-300">Jagged Arrays</span></span>

<span data-ttu-id="60e84-301">Vícenásobné pole, někdy označované jako "pole polí", je pole, jehož prvky jsou pole.</span><span class="sxs-lookup"><span data-stu-id="60e84-301">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="60e84-302">Prvky vícenásobného pole mohou mít různé velikosti.</span><span class="sxs-lookup"><span data-stu-id="60e84-302">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="60e84-303">Následující příklad ukazuje, jak deklarovat a inicializovat vícenásobné pole reprezentující tabulku násobení.</span><span class="sxs-lookup"><span data-stu-id="60e84-303">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="60e84-304">Pole, která se mají volat</span><span class="sxs-lookup"><span data-stu-id="60e84-304">Arrays of callables</span></span> 

<span data-ttu-id="60e84-305">Všimněte si, že další podrobnosti o volat typy lze najít níže a také na další stránce, [operace a funkce v Q #](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="60e84-305">Note that more details on callable types can be found below, as well as on the next page, [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

<span data-ttu-id="60e84-306">Je-li běžný typ prvku typ operace nebo funkce, všechny prvky musí mít stejné vstupní a výstupní typy.</span><span class="sxs-lookup"><span data-stu-id="60e84-306">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="60e84-307">Typ elementu pole bude podporovat všechny funktory, které jsou podporovány všemi prvky.</span><span class="sxs-lookup"><span data-stu-id="60e84-307">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="60e84-308">Například pokud `Op1` , `Op2` a `Op3` jsou všechny `Qubit[] => Unit` , ale `Op1` podporují `Adjoint` , `Op2` podporují `Controlled` a `Op3` podporují obojí:</span><span class="sxs-lookup"><span data-stu-id="60e84-308">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="60e84-309">`[Op1, Op2]`je pole `(Qubit[] => Unit)` operací.</span><span class="sxs-lookup"><span data-stu-id="60e84-309">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="60e84-310">`[Op1, Op3]`je pole `(Qubit[] => Unit is Adj)` operací.</span><span class="sxs-lookup"><span data-stu-id="60e84-310">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="60e84-311">`[Op2, Op3]`je pole `(Qubit[] => Unit is Ctl)` operací.</span><span class="sxs-lookup"><span data-stu-id="60e84-311">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="60e84-312">Nicméně zatímco `(Qubit[] => Unit is Adj)` a `(Qubit[] => Unit is Ctl)` operace mají společný základní typ `(Qubit[] => Unit)` , mějte na paměti, že pole *of* těchto operátorů nesdílejí společný základní typ.</span><span class="sxs-lookup"><span data-stu-id="60e84-312">However, while `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` operations have the common base type of `(Qubit[] => Unit)`, note that arrays *of* these operators do not share a common base type.</span></span> <span data-ttu-id="60e84-313">Například by v `[[Op1], [Op2]]` současné době vyvolala chybu, protože se pokouší vytvořit pole nekompatibilních typů polí `(Qubit[] => Unit is Adj)[]` a `(Qubit[] => Unit is Ctl)[]` .</span><span class="sxs-lookup"><span data-stu-id="60e84-313">For example, `[[Op1], [Op2]]` would currently raise an error because it is attempting to create an array of the incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>


## <a name="conditional-expressions"></a><span data-ttu-id="60e84-314">Podmíněné výrazy</span><span class="sxs-lookup"><span data-stu-id="60e84-314">Conditional Expressions</span></span>

<span data-ttu-id="60e84-315">Vzhledem k dvěma dalším výrazům stejného typu a logickému výrazu může být podmíněný výraz vytvořen pomocí otazníku `?` a svislého panelu `|` .</span><span class="sxs-lookup"><span data-stu-id="60e84-315">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="60e84-316">Například `a==b ? c | d` .</span><span class="sxs-lookup"><span data-stu-id="60e84-316">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="60e84-317">V tomto příkladu bude hodnota podmíněného výrazu v `c` případě hodnoty `a==b` true a v `d` případě false.</span><span class="sxs-lookup"><span data-stu-id="60e84-317">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="60e84-318">Podmíněné výrazy s volat</span><span class="sxs-lookup"><span data-stu-id="60e84-318">Conditional expressions with callables</span></span>

<span data-ttu-id="60e84-319">Tyto dva výrazy mohou být vyhodnoceny na operace, které mají stejné vstupy a výstupy, ale podporují různé funktory.</span><span class="sxs-lookup"><span data-stu-id="60e84-319">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="60e84-320">V tomto případě typ podmíněného výrazu je operace s těmito vstupy a výstupy, které podporují všechny funktory Podporované oběma výrazy.</span><span class="sxs-lookup"><span data-stu-id="60e84-320">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="60e84-321">Například pokud `Op1` , `Op2` a `Op3` jsou všechny `Qubit[]=>Unit` , ale `Op1` podporují `Adjoint` , `Op2` podporují `Controlled` a `Op3` podporují obojí:</span><span class="sxs-lookup"><span data-stu-id="60e84-321">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="60e84-322">`flag ? Op1 | Op2`je `(Qubit[] => Unit)` operace.</span><span class="sxs-lookup"><span data-stu-id="60e84-322">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="60e84-323">`flag ? Op1 | Op3`je `(Qubit[] => Unit is Adj)` operace.</span><span class="sxs-lookup"><span data-stu-id="60e84-323">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="60e84-324">`flag ? Op2 | Op3`je `(Qubit[] => Unit is Ctl)` operace.</span><span class="sxs-lookup"><span data-stu-id="60e84-324">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="60e84-325">Pokud jeden ze dvou možných výsledných výrazů zahrnuje volání funkce nebo operace, bude toto volání provedeno pouze v případě, že je výsledkem ta, která bude hodnotou volání.</span><span class="sxs-lookup"><span data-stu-id="60e84-325">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="60e84-326">Například v případě `a==b ? C(qs) | D(qs)` , pokud `a==b` je hodnota true, bude `C` vyvolána operace, a pokud je hodnota false, `D` bude vyvolána pouze.</span><span class="sxs-lookup"><span data-stu-id="60e84-326">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="60e84-327">To se podobá krátkodobému okruhu v jiných jazycích.</span><span class="sxs-lookup"><span data-stu-id="60e84-327">This is similar to short-circuiting in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="60e84-328">Výrazy, které se mají volat</span><span class="sxs-lookup"><span data-stu-id="60e84-328">Callable Expressions</span></span>

<span data-ttu-id="60e84-329">Volatelné literály je název operace nebo funkce definované v oboru kompilace.</span><span class="sxs-lookup"><span data-stu-id="60e84-329">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="60e84-330">Například `X` je literál operace, který odkazuje na standardní `X` operace knihovny a `Message` je literál funkce, který odkazuje na standardní `Message` funkci knihovny.</span><span class="sxs-lookup"><span data-stu-id="60e84-330">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="60e84-331">Pokud operace podporuje `Adjoint` funktor, pak `Adjoint op` je výraz operace.</span><span class="sxs-lookup"><span data-stu-id="60e84-331">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="60e84-332">Podobně platí, že pokud operace podporuje `Controlled` funktor, pak `Controlled op` je výraz operace.</span><span class="sxs-lookup"><span data-stu-id="60e84-332">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="60e84-333">Typy těchto výrazů jsou určeny při [volání specializace operace](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span><span class="sxs-lookup"><span data-stu-id="60e84-333">The types of these expressions are specified at [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="60e84-334">Funktory ( `Adjoint` a `Controlled` ) sváže více než všechny ostatní operátory s výjimkou operátoru Unwrap `!` a pole s indexem [].</span><span class="sxs-lookup"><span data-stu-id="60e84-334">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with []\`.</span></span>
<span data-ttu-id="60e84-335">Níže jsou uvedené všechny právní a za předpokladu, že operace podporují funktory, který se používá:</span><span class="sxs-lookup"><span data-stu-id="60e84-335">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="60e84-336">Výrazy s parametry, které je typu volat</span><span class="sxs-lookup"><span data-stu-id="60e84-336">Type-parameterized callable expressions</span></span>

<span data-ttu-id="60e84-337">Dá se použít jako hodnota, která se dá použít jako hodnota, řekněme, že se přiřadí proměnné nebo přejdou na jinou možnou volat.</span><span class="sxs-lookup"><span data-stu-id="60e84-337">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="60e84-338">V tomto případě musí být v případě, že je možné volat [parametry typu](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), zadány jako součást hodnoty, kterou lze volat.</span><span class="sxs-lookup"><span data-stu-id="60e84-338">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), they must be provided as part of the callable value.</span></span>
<span data-ttu-id="60e84-339">Hodnota, která se nedá volat, nemůže mít nespecifikované parametry typu.</span><span class="sxs-lookup"><span data-stu-id="60e84-339">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="60e84-340">Pokud `Fun` je například funkce s signaturou `'T1->Unit` :</span><span class="sxs-lookup"><span data-stu-id="60e84-340">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="60e84-341">Volat výrazy vyvolání</span><span class="sxs-lookup"><span data-stu-id="60e84-341">Callable Invocation Expressions</span></span>

<span data-ttu-id="60e84-342">Vzhledem k volání (operace nebo funkce) a výrazu řazené kolekce členů na vstupním typu signatury, která se dá volat, může být výraz vyvolání vytvořen připojením výrazu řazené kolekce členů k výrazu, který je k volání.</span><span class="sxs-lookup"><span data-stu-id="60e84-342">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="60e84-343">Typ výrazu vyvolání je výstupní typ signatury, kterou chcete volat.</span><span class="sxs-lookup"><span data-stu-id="60e84-343">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="60e84-344">Například pokud `Op` je operace s signaturou `((Int, Qubit) => Double)` , `Op(3, qubit1)` je výraz typu `Double` .</span><span class="sxs-lookup"><span data-stu-id="60e84-344">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="60e84-345">Podobně, pokud `Sin` je funkce s signaturou `(Double -> Double)` , `Sin(0.1)` je výraz typu `Double` .</span><span class="sxs-lookup"><span data-stu-id="60e84-345">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="60e84-346">Nakonec, pokud `Builder` je funkce s signaturou `(Int -> (Int -> Int))` , `Builder(3)` je funkce z do int.</span><span class="sxs-lookup"><span data-stu-id="60e84-346">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="60e84-347">Vyvolání výsledku výrazu s možností volání vyžaduje navíc pár závorek kolem volání.</span><span class="sxs-lookup"><span data-stu-id="60e84-347">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="60e84-348">Proto pokud chcete vyvolat výsledek volání `Builder` z předchozího odstavce, správná syntaxe je:</span><span class="sxs-lookup"><span data-stu-id="60e84-348">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="60e84-349">Při vyvolání [typu](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) , který se dá volat, se skutečné parametry typu můžou zadat v lomených závorkách `<` a `>` po volání výrazu.</span><span class="sxs-lookup"><span data-stu-id="60e84-349">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="60e84-350">To je obvykle zbytečné, protože kompilátor Q # odvodí skutečné typy.</span><span class="sxs-lookup"><span data-stu-id="60e84-350">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="60e84-351">Nicméně *je* vyžadován pro [částečnou aplikaci](xref:microsoft.quantum.guide.operationsfunctions#partial-application) , pokud je argument typu bez parametrů ponechán neurčen.</span><span class="sxs-lookup"><span data-stu-id="60e84-351">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="60e84-352">Někdy je to užitečné i při předávání operací s různými funktory, které jsou schopné volat.</span><span class="sxs-lookup"><span data-stu-id="60e84-352">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="60e84-353">Například pokud `Func` má signatura `('T1, 'T2, 'T1) -> 'T2` a má signaturu `Op1` `Op2` `(Qubit[] => Unit is Adj)` a `Op3` má signaturu, `(Qubit[] => Unit)` pro vyvolání `Func` `Op1` jako první argument jako `Op2` druhý a `Op3` jako třetí:</span><span class="sxs-lookup"><span data-stu-id="60e84-353">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="60e84-354">Specifikace typu je povinná `Op3` , protože a `Op1` má jiné typy, takže kompilátor bude považovat za dvojznačný bez specifikace.</span><span class="sxs-lookup"><span data-stu-id="60e84-354">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="60e84-355">Priorita operátorů</span><span class="sxs-lookup"><span data-stu-id="60e84-355">Operator Precedence</span></span>

<span data-ttu-id="60e84-356">Všechny binární operátory jsou asociativní zprava, s výjimkou `^` .</span><span class="sxs-lookup"><span data-stu-id="60e84-356">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="60e84-357">Hranaté závorky `[` a `]` pro vytváření řezů a indexování polí sváže před libovolným operátorem.</span><span class="sxs-lookup"><span data-stu-id="60e84-357">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="60e84-358">Funktory `Adjoint` a `Controlled` BIND po vyřazení pole, ale před všemi ostatními operátory.</span><span class="sxs-lookup"><span data-stu-id="60e84-358">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="60e84-359">Kulaté závorky pro operace a volání funkce se také vážou před libovolným operátorem, ale po vyřazení a funktory pole.</span><span class="sxs-lookup"><span data-stu-id="60e84-359">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="60e84-360">Operátory v pořadí podle priority, od nejvyšších po nejnižší:</span><span class="sxs-lookup"><span data-stu-id="60e84-360">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="60e84-361">Operátor</span><span class="sxs-lookup"><span data-stu-id="60e84-361">Operator</span></span> | <span data-ttu-id="60e84-362">Aritou</span><span class="sxs-lookup"><span data-stu-id="60e84-362">Arity</span></span> | <span data-ttu-id="60e84-363">Description</span><span class="sxs-lookup"><span data-stu-id="60e84-363">Description</span></span> | <span data-ttu-id="60e84-364">Typy operandů</span><span class="sxs-lookup"><span data-stu-id="60e84-364">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="60e84-365">koncové`!`</span><span class="sxs-lookup"><span data-stu-id="60e84-365">trailing `!`</span></span> | <span data-ttu-id="60e84-366">Unární</span><span class="sxs-lookup"><span data-stu-id="60e84-366">Unary</span></span> | <span data-ttu-id="60e84-367">Rozbalení</span><span class="sxs-lookup"><span data-stu-id="60e84-367">Unwrap</span></span> | <span data-ttu-id="60e84-368">Libovolný uživatelsky definovaný typ</span><span class="sxs-lookup"><span data-stu-id="60e84-368">Any user-defined type</span></span>
 <span data-ttu-id="60e84-369">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="60e84-369">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="60e84-370">Unární</span><span class="sxs-lookup"><span data-stu-id="60e84-370">Unary</span></span> | <span data-ttu-id="60e84-371">Numerický negativní, bitový doplněk, logická negace</span><span class="sxs-lookup"><span data-stu-id="60e84-371">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="60e84-372">`Int`, nebo pro, pro, `BigInt` `Double` `-` `Int` `BigInt` `~~~` `Bool` pro`not`</span><span class="sxs-lookup"><span data-stu-id="60e84-372">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="60e84-373">Binární</span><span class="sxs-lookup"><span data-stu-id="60e84-373">Binary</span></span> | <span data-ttu-id="60e84-374">Celočíselný výkon</span><span class="sxs-lookup"><span data-stu-id="60e84-374">Integer power</span></span> | <span data-ttu-id="60e84-375">`Int`nebo `BigInt` pro základ `Int` pro exponent</span><span class="sxs-lookup"><span data-stu-id="60e84-375">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="60e84-376">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="60e84-376">`/`, `*`, `%`</span></span> | <span data-ttu-id="60e84-377">Binární</span><span class="sxs-lookup"><span data-stu-id="60e84-377">Binary</span></span> | <span data-ttu-id="60e84-378">Dělení, násobení, celočíselné zbytky</span><span class="sxs-lookup"><span data-stu-id="60e84-378">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="60e84-379">`Int`, `BigInt` nebo `Double` pro `/` a `*` , `Int` nebo `BigInt` pro`%`</span><span class="sxs-lookup"><span data-stu-id="60e84-379">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="60e84-380">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="60e84-380">`+`, `-`</span></span> | <span data-ttu-id="60e84-381">Binární</span><span class="sxs-lookup"><span data-stu-id="60e84-381">Binary</span></span> | <span data-ttu-id="60e84-382">Sčítání nebo řetězce a zřetězení polí, odčítání</span><span class="sxs-lookup"><span data-stu-id="60e84-382">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="60e84-383">`Int`, `BigInt` nebo `Double` , navíc `String` nebo libovolný typ pole pro`+`</span><span class="sxs-lookup"><span data-stu-id="60e84-383">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="60e84-384">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="60e84-384">`<<<`, `>>>`</span></span> | <span data-ttu-id="60e84-385">Binární</span><span class="sxs-lookup"><span data-stu-id="60e84-385">Binary</span></span> | <span data-ttu-id="60e84-386">Levý SHIFT, posun doprava</span><span class="sxs-lookup"><span data-stu-id="60e84-386">Left shift, right shift</span></span> | <span data-ttu-id="60e84-387">`Int` nebo `BigInt`</span><span class="sxs-lookup"><span data-stu-id="60e84-387">`Int` or `BigInt`</span></span>
 <span data-ttu-id="60e84-388">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="60e84-388">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="60e84-389">Binární</span><span class="sxs-lookup"><span data-stu-id="60e84-389">Binary</span></span> | <span data-ttu-id="60e84-390">Méně než, méně než nebo-rovno, větší než, větší než nebo rovno, větší než nebo rovno</span><span class="sxs-lookup"><span data-stu-id="60e84-390">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="60e84-391">`Int`, `BigInt` nebo`Double`</span><span class="sxs-lookup"><span data-stu-id="60e84-391">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="60e84-392">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="60e84-392">`==`, `!=`</span></span> | <span data-ttu-id="60e84-393">Binární</span><span class="sxs-lookup"><span data-stu-id="60e84-393">Binary</span></span> | <span data-ttu-id="60e84-394">rovná se, nerovná se porovnávání</span><span class="sxs-lookup"><span data-stu-id="60e84-394">equal, not-equal comparisons</span></span> | <span data-ttu-id="60e84-395">jakýkoli primitivní typ</span><span class="sxs-lookup"><span data-stu-id="60e84-395">any primitive type</span></span>
 `&&&` | <span data-ttu-id="60e84-396">Binární</span><span class="sxs-lookup"><span data-stu-id="60e84-396">Binary</span></span> | <span data-ttu-id="60e84-397">Bitový operátor AND</span><span class="sxs-lookup"><span data-stu-id="60e84-397">Bitwise AND</span></span> | <span data-ttu-id="60e84-398">`Int` nebo `BigInt`</span><span class="sxs-lookup"><span data-stu-id="60e84-398">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="60e84-399">Binární</span><span class="sxs-lookup"><span data-stu-id="60e84-399">Binary</span></span> | <span data-ttu-id="60e84-400">Bitový operátor XOR</span><span class="sxs-lookup"><span data-stu-id="60e84-400">Bitwise XOR</span></span> | <span data-ttu-id="60e84-401">`Int` nebo `BigInt`</span><span class="sxs-lookup"><span data-stu-id="60e84-401">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="60e84-402">Binární</span><span class="sxs-lookup"><span data-stu-id="60e84-402">Binary</span></span> | <span data-ttu-id="60e84-403">Bitový operátor OR</span><span class="sxs-lookup"><span data-stu-id="60e84-403">Bitwise OR</span></span> | <span data-ttu-id="60e84-404">`Int` nebo `BigInt`</span><span class="sxs-lookup"><span data-stu-id="60e84-404">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="60e84-405">Binární</span><span class="sxs-lookup"><span data-stu-id="60e84-405">Binary</span></span> | <span data-ttu-id="60e84-406">Logický operátor AND</span><span class="sxs-lookup"><span data-stu-id="60e84-406">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="60e84-407">Binární</span><span class="sxs-lookup"><span data-stu-id="60e84-407">Binary</span></span> | <span data-ttu-id="60e84-408">Logický operátor OR</span><span class="sxs-lookup"><span data-stu-id="60e84-408">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="60e84-409">Binární/Ternární</span><span class="sxs-lookup"><span data-stu-id="60e84-409">Binary/Ternary</span></span> | <span data-ttu-id="60e84-410">Operátor rozsahu</span><span class="sxs-lookup"><span data-stu-id="60e84-410">Range operator</span></span> | `Int`
 <span data-ttu-id="60e84-411">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="60e84-411">`?` `|`</span></span> | <span data-ttu-id="60e84-412">Ternární</span><span class="sxs-lookup"><span data-stu-id="60e84-412">Ternary</span></span> | <span data-ttu-id="60e84-413">Podmíněné</span><span class="sxs-lookup"><span data-stu-id="60e84-413">Conditional</span></span> | <span data-ttu-id="60e84-414">`Bool`na levé straně</span><span class="sxs-lookup"><span data-stu-id="60e84-414">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="60e84-415">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="60e84-415">`w/` `<-`</span></span> | <span data-ttu-id="60e84-416">Ternární</span><span class="sxs-lookup"><span data-stu-id="60e84-416">Ternary</span></span> | <span data-ttu-id="60e84-417">Kopírování a aktualizace</span><span class="sxs-lookup"><span data-stu-id="60e84-417">Copy-and-update</span></span> | <span data-ttu-id="60e84-418">viz [výrazy pro kopírování a aktualizaci](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="60e84-418">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="60e84-419">Další kroky</span><span class="sxs-lookup"><span data-stu-id="60e84-419">Next steps</span></span>

<span data-ttu-id="60e84-420">Teď, když můžete pracovat s výrazy v Q #, můžete přejít na [operace a funkce v q #](xref:microsoft.quantum.guide.operationsfunctions) a zjistit, jak definovat a volat operace a funkce.</span><span class="sxs-lookup"><span data-stu-id="60e84-420">Now that you can work with expressions in Q#, you can head to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
