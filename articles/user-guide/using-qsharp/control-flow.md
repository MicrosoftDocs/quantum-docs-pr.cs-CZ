---
title: 'Tok řízení v Q #'
description: Smyčky, podmíněnéy atd.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: 1f1b641563fe35879abeee32b4f0aeeb7001b1a0
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/03/2020
ms.locfileid: "84326536"
---
# <a name="control-flow-in-q"></a><span data-ttu-id="3dbc7-103">Tok řízení v Q #</span><span class="sxs-lookup"><span data-stu-id="3dbc7-103">Control Flow in Q#</span></span>

<span data-ttu-id="3dbc7-104">V rámci operace nebo funkce se každý příkaz provede v uvedeném pořadí, podobně jako u nejběžnějších imperativních klasických jazyků.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-104">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="3dbc7-105">Tento tok řízení lze změnit, ale třemi různými způsoby:</span><span class="sxs-lookup"><span data-stu-id="3dbc7-105">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="3dbc7-106">`if`učiněn</span><span class="sxs-lookup"><span data-stu-id="3dbc7-106">`if` statements</span></span>
- <span data-ttu-id="3dbc7-107">`for`smyčky</span><span class="sxs-lookup"><span data-stu-id="3dbc7-107">`for` loops</span></span>
- <span data-ttu-id="3dbc7-108">`repeat`-`until`smyčky</span><span class="sxs-lookup"><span data-stu-id="3dbc7-108">`repeat`-`until` loops</span></span>

