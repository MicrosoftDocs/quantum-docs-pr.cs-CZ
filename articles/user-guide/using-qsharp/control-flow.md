---
title: Tok řízení v Q#
description: Smyčky, podmíněnéy atd.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- Q#
- $$v
ms.openlocfilehash: e8c873868d6f697fc90b23a38c11f35e46b40c4f
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759658"
---
# <a name="control-flow-in-no-locq"></a><span data-ttu-id="6030c-103">Tok řízení v Q#</span><span class="sxs-lookup"><span data-stu-id="6030c-103">Control flow in Q#</span></span>

<span data-ttu-id="6030c-104">V rámci operace nebo funkce každý příkaz běží v uvedeném pořadí, podobně jako ostatní běžně imperativní klasické jazyky.</span><span class="sxs-lookup"><span data-stu-id="6030c-104">Within an operation or function, each statement runs in order, similar to other common imperative classical languages.</span></span>
<span data-ttu-id="6030c-105">Tok řízení lze však upravit třemi různými způsoby:</span><span class="sxs-lookup"><span data-stu-id="6030c-105">However, you can modify the flow of control in three distinct ways:</span></span>

* <span data-ttu-id="6030c-106">`if` učiněn</span><span class="sxs-lookup"><span data-stu-id="6030c-106">`if` statements</span></span>
* <span data-ttu-id="6030c-107">`for` smyčky</span><span class="sxs-lookup"><span data-stu-id="6030c-107">`for` loops</span></span>
* <span data-ttu-id="6030c-108">`repeat-until-success` smyčky</span><span class="sxs-lookup"><span data-stu-id="6030c-108">`repeat-until-success` loops</span></span>

<span data-ttu-id="6030c-109">`if` `for` Konstrukce toku ovládacích prvků a postupují ve známém smyslu pro většinu klasických programovacích jazyků.</span><span class="sxs-lookup"><span data-stu-id="6030c-109">The `if` and `for` control flow constructs proceed in a familiar sense to most classical programming languages.</span></span> <span data-ttu-id="6030c-110">[`Repeat-until-success`](#repeat-until-success-loop) smyčky jsou popsány dále v tomto článku.</span><span class="sxs-lookup"><span data-stu-id="6030c-110">[`Repeat-until-success`](#repeat-until-success-loop) loops are discussed later in this article.</span></span>

<span data-ttu-id="6030c-111">Důležité je, `for` smyčky a `if` příkazy lze použít v operacích, pro které jsou automaticky generovány [specializace](xref:microsoft.quantum.guide.operationsfunctions) .</span><span class="sxs-lookup"><span data-stu-id="6030c-111">Importantly, `for` loops and `if` statements can be used in operations for which [specializations](xref:microsoft.quantum.guide.operationsfunctions) are auto-generated.</span></span> <span data-ttu-id="6030c-112">V tomto scénáři sousední `for` smyčka smyčky obrátí směr a převezme souseda pro každou iteraci.</span><span class="sxs-lookup"><span data-stu-id="6030c-112">In that scenario, the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="6030c-113">Tato akce následuje po principu "obuv-a-SOCKS": Pokud chcete vrátit zpět do aplikace SOCKS a potom provést operaci, musíte zrušit uvedení na obuv a pak zrušit vložení na SOCKS.</span><span class="sxs-lookup"><span data-stu-id="6030c-113">This action follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span> 

## <a name="if-else-if-else"></a><span data-ttu-id="6030c-114">If, else-if, else</span><span class="sxs-lookup"><span data-stu-id="6030c-114">If, Else-if, Else</span></span>

<span data-ttu-id="6030c-115">`if`Příkaz podporuje podmíněné spuštění.</span><span class="sxs-lookup"><span data-stu-id="6030c-115">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="6030c-116">Skládá se z klíčového slova `if` , logického výrazu v závorkách a bloku příkazu (blok _then_ ).</span><span class="sxs-lookup"><span data-stu-id="6030c-116">It consists of the keyword `if`, a Boolean expression in parentheses, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="6030c-117">Volitelně může následovat libovolný počet klauzulí else-if, z nichž každá se skládá z klíčového slova `elif` , logického výrazu v závorkách a bloku příkazu (blok _else-if_ ).</span><span class="sxs-lookup"><span data-stu-id="6030c-117">Optionally, any number of else-if clauses can follow, each of which consists of the keyword `elif`, a Boolean expression in parentheses, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="6030c-118">Nakonec příkaz může volitelně končit klauzulí else, která se skládá z klíčového slova `else` následovaného jiným blokem příkazu (blok _Else_ ).</span><span class="sxs-lookup"><span data-stu-id="6030c-118">Finally, the statement can optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="6030c-119">`if`Podmínka je vyhodnocena a je-li nastavena na *hodnotu true*, je spuštěn blok *a* .</span><span class="sxs-lookup"><span data-stu-id="6030c-119">The `if` condition is evaluated, and if it is *true*, the *then* block is run.</span></span>
<span data-ttu-id="6030c-120">Pokud je podmínka *NEPRAVDA*, vyhodnotí se první podmínka else if; Pokud je to pravda, pak je spuštěn blok *else-if* .</span><span class="sxs-lookup"><span data-stu-id="6030c-120">If the condition is *false*, then the first else-if condition is evaluated; if that is true, then the *else-if* block is run.</span></span>
<span data-ttu-id="6030c-121">V opačném případě se druhý blok else-if vyhodnocuje a pak třetí a tak dále, dokud není nalezena klauzule s podmínkou true nebo pokud nejsou k dispozici další klauzule else-if.</span><span class="sxs-lookup"><span data-stu-id="6030c-121">Otherwise, the second else-if block evaluates, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="6030c-122">Pokud je původní podmínka *if* a všechny klauzule else-if vyhodnoceny jako *false*, je spuštěn blok *Else* , pokud je k dispozici.</span><span class="sxs-lookup"><span data-stu-id="6030c-122">If the original *if* condition and all the else-if clauses evaluate to *false*, the *else* block is run, if provided.</span></span>

<span data-ttu-id="6030c-123">Všimněte si, že všechny spuštěné bloky se spustí v rámci svého vlastního oboru.</span><span class="sxs-lookup"><span data-stu-id="6030c-123">Note that whichever block runs, it runs within its own scope.</span></span>
<span data-ttu-id="6030c-124">Vazby provedené v `if` `elif` bloku, nebo nejsou `else` po ukončení bloku viditelné.</span><span class="sxs-lookup"><span data-stu-id="6030c-124">Bindings made inside of an `if`, `elif`, or `else` block are not visible after the block ends.</span></span>

<span data-ttu-id="6030c-125">Příklad:</span><span class="sxs-lookup"><span data-stu-id="6030c-125">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="6030c-126">nebo</span><span class="sxs-lookup"><span data-stu-id="6030c-126">or</span></span>
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

## <a name="for-loop"></a><span data-ttu-id="6030c-127">Smyčka for</span><span class="sxs-lookup"><span data-stu-id="6030c-127">For loop</span></span>

<span data-ttu-id="6030c-128">`for`Příkaz podporuje iteraci v celé celočíselné oblasti nebo poli.</span><span class="sxs-lookup"><span data-stu-id="6030c-128">The `for` statement supports iteration over an integer range or an array.</span></span>
<span data-ttu-id="6030c-129">Příkaz se skládá z klíčového slova `for` následovaných řazenou kolekcí členů symbolu nebo symbolu, klíčového slova `in` a výrazu typu `Range` nebo pole, vše v závorkách a bloku příkazu.</span><span class="sxs-lookup"><span data-stu-id="6030c-129">The statement consists of the keyword `for`, followed by a symbol or symbol tuple, the keyword `in`, and an expression of type `Range` or array, all in parentheses, and a statement block.</span></span>

<span data-ttu-id="6030c-130">Blok příkazu (tělo smyčky) se opakovaně spouští s definovaným symbolem (proměnná smyčky) svázaná s každou hodnotou v rozsahu nebo poli.</span><span class="sxs-lookup"><span data-stu-id="6030c-130">The statement block (the body of the loop) runs repeatedly, with the defined symbol (the loop variable) bound to each value in the range or array.</span></span>
<span data-ttu-id="6030c-131">Všimněte si, že pokud je výraz Range vyhodnocen jako prázdný rozsah nebo pole, tělo se nespustí vůbec.</span><span class="sxs-lookup"><span data-stu-id="6030c-131">Note that if the range expression evaluates to an empty range or array, the body does not run at all.</span></span>
<span data-ttu-id="6030c-132">Výraz je plně vyhodnocen před vstupem do smyčky a při provádění smyčky se nemění.</span><span class="sxs-lookup"><span data-stu-id="6030c-132">The expression is fully evaluated before entering the loop, and does not change while the loop is executing.</span></span>

<span data-ttu-id="6030c-133">Proměnná smyčky je svázána s každým vchodem do těla smyčky a není vázána na konci těla.</span><span class="sxs-lookup"><span data-stu-id="6030c-133">The loop variable is bound at each entrance to the loop body, and is unbound at the end of the body.</span></span>
<span data-ttu-id="6030c-134">Proměnná smyčky není svázána po dokončení smyčky for.</span><span class="sxs-lookup"><span data-stu-id="6030c-134">The loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="6030c-135">Vazba proměnné smyčky je neměnná a řídí se stejnými pravidly jako jiné vazby proměnných.</span><span class="sxs-lookup"><span data-stu-id="6030c-135">The binding of the loop variable is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="6030c-136">V těchto příkladech `qubits` je registr qubits (tj. typu `Qubit[]` ),</span><span class="sxs-lookup"><span data-stu-id="6030c-136">In these examples, `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

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

<span data-ttu-id="6030c-137">Všimněte si, že na konci jsme využili binární operátor aritmetické a posunutí vlevo, `<<<` .</span><span class="sxs-lookup"><span data-stu-id="6030c-137">Note that at the end, we utilized the arithmetic-shift-left binary operator, `<<<`.</span></span> <span data-ttu-id="6030c-138">Další informace najdete v tématu [číselné výrazy](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span><span class="sxs-lookup"><span data-stu-id="6030c-138">For more information, see [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span></span>

## <a name="repeat-until-success-loop"></a><span data-ttu-id="6030c-139">Opakování do smyčky po úspěšném dokončení</span><span class="sxs-lookup"><span data-stu-id="6030c-139">Repeat-until-success loop</span></span>

<span data-ttu-id="6030c-140">Q#Jazyk umožňuje, aby tok klasického řízení byl závislý na výsledcích měření qubits.</span><span class="sxs-lookup"><span data-stu-id="6030c-140">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="6030c-141">Tato funkce zase umožňuje implementovat výkonné pravděpodobnostní miniaplikace, které mohou snížit výpočetní náklady na implementaci unitaries.</span><span class="sxs-lookup"><span data-stu-id="6030c-141">This capability, in turn, enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="6030c-142">Příklady tohoto příkladu jsou vzory *opakování až po úspěch* (ru) v Q# .</span><span class="sxs-lookup"><span data-stu-id="6030c-142">Examples of this are the *repeat-until-success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="6030c-143">Tyto ru vzory jsou pravděpodobnostní programy, které mají *očekávané* nízké náklady v souvislosti s základními branami; vzniklé náklady závisí na skutečném běhu a prokládání několika možných větví.</span><span class="sxs-lookup"><span data-stu-id="6030c-143">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates; the incurred cost depends on the actual run and the interleaving of the multiple possible branchings.</span></span>

<span data-ttu-id="6030c-144">Chcete-li zjednodušit vzory opakování až po úspěch (ru), Q# podporují konstrukce</span><span class="sxs-lookup"><span data-stu-id="6030c-144">To facilitate repeat-until-success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="6030c-145">kde `expression` je libovolný platný výraz, který je vyhodnocen jako hodnota typu `Bool` .</span><span class="sxs-lookup"><span data-stu-id="6030c-145">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="6030c-146">Tělo smyčky se spustí a podmínka se vyhodnotí.</span><span class="sxs-lookup"><span data-stu-id="6030c-146">The loop body runs, and then the condition is evaluated.</span></span>
<span data-ttu-id="6030c-147">Pokud je podmínka pravdivá, je příkaz dokončen; v opačném případě se oprava spustí a příkaz se spustí znovu, počínaje textem smyčky.</span><span class="sxs-lookup"><span data-stu-id="6030c-147">If the condition is true, then the statement is completed; otherwise, the fixup runs, and the statement runs again, starting with the loop body.</span></span>

<span data-ttu-id="6030c-148">Všechny tři části smyčky ru (tělo, test a oprava) se považují za jeden obor *pro každé opakování*, takže symboly, které jsou svázané s textem, jsou k dispozici v testu i v opravě.</span><span class="sxs-lookup"><span data-stu-id="6030c-148">All three portions of an RUS loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in both the test and the fixup.</span></span>
<span data-ttu-id="6030c-149">Nicméně dokončení provádění opravy ukončí rozsah příkazu, takže vazby symbolů provedené během těla nebo opravy nejsou k dispozici v následných opakováních.</span><span class="sxs-lookup"><span data-stu-id="6030c-149">However, completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="6030c-150">Kromě toho `fixup` je příkaz často užitečný, ale není vždy nezbytný.</span><span class="sxs-lookup"><span data-stu-id="6030c-150">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="6030c-151">V případě, že není potřeba, konstrukce</span><span class="sxs-lookup"><span data-stu-id="6030c-151">In cases that it is not needed, the construct</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression);
```

<span data-ttu-id="6030c-152">je také platným vzorem ru.</span><span class="sxs-lookup"><span data-stu-id="6030c-152">is also a valid RUS pattern.</span></span>

<span data-ttu-id="6030c-153">Další příklady a podrobnosti najdete v [příkladech Zopakování kroků](#repeat-until-success-examples) v tomto článku.</span><span class="sxs-lookup"><span data-stu-id="6030c-153">For more examples and details, see [Repeat-until-success examples](#repeat-until-success-examples) in this article.</span></span>

> [!TIP]   
> <span data-ttu-id="6030c-154">Nepoužívejte v rámci funkcí smyčky Repeat-do-úspěch.</span><span class="sxs-lookup"><span data-stu-id="6030c-154">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="6030c-155">Použijte *while* k zajištění odpovídajících funkcí v rámci funkcí.</span><span class="sxs-lookup"><span data-stu-id="6030c-155">Use *while* loops to provide the corresponding functionality inside functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="6030c-156">Smyčka while</span><span class="sxs-lookup"><span data-stu-id="6030c-156">While loop</span></span>

<span data-ttu-id="6030c-157">Vzory opakování až po úspěchu mají velmi stejný zápis na základě stavu.</span><span class="sxs-lookup"><span data-stu-id="6030c-157">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="6030c-158">Jsou široce používány v určitých třídách algoritmů pro plnění, což je tedy konstrukce vyhrazeného jazyka Q# .</span><span class="sxs-lookup"><span data-stu-id="6030c-158">They are widely used in particular classes of quantum algorithms - hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="6030c-159">Nicméně cykly, které jsou přerušeny na základě podmínky a jejichž délka spuštění je tedy neznámá v době kompilace, jsou zpracovávány zvláštní péčí v modulu runtime.</span><span class="sxs-lookup"><span data-stu-id="6030c-159">However, loops that break based on a condition and whose execution length is thus unknown at compile-time, are handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="6030c-160">Jejich použití v rámci funkcí je však neproblematické, protože tyto smyčky obsahují pouze kód, který běží na konvenčním (nestránkovaném) hardwaru.</span><span class="sxs-lookup"><span data-stu-id="6030c-160">However, their use within functions is unproblematic since these loops only contain code that runs on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="6030c-161">Q#Proto podporuje použití smyčky while pouze v rámci funkcí.</span><span class="sxs-lookup"><span data-stu-id="6030c-161">Q#, therefore, supports to use of while loops within functions only.</span></span> <span data-ttu-id="6030c-162">`while`Příkaz se skládá z klíčového slova `while` , logického výrazu v závorkách a bloku příkazu.</span><span class="sxs-lookup"><span data-stu-id="6030c-162">A `while` statement consists of the keyword `while`, a Boolean expression in parentheses, and a statement block.</span></span>
<span data-ttu-id="6030c-163">Blok příkazu (tělo smyčky) běží, pokud je podmínka vyhodnocena jako `true` .</span><span class="sxs-lookup"><span data-stu-id="6030c-163">The statement block (the body of the loop) runs as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="return-statement"></a><span data-ttu-id="6030c-164">Return – příkaz</span><span class="sxs-lookup"><span data-stu-id="6030c-164">Return Statement</span></span>

<span data-ttu-id="6030c-165">Příkaz return ukončí běh operace nebo funkce a vrátí hodnotu volajícímu.</span><span class="sxs-lookup"><span data-stu-id="6030c-165">The return statement ends the run of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="6030c-166">Skládá se z klíčového slova `return` , následovaný výrazem příslušného typu a ukončující středník.</span><span class="sxs-lookup"><span data-stu-id="6030c-166">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="6030c-167">Příklad:</span><span class="sxs-lookup"><span data-stu-id="6030c-167">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="6030c-168">nebo</span><span class="sxs-lookup"><span data-stu-id="6030c-168">or</span></span>
```qsharp
return (results, qubits);
```

* <span data-ttu-id="6030c-169">Navrácená instance, která vrací prázdnou řazenou kolekci členů, nevyžaduje `()` příkaz return.</span><span class="sxs-lookup"><span data-stu-id="6030c-169">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
* <span data-ttu-id="6030c-170">Chcete-li zadat předčasné ukončení operace nebo funkce, použijte `return ();` .</span><span class="sxs-lookup"><span data-stu-id="6030c-170">To specify an early exit from the operation or function, use `return ();`.</span></span>
<span data-ttu-id="6030c-171">Volat, které vracejí jiný typ, vyžadují konečný návratový příkaz.</span><span class="sxs-lookup"><span data-stu-id="6030c-171">Callables that return any other type require a final return statement.</span></span>
* <span data-ttu-id="6030c-172">V rámci operace není maximální počet návratových příkazů.</span><span class="sxs-lookup"><span data-stu-id="6030c-172">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="6030c-173">Kompilátor může vygenerovat upozornění, pokud příkazy následují příkaz return v rámci bloku.</span><span class="sxs-lookup"><span data-stu-id="6030c-173">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

   
## <a name="fail-statement"></a><span data-ttu-id="6030c-174">Příkaz selhání</span><span class="sxs-lookup"><span data-stu-id="6030c-174">Fail statement</span></span>

<span data-ttu-id="6030c-175">Příkaz selhání ukončí běh operace a vrátí volajícímu hodnotu chyby.</span><span class="sxs-lookup"><span data-stu-id="6030c-175">The fail statement ends the run of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="6030c-176">Skládá se z klíčového slova `fail` následovaných řetězcem a zakončeným středníkem.</span><span class="sxs-lookup"><span data-stu-id="6030c-176">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="6030c-177">Příkaz vrátí řetězec klasického ovladače jako chybovou zprávu.</span><span class="sxs-lookup"><span data-stu-id="6030c-177">The statement returns the string to the classical driver as the error message.</span></span>

<span data-ttu-id="6030c-178">Počet příkazů selhání v rámci operace není nijak omezen.</span><span class="sxs-lookup"><span data-stu-id="6030c-178">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="6030c-179">Kompilátor může vygenerovat upozornění, pokud příkazy následují po příkazu neúspěchu v rámci bloku.</span><span class="sxs-lookup"><span data-stu-id="6030c-179">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="6030c-180">Příklad:</span><span class="sxs-lookup"><span data-stu-id="6030c-180">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="6030c-181">nebo použití [interpolované řetězce](xref:microsoft.quantum.guide.expressions#interpolated-strings)</span><span class="sxs-lookup"><span data-stu-id="6030c-181">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="6030c-182">Příklady opakování do až po úspěch</span><span class="sxs-lookup"><span data-stu-id="6030c-182">Repeat-until-success examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="6030c-183">RU vzor pro jednoduché qubit otočení o ose Irrational</span><span class="sxs-lookup"><span data-stu-id="6030c-183">RUS pattern for single-qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="6030c-184">V typickém případu použití následující Q# operace implementuje otočení kolem osy Irrational $ (I + 2i Z)/\sqrt {5} $ v koule Bloch.</span><span class="sxs-lookup"><span data-stu-id="6030c-184">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="6030c-185">Implementace používá známý vzor ru:</span><span class="sxs-lookup"><span data-stu-id="6030c-185">The implementation uses a known RUS pattern:</span></span>

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a><span data-ttu-id="6030c-186">RU smyčka se proměnlivou proměnnou v oboru</span><span class="sxs-lookup"><span data-stu-id="6030c-186">RUS loop with a mutable variable in scope</span></span>

<span data-ttu-id="6030c-187">Tento příklad ukazuje použití proměnlivé proměnné, `finished` , která je v rámci rozsahu celé smyčky Repeat-to-refixup a která je inicializována před smyčkou a aktualizována v kroku opravy.</span><span class="sxs-lookup"><span data-stu-id="6030c-187">This example shows the use of a mutable variable, `finished`, which is within the scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

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

### <a name="rus-without-fixup"></a><span data-ttu-id="6030c-188">RU bez `fixup`</span><span class="sxs-lookup"><span data-stu-id="6030c-188">RUS without `fixup`</span></span>

<span data-ttu-id="6030c-189">Tento příklad ukazuje smyčku ru bez kroku opravy.</span><span class="sxs-lookup"><span data-stu-id="6030c-189">This example shows an RUS loop without the fixup step.</span></span> <span data-ttu-id="6030c-190">Kód je okruh pravděpodobnostní, který implementuje důležitou rotující bránu $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ pomocí `H` bran a `T` .</span><span class="sxs-lookup"><span data-stu-id="6030c-190">The code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="6030c-191">Smyčka končí v průměru v $ \frac {8} {5} $ opakování.</span><span class="sxs-lookup"><span data-stu-id="6030c-191">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="6030c-192">Další podrobnosti najdete v tématu [*opakování až po úspěch: nedeterministické rozklady qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick a Svore, 2014).</span><span class="sxs-lookup"><span data-stu-id="6030c-192">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

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

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="6030c-193">RU pro přípravu stavu pro stav</span><span class="sxs-lookup"><span data-stu-id="6030c-193">RUS to prepare a quantum state</span></span>

<span data-ttu-id="6030c-194">Tady je příklad ru vzoru pro přípravu stavového pole $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, počínaje ze stavu $ \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="6030c-194">Finally, here is an example of an RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>

<span data-ttu-id="6030c-195">Mezi významné programové funkce uvedené v této operaci patří:</span><span class="sxs-lookup"><span data-stu-id="6030c-195">Notable programmatic features shown in this operation are:</span></span>

* <span data-ttu-id="6030c-196">Složitější `fixup` součást smyčky, která zahrnuje operace po částech.</span><span class="sxs-lookup"><span data-stu-id="6030c-196">A more complex `fixup` part of the loop, which involves quantum operations.</span></span> 
* <span data-ttu-id="6030c-197">Použití `AssertMeasurementProbability` příkazů k zjištění pravděpodobnosti měření stavu v určitém počtu bodů v programu.</span><span class="sxs-lookup"><span data-stu-id="6030c-197">The use of `AssertMeasurementProbability` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>

<span data-ttu-id="6030c-198">Další informace o [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) operacích a naleznete v tématu [testování a ladění](xref:microsoft.quantum.guide.testingdebugging).</span><span class="sxs-lookup"><span data-stu-id="6030c-198">For more information about the [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) and [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) operations, see [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging).</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
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

<span data-ttu-id="6030c-199">Další informace najdete v tématu [Ukázka testování částí, která je k dispozici ve standardní knihovně](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="6030c-199">For more information, see [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

## <a name="next-steps"></a><span data-ttu-id="6030c-200">Další kroky</span><span class="sxs-lookup"><span data-stu-id="6030c-200">Next steps</span></span>

<span data-ttu-id="6030c-201">Přečtěte si o [testování a ladění](xref:microsoft.quantum.guide.testingdebugging) v Q# .</span><span class="sxs-lookup"><span data-stu-id="6030c-201">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>