<span data-ttu-id="3dbc7-109">Další informace o druhém odložení [najdete níže](#repeat-until-success-loop).</span><span class="sxs-lookup"><span data-stu-id="3dbc7-109">We defer discussion of the latter to further [below](#repeat-until-success-loop).</span></span>
<span data-ttu-id="3dbc7-110">`if` `for` Konstrukce toku ovládacích prvků a však budou mít známý smysl pro většinu klasických programovacích jazyků.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-110">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>

<span data-ttu-id="3dbc7-111">Důležité jsou `for` smyčky a `if` příkazy mohou být použity i v operacích, pro které jsou automaticky generovány specializace.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-111">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="3dbc7-112">V takovém případě sousední `for` smyčka smyčky obrátí směr a převezme sousedícího typu každé iterace.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-112">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="3dbc7-113">Tento postup se řídí principem "obuv-a-SOCKS": Pokud chcete vrátit zpět vložení do aplikace SOCKS a pak provést operaci, je nutné vrátit zpět na obuv a pak zrušit uvedení na SOCKS.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-113">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="3dbc7-114">V takovém případě stále ještě méně se nedaří vyzkoušet a pořídit si své služby SOCKS, dokud budete mít pořád na svou obuv.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-114">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="if-else-if-else"></a><span data-ttu-id="3dbc7-115">If, else-if, else</span><span class="sxs-lookup"><span data-stu-id="3dbc7-115">If, Else-if, Else</span></span>

<span data-ttu-id="3dbc7-116">`if`Příkaz podporuje podmíněné spuštění.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-116">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="3dbc7-117">Skládá se z klíčového slova `if` , otevřené závorky `(` , logického výrazu, uzavírací závorky `)` a bloku příkazu (blok _then_ ).</span><span class="sxs-lookup"><span data-stu-id="3dbc7-117">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="3dbc7-118">Za tímto může následovat libovolný počet klauzulí else-if, každý z nich se skládá z klíčového slova `elif` , otevírací závorky `(` , logického výrazu, uzavírací závorky `)` a bloku příkazu (blok _else-if_ ).</span><span class="sxs-lookup"><span data-stu-id="3dbc7-118">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="3dbc7-119">Nakonec může být příkaz volitelně dokončen s klauzulí else, která se skládá z klíčového slova `else` následovaného jiným blokem příkazu (blok _Else_ ).</span><span class="sxs-lookup"><span data-stu-id="3dbc7-119">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="3dbc7-120">`if`Podmínka je vyhodnocena a je-li nastavena na hodnotu true, je spuštěn blok po.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-120">The `if` condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="3dbc7-121">Pokud je podmínka NEPRAVDA, vyhodnotí se první podmínka else if; Pokud má hodnotu true, je spuštěn blok else-if.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-121">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="3dbc7-122">V opačném případě se otestuje druhý blok else-if a třetí a tak dále, dokud není zjištěna buď klauzule s podmínkou true, nebo nejsou k dispozici další klauzule else-if.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-122">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="3dbc7-123">Pokud je původní podmínka IF a všechny klauzule else-if vyhodnoceny jako NEPRAVDA, je spuštěn blok else, pokud byl poskytnut jeden.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-123">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="3dbc7-124">Všimněte si, že libovolný blok je spuštěný ve svém vlastním oboru.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-124">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="3dbc7-125">Vazby provedené v `if` `elif` bloku, nebo nejsou `else` po konci viditelné.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-125">Bindings made inside of an `if`, `elif`, or `else` block are not visible after its end.</span></span>

<span data-ttu-id="3dbc7-126">Třeba</span><span class="sxs-lookup"><span data-stu-id="3dbc7-126">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="3dbc7-127">nebo</span><span class="sxs-lookup"><span data-stu-id="3dbc7-127">or</span></span>
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a><span data-ttu-id="3dbc7-128">Smyčka for</span><span class="sxs-lookup"><span data-stu-id="3dbc7-128">For Loop</span></span>

<span data-ttu-id="3dbc7-129">`for`Příkaz podporuje iteraci v rozsahu celého čísla nebo nad polem.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-129">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="3dbc7-130">Příkaz se skládá z klíčového slova `for` , otevírací závorky `(` následovaný symbolem nebo řazenou kolekcí členů, klíčovým slovem `in` , výrazem typu `Range` nebo polem, uzavírací závorky `)` a bloku příkazu.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-130">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="3dbc7-131">Blok příkazu (tělo smyčky) je proveden opakovaně s definovanými symboly (proměnné smyčky) svázané s každou hodnotou v rozsahu nebo poli.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-131">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="3dbc7-132">Všimněte si, že pokud je výraz Range vyhodnocen jako prázdný rozsah nebo pole, text nebude proveden vůbec.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-132">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="3dbc7-133">Výraz je plně vyhodnocen před vstupem do smyčky a při provádění smyčky se nemění.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-133">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="3dbc7-134">Proměnná smyčky je svázána s každým vchodem do těla smyčky a na konci těla není svázána.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-134">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="3dbc7-135">Konkrétně proměnná smyčky není svázána po dokončení smyčky for.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-135">In particular, the loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="3dbc7-136">Vazba deklarovaného symbolu je neměnná a řídí se stejnými pravidly jako jiné vazby proměnných.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-136">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="3dbc7-137">V některých příkladech `qubits` je Supposing registrem qubits (tj. typu `Qubit[]` ),</span><span class="sxs-lookup"><span data-stu-id="3dbc7-137">For some examples, supposing `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```
<span data-ttu-id="3dbc7-138">Všimněte si, že na konci jsme využili binární operátor aritmetické a posunutí vlevo, `<<<` Podrobnosti o tom, které lze najít v [numerických výrazech](xref:microsoft.quantum.guide.expressions#numeric-expressions) .</span><span class="sxs-lookup"><span data-stu-id="3dbc7-138">Note that at the end we utilized the arithmetic-shift-left binary operator, `<<<`, details of which can be found at [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions)</span></span>


## <a name="repeat-until-success-loop"></a><span data-ttu-id="3dbc7-139">Opakování do smyčky po úspěšném dokončení</span><span class="sxs-lookup"><span data-stu-id="3dbc7-139">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="3dbc7-140">Jazyk Q # umožňuje, aby byl tok klasického řízení závislý na výsledcích měření qubits.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-140">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="3dbc7-141">Tato funkce zase umožňuje implementovat výkonné pravděpodobnostní miniaplikace, které mohou snížit výpočetní náklady na implementaci unitaries.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-141">This capability in turn enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="3dbc7-142">Jako příklad můžete snadno implementovat vzory, které se označují jako *opakované a neúspěšné* (ru) v Q #.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-142">As an example, it is easy to implement so-called *Repeat-Until-Success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="3dbc7-143">Tyto ru vzory jsou pravděpodobnostní programy, které mají *očekávané* nízké náklady v rámci základních bran, ale u kterých se skutečné náklady závisí na skutečném běhu a skutečném proplutí různých možných větví.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-143">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span>

<span data-ttu-id="3dbc7-144">Aby bylo možné zjednodušit vzorce opakování až do úspěchu (ru), Q # podporuje konstrukce.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-144">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="3dbc7-145">kde `expression` je libovolný platný výraz, který je vyhodnocen jako hodnota typu `Bool` .</span><span class="sxs-lookup"><span data-stu-id="3dbc7-145">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="3dbc7-146">Tělo smyčky se provede a podmínka se vyhodnotí.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-146">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="3dbc7-147">Pokud je podmínka pravdivá, je příkaz dokončen; v opačném případě se oprava provede a příkaz se znovu spustí počínaje textem smyčky.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-147">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>

<span data-ttu-id="3dbc7-148">Všechny tři části smyčky Repeat/dokud (tělo, test a oprava) se považují za jeden obor *pro každé opakování*, takže symboly, které jsou v těle textu, jsou k dispozici v testu a v opravě.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-148">All three portions of a repeat/until loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in the test and in the fixup.</span></span>
<span data-ttu-id="3dbc7-149">Provedení opravy ale ukončí rozsah příkazu, takže vazby symbolů provedené během těla nebo opravy nejsou v dalších opakováních k dispozici.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-149">However completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="3dbc7-150">Kromě toho `fixup` je příkaz často užitečný, ale není vždy nezbytný.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-150">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="3dbc7-151">V případě, že není potřeba, konstrukce</span><span class="sxs-lookup"><span data-stu-id="3dbc7-151">In cases that it is not needed, the construct</span></span>
```qsharp
repeat {
    // do stuff
}
until (expression);
```
<span data-ttu-id="3dbc7-152">je také platným vzorem ru.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-152">is also a valid RUS pattern.</span></span>

<span data-ttu-id="3dbc7-153">V dolní části této stránky uvádíme několik [příkladů cyklů ru](#repeat-until-success-examples).</span><span class="sxs-lookup"><span data-stu-id="3dbc7-153">At the bottom of this page we present some [examples of RUS loops](#repeat-until-success-examples).</span></span>

> [!TIP]   
> <span data-ttu-id="3dbc7-154">Nepoužívejte v rámci funkcí smyčky Repeat-do-úspěch.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-154">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="3dbc7-155">Odpovídající funkce jsou k dispozici v průběhu cyklů ve funkcích.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-155">The corresponding functionality is provided by while loops in functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="3dbc7-156">Smyčka while</span><span class="sxs-lookup"><span data-stu-id="3dbc7-156">While Loop</span></span>

<span data-ttu-id="3dbc7-157">Vzory opakování až po úspěchu mají velmi stejný zápis na základě stavu.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-157">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="3dbc7-158">Jsou běžně používány v určitých třídách algoritmů pro stav, a proto je konstrukce vyhrazeného jazyka v Q #.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-158">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="3dbc7-159">Nicméně cykly, které jsou přerušeny na základě podmínky a jejichž délka spuštění je tudíž neznámá v době kompilace, je nutné zpracovat zvláštní péčí v modulu runtime.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-159">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="3dbc7-160">Jejich použití v rámci funkcí na druhé straně je neproblematické, protože obsahují pouze kód, který bude spuštěn na konvenčním (nestránkovaném) hardwaru.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-160">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="3dbc7-161">Q # proto podporuje použití smyčky while pouze v rámci funkcí.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-161">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="3dbc7-162">`while`Příkaz se skládá z klíčového slova `while` , otevřené závorky `(` , podmínky (tj. logický výraz), uzavírací závorky `)` a bloku příkazu.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-162">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="3dbc7-163">Blok příkazu (tělo smyčky) je proveden, pokud je podmínka vyhodnocena jako `true` .</span><span class="sxs-lookup"><span data-stu-id="3dbc7-163">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a><span data-ttu-id="3dbc7-164">Return – příkaz</span><span class="sxs-lookup"><span data-stu-id="3dbc7-164">Return Statement</span></span>

<span data-ttu-id="3dbc7-165">Příkaz return ukončí provádění operace nebo funkce a vrátí hodnotu volajícímu.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-165">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="3dbc7-166">Skládá se z klíčového slova `return` , následovaný výrazem příslušného typu a ukončující středník.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-166">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="3dbc7-167">Navrácená instance, která vrací prázdnou řazenou kolekci členů, nevyžaduje `()` příkaz return.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-167">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="3dbc7-168">Pokud se požaduje předčasné ukončení, `return ()` může se v tomto případě použít.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-168">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="3dbc7-169">Volat, které vracejí jiný typ, vyžadují konečný návratový příkaz.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-169">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="3dbc7-170">V rámci operace není maximální počet návratových příkazů.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-170">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="3dbc7-171">Kompilátor může vygenerovat upozornění, pokud příkazy následují příkaz return v rámci bloku.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-171">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="3dbc7-172">Třeba</span><span class="sxs-lookup"><span data-stu-id="3dbc7-172">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="3dbc7-173">nebo</span><span class="sxs-lookup"><span data-stu-id="3dbc7-173">or</span></span>
```qsharp
return ();
```
<span data-ttu-id="3dbc7-174">nebo</span><span class="sxs-lookup"><span data-stu-id="3dbc7-174">or</span></span>
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a><span data-ttu-id="3dbc7-175">Příkaz selhání</span><span class="sxs-lookup"><span data-stu-id="3dbc7-175">Fail Statement</span></span>

<span data-ttu-id="3dbc7-176">Příkaz selhání ukončí provádění operace a vrátí volajícímu hodnotu chyby.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-176">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="3dbc7-177">Skládá se z klíčového slova `fail` následovaných řetězcem a zakončeným středníkem.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-177">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="3dbc7-178">Řetězec se vrátí do ovladače klasického rozhraní jako chybová zpráva.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-178">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="3dbc7-179">Počet příkazů selhání v rámci operace není nijak omezen.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-179">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="3dbc7-180">Kompilátor může vygenerovat upozornění, pokud příkazy následují po příkazu neúspěchu v rámci bloku.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-180">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="3dbc7-181">Třeba</span><span class="sxs-lookup"><span data-stu-id="3dbc7-181">For example,</span></span>
```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="3dbc7-182">nebo použití [interpolované řetězce](xref:microsoft.quantum.guide.expressions#interpolated-strings)</span><span class="sxs-lookup"><span data-stu-id="3dbc7-182">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="3dbc7-183">Příklady opakování do až po úspěch</span><span class="sxs-lookup"><span data-stu-id="3dbc7-183">Repeat-Until-Success Examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="3dbc7-184">RU vzor pro jednoduché qubit otočení o ose Irrational</span><span class="sxs-lookup"><span data-stu-id="3dbc7-184">RUS pattern for single qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="3dbc7-185">V typickém případu použití následující operace Q # implementuje otočení kolem osy Irrational $ (I + 2i Z)/\sqrt {5} $ v koule Bloch.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-185">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="3dbc7-186">Toho je možné dosáhnout pomocí známého vzoru ru:</span><span class="sxs-lookup"><span data-stu-id="3dbc7-186">This is accomplished by using a known RUS pattern:</span></span>

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

### <a name="rus-loop-with-mutable-variable-in-scope"></a><span data-ttu-id="3dbc7-187">Smyčka ru se proměnlivou proměnnou v oboru</span><span class="sxs-lookup"><span data-stu-id="3dbc7-187">RUS loop with mutable variable in scope</span></span>

<span data-ttu-id="3dbc7-188">Tento příklad ukazuje použití proměnlivé proměnné, `finished` která je v rozsahu celého cyklu opakování až do opravy a která je inicializována před smyčkou a aktualizována v kroku opravy.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-188">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a><span data-ttu-id="3dbc7-189">RU bez`fixup`</span><span class="sxs-lookup"><span data-stu-id="3dbc7-189">RUS without `fixup`</span></span>

<span data-ttu-id="3dbc7-190">Například následující kód je okruh pravděpodobnostní, který implementuje důležitou rotující bránu $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ pomocí `H` `T` bran a.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-190">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="3dbc7-191">Smyčka končí v průměru v $ \frac {8} {5} $ opakování.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-191">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="3dbc7-192">Další podrobnosti najdete v tématu [*opakování až po úspěch: nedeterministické rozklady qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick a Svore, 2014).</span><span class="sxs-lookup"><span data-stu-id="3dbc7-192">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="3dbc7-193">RU pro přípravu stavu pro stav</span><span class="sxs-lookup"><span data-stu-id="3dbc7-193">RUS to prepare a quantum state</span></span>

<span data-ttu-id="3dbc7-194">Nakonec ukážeme příklad ru vzoru pro přípravu stavu s hodnotou # \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, počínaje ze stavu $ \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-194">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>
<span data-ttu-id="3dbc7-195">Viz také [ukázkový test jednotek, který je součástí standardní knihovny](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="3dbc7-195">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

<span data-ttu-id="3dbc7-196">Významné programové funkce zobrazené v této operaci jsou složitější `fixup` součástí smyčky, která zahrnuje operace s jednou částí, a použití `AssertProb` příkazů k zjištění pravděpodobnosti měření stavu u určitých bodů v programu.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-196">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop, which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>
<span data-ttu-id="3dbc7-197">Viz také [testování a ladění](xref:microsoft.quantum.guide.testingdebugging) pro další informace o [`Assert`](xref:microsoft.quantum.intrinsic.assert) [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operacích a.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-197">See also [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging) for more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations.</span></span>


## <a name="next-steps"></a><span data-ttu-id="3dbc7-198">Další kroky</span><span class="sxs-lookup"><span data-stu-id="3dbc7-198">Next steps</span></span>

<span data-ttu-id="3dbc7-199">Přečtěte si o [testování a ladění](xref:microsoft.quantum.guide.testingdebugging) v Q #.</span><span class="sxs-lookup"><span data-stu-id="3dbc7-199">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>