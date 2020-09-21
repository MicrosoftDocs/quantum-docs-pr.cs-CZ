---
title: Tok řízení v Q#
description: Smyčky, podmíněnéy atd.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- Q#
- $$v
ms.openlocfilehash: 547c57cab67443e8b487bf817eb79fc922b43cdc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833517"
---
# <a name="control-flow-in-no-locq"></a><span data-ttu-id="91d02-103">Tok řízení v Q#</span><span class="sxs-lookup"><span data-stu-id="91d02-103">Control flow in Q#</span></span>

<span data-ttu-id="91d02-104">V rámci operace nebo funkce každý příkaz běží v uvedeném pořadí, podobně jako ostatní běžně imperativní klasické jazyky.</span><span class="sxs-lookup"><span data-stu-id="91d02-104">Within an operation or function, each statement runs in order, similar to other common imperative classical languages.</span></span>
<span data-ttu-id="91d02-105">Tok řízení lze však upravit třemi různými způsoby:</span><span class="sxs-lookup"><span data-stu-id="91d02-105">However, you can modify the flow of control in three distinct ways:</span></span>

* <span data-ttu-id="91d02-106">`if` učiněn</span><span class="sxs-lookup"><span data-stu-id="91d02-106">`if` statements</span></span>
* <span data-ttu-id="91d02-107">`for` smyčky</span><span class="sxs-lookup"><span data-stu-id="91d02-107">`for` loops</span></span>
* <span data-ttu-id="91d02-108">`repeat-until-success` smyčky</span><span class="sxs-lookup"><span data-stu-id="91d02-108">`repeat-until-success` loops</span></span>
* <span data-ttu-id="91d02-109">conjugations ( `apply-within` příkazy)</span><span class="sxs-lookup"><span data-stu-id="91d02-109">conjugations (`apply-within` statements)</span></span>

<span data-ttu-id="91d02-110">`if` `for` Konstrukce toku ovládacích prvků a postupují ve známém smyslu pro většinu klasických programovacích jazyků.</span><span class="sxs-lookup"><span data-stu-id="91d02-110">The `if` and `for` control flow constructs proceed in a familiar sense to most classical programming languages.</span></span> <span data-ttu-id="91d02-111">[`Repeat-until-success`](#repeat-until-success-loop) smyčky a [conjugations](#conjugations) jsou popsány dále v tomto článku.</span><span class="sxs-lookup"><span data-stu-id="91d02-111">[`Repeat-until-success`](#repeat-until-success-loop) loops and [conjugations](#conjugations) are discussed later in this article.</span></span>

<span data-ttu-id="91d02-112">Důležité je, `for` smyčky a `if` příkazy lze použít v operacích, pro které jsou automaticky generovány [specializace](xref:microsoft.quantum.guide.operationsfunctions) .</span><span class="sxs-lookup"><span data-stu-id="91d02-112">Importantly, `for` loops and `if` statements can be used in operations for which [specializations](xref:microsoft.quantum.guide.operationsfunctions) are auto-generated.</span></span> <span data-ttu-id="91d02-113">V tomto scénáři sousední `for` smyčka smyčky obrátí směr a převezme souseda pro každou iteraci.</span><span class="sxs-lookup"><span data-stu-id="91d02-113">In that scenario, the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="91d02-114">Tato akce následuje po principu "obuv-a-SOCKS": Pokud chcete vrátit zpět do aplikace SOCKS a potom provést operaci, musíte zrušit uvedení na obuv a pak zrušit vložení na SOCKS.</span><span class="sxs-lookup"><span data-stu-id="91d02-114">This action follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span> 

## <a name="if-else-if-else"></a><span data-ttu-id="91d02-115">If, else-if, else</span><span class="sxs-lookup"><span data-stu-id="91d02-115">If, Else-if, Else</span></span>

<span data-ttu-id="91d02-116">`if`Příkaz podporuje podmíněné zpracování.</span><span class="sxs-lookup"><span data-stu-id="91d02-116">The `if` statement supports conditional processing.</span></span>
<span data-ttu-id="91d02-117">Skládá se z klíčového slova `if` , logického výrazu v závorkách a bloku příkazu (blok _then_ ).</span><span class="sxs-lookup"><span data-stu-id="91d02-117">It consists of the keyword `if`, a Boolean expression in parentheses, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="91d02-118">Volitelně může následovat libovolný počet klauzulí else-if, z nichž každá se skládá z klíčového slova `elif` , logického výrazu v závorkách a bloku příkazu (blok _else-if_ ).</span><span class="sxs-lookup"><span data-stu-id="91d02-118">Optionally, any number of else-if clauses can follow, each of which consists of the keyword `elif`, a Boolean expression in parentheses, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="91d02-119">Nakonec příkaz může volitelně končit klauzulí else, která se skládá z klíčového slova `else` následovaného jiným blokem příkazu (blok _Else_ ).</span><span class="sxs-lookup"><span data-stu-id="91d02-119">Finally, the statement can optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="91d02-120">`if`Podmínka je vyhodnocena a je-li nastavena na *hodnotu true*, je spuštěn blok *a* .</span><span class="sxs-lookup"><span data-stu-id="91d02-120">The `if` condition is evaluated, and if it is *true*, the *then* block is run.</span></span>
<span data-ttu-id="91d02-121">Pokud je podmínka *NEPRAVDA*, vyhodnotí se první podmínka else if; Pokud je to pravda, pak je spuštěn blok *else-if* .</span><span class="sxs-lookup"><span data-stu-id="91d02-121">If the condition is *false*, then the first else-if condition is evaluated; if that is true, then the *else-if* block is run.</span></span>
<span data-ttu-id="91d02-122">V opačném případě se druhý blok else-if vyhodnocuje a pak třetí a tak dále, dokud není nalezena klauzule s podmínkou true nebo pokud nejsou k dispozici další klauzule else-if.</span><span class="sxs-lookup"><span data-stu-id="91d02-122">Otherwise, the second else-if block evaluates, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="91d02-123">Pokud je původní podmínka *if* a všechny klauzule else-if vyhodnoceny jako *false*, je spuštěn blok *Else* , pokud je k dispozici.</span><span class="sxs-lookup"><span data-stu-id="91d02-123">If the original *if* condition and all the else-if clauses evaluate to *false*, the *else* block is run, if provided.</span></span>

<span data-ttu-id="91d02-124">Všimněte si, že všechny spuštěné bloky se spustí v rámci svého vlastního oboru.</span><span class="sxs-lookup"><span data-stu-id="91d02-124">Note that whichever block runs, it runs within its own scope.</span></span>
<span data-ttu-id="91d02-125">Vazby provedené v `if` `elif` bloku, nebo nejsou `else` po ukončení bloku viditelné.</span><span class="sxs-lookup"><span data-stu-id="91d02-125">Bindings made inside of an `if`, `elif`, or `else` block are not visible after the block ends.</span></span>

<span data-ttu-id="91d02-126">Příklad:</span><span class="sxs-lookup"><span data-stu-id="91d02-126">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="91d02-127">nebo</span><span class="sxs-lookup"><span data-stu-id="91d02-127">or</span></span>
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

## <a name="for-loop"></a><span data-ttu-id="91d02-128">Smyčka for</span><span class="sxs-lookup"><span data-stu-id="91d02-128">For loop</span></span>

<span data-ttu-id="91d02-129">`for`Příkaz podporuje iteraci v celé celočíselné oblasti nebo poli.</span><span class="sxs-lookup"><span data-stu-id="91d02-129">The `for` statement supports iteration over an integer range or an array.</span></span>
<span data-ttu-id="91d02-130">Příkaz se skládá z klíčového slova `for` následovaných řazenou kolekcí členů symbolu nebo symbolu, klíčového slova `in` a výrazu typu `Range` nebo pole, vše v závorkách a bloku příkazu.</span><span class="sxs-lookup"><span data-stu-id="91d02-130">The statement consists of the keyword `for`, followed by a symbol or symbol tuple, the keyword `in`, and an expression of type `Range` or array, all in parentheses, and a statement block.</span></span>

<span data-ttu-id="91d02-131">Blok příkazu (tělo smyčky) se opakovaně spouští s definovaným symbolem (proměnná smyčky) svázaná s každou hodnotou v rozsahu nebo poli.</span><span class="sxs-lookup"><span data-stu-id="91d02-131">The statement block (the body of the loop) runs repeatedly, with the defined symbol (the loop variable) bound to each value in the range or array.</span></span>
<span data-ttu-id="91d02-132">Všimněte si, že pokud je výraz Range vyhodnocen jako prázdný rozsah nebo pole, tělo se nespustí vůbec.</span><span class="sxs-lookup"><span data-stu-id="91d02-132">Note that if the range expression evaluates to an empty range or array, the body does not run at all.</span></span>
<span data-ttu-id="91d02-133">Výraz je plně vyhodnocen před vstupem do smyčky a při spuštění smyčky se nemění.</span><span class="sxs-lookup"><span data-stu-id="91d02-133">The expression is fully evaluated before entering the loop, and does not change while the loop is running.</span></span>

<span data-ttu-id="91d02-134">Proměnná smyčky je svázána s každým vchodem do těla smyčky a není vázána na konci těla.</span><span class="sxs-lookup"><span data-stu-id="91d02-134">The loop variable is bound at each entrance to the loop body, and is unbound at the end of the body.</span></span>
<span data-ttu-id="91d02-135">Proměnná smyčky není svázána po dokončení smyčky for.</span><span class="sxs-lookup"><span data-stu-id="91d02-135">The loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="91d02-136">Vazba proměnné smyčky je neměnná a řídí se stejnými pravidly jako jiné vazby proměnných.</span><span class="sxs-lookup"><span data-stu-id="91d02-136">The binding of the loop variable is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="91d02-137">V těchto příkladech `qubits` je registr qubits (tj. typu `Qubit[]` ),</span><span class="sxs-lookup"><span data-stu-id="91d02-137">In these examples, `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

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

<span data-ttu-id="91d02-138">Všimněte si, že na konci jsme využili binární operátor aritmetické a posunutí vlevo, `<<<` .</span><span class="sxs-lookup"><span data-stu-id="91d02-138">Note that at the end, we utilized the arithmetic-shift-left binary operator, `<<<`.</span></span> <span data-ttu-id="91d02-139">Další informace najdete v tématu [číselné výrazy](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span><span class="sxs-lookup"><span data-stu-id="91d02-139">For more information, see [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span></span>

## <a name="repeat-until-success-loop"></a><span data-ttu-id="91d02-140">Opakování do smyčky po úspěšném dokončení</span><span class="sxs-lookup"><span data-stu-id="91d02-140">Repeat-until-success loop</span></span>

<span data-ttu-id="91d02-141">Q#Jazyk umožňuje, aby tok klasického řízení byl závislý na výsledcích měření qubits.</span><span class="sxs-lookup"><span data-stu-id="91d02-141">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="91d02-142">Tato funkce zase umožňuje implementovat výkonné pravděpodobnostní miniaplikace, které mohou snížit výpočetní náklady na implementaci unitaries.</span><span class="sxs-lookup"><span data-stu-id="91d02-142">This capability, in turn, enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="91d02-143">Příklady tohoto příkladu jsou vzory *opakování až po úspěch* (ru) v Q# .</span><span class="sxs-lookup"><span data-stu-id="91d02-143">Examples of this are the *repeat-until-success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="91d02-144">Tyto ru vzory jsou pravděpodobnostní programy, které mají *očekávané* nízké náklady v souvislosti s základními branami; vzniklé náklady závisí na skutečném běhu a prokládání několika možných větví.</span><span class="sxs-lookup"><span data-stu-id="91d02-144">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates; the incurred cost depends on the actual run and the interleaving of the multiple possible branchings.</span></span>

<span data-ttu-id="91d02-145">Chcete-li zjednodušit vzory opakování až po úspěch (ru), Q# podporují konstrukce</span><span class="sxs-lookup"><span data-stu-id="91d02-145">To facilitate repeat-until-success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="91d02-146">kde `expression` je libovolný platný výraz, který je vyhodnocen jako hodnota typu `Bool` .</span><span class="sxs-lookup"><span data-stu-id="91d02-146">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="91d02-147">Tělo smyčky se spustí a podmínka se vyhodnotí.</span><span class="sxs-lookup"><span data-stu-id="91d02-147">The loop body runs, and then the condition is evaluated.</span></span>
<span data-ttu-id="91d02-148">Pokud je podmínka pravdivá, je příkaz dokončen; v opačném případě se oprava spustí a příkaz se spustí znovu, počínaje textem smyčky.</span><span class="sxs-lookup"><span data-stu-id="91d02-148">If the condition is true, then the statement is completed; otherwise, the fixup runs, and the statement runs again, starting with the loop body.</span></span>

<span data-ttu-id="91d02-149">Všechny tři části smyčky ru (tělo, test a oprava) se považují za jeden obor *pro každé opakování*, takže symboly, které jsou svázané s textem, jsou k dispozici v testu i v opravě.</span><span class="sxs-lookup"><span data-stu-id="91d02-149">All three portions of an RUS loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in both the test and the fixup.</span></span>
<span data-ttu-id="91d02-150">Nicméně dokončení spuštění opravy ukončí rozsah příkazu, takže vazby symbolů provedené během těla nebo opravy nejsou k dispozici v následných opakováních.</span><span class="sxs-lookup"><span data-stu-id="91d02-150">However, completing the run of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="91d02-151">Kromě toho `fixup` je příkaz často užitečný, ale není vždy nezbytný.</span><span class="sxs-lookup"><span data-stu-id="91d02-151">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="91d02-152">V případě, že není potřeba, konstrukce</span><span class="sxs-lookup"><span data-stu-id="91d02-152">In cases that it is not needed, the construct</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression);
```

<span data-ttu-id="91d02-153">je také platným vzorem ru.</span><span class="sxs-lookup"><span data-stu-id="91d02-153">is also a valid RUS pattern.</span></span>

<span data-ttu-id="91d02-154">Další příklady a podrobnosti najdete v [příkladech Zopakování kroků](#repeat-until-success-examples) v tomto článku.</span><span class="sxs-lookup"><span data-stu-id="91d02-154">For more examples and details, see [Repeat-until-success examples](#repeat-until-success-examples) in this article.</span></span>

> [!TIP]   
> <span data-ttu-id="91d02-155">Nepoužívejte v rámci funkcí smyčky Repeat-do-úspěch.</span><span class="sxs-lookup"><span data-stu-id="91d02-155">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="91d02-156">Použijte *while* k zajištění odpovídajících funkcí v rámci funkcí.</span><span class="sxs-lookup"><span data-stu-id="91d02-156">Use *while* loops to provide the corresponding functionality inside functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="91d02-157">Smyčka while</span><span class="sxs-lookup"><span data-stu-id="91d02-157">While loop</span></span>

<span data-ttu-id="91d02-158">Vzory opakování až po úspěchu mají velmi stejný zápis na základě stavu.</span><span class="sxs-lookup"><span data-stu-id="91d02-158">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="91d02-159">Jsou široce používány v určitých třídách algoritmů pro plnění, což je tedy konstrukce vyhrazeného jazyka Q# .</span><span class="sxs-lookup"><span data-stu-id="91d02-159">They are widely used in particular classes of quantum algorithms - hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="91d02-160">Nicméně cykly, které jsou přerušeny na základě podmínky a jejichž délka běhu je tedy neznámá v době kompilace, jsou zpracovávány zvláštní péčí v modulu runtime.</span><span class="sxs-lookup"><span data-stu-id="91d02-160">However, loops that break based on a condition and whose run length is thus unknown at compile-time, are handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="91d02-161">Jejich použití v rámci funkcí je však neproblematické, protože tyto smyčky obsahují pouze kód, který běží na konvenčním (nestránkovaném) hardwaru.</span><span class="sxs-lookup"><span data-stu-id="91d02-161">However, their use within functions is unproblematic since these loops only contain code that runs on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="91d02-162">Q#Proto podporuje použití smyčky while pouze v rámci funkcí.</span><span class="sxs-lookup"><span data-stu-id="91d02-162">Q#, therefore, supports to use of while loops within functions only.</span></span>
<span data-ttu-id="91d02-163">`while`Příkaz se skládá z klíčového slova `while` , logického výrazu v závorkách a bloku příkazu.</span><span class="sxs-lookup"><span data-stu-id="91d02-163">A `while` statement consists of the keyword `while`, a Boolean expression in parentheses, and a statement block.</span></span>
<span data-ttu-id="91d02-164">Blok příkazu (tělo smyčky) běží, pokud je podmínka vyhodnocena jako `true` .</span><span class="sxs-lookup"><span data-stu-id="91d02-164">The statement block (the body of the loop) runs as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="conjugations"></a><span data-ttu-id="91d02-165">Conjugations</span><span class="sxs-lookup"><span data-stu-id="91d02-165">Conjugations</span></span>

<span data-ttu-id="91d02-166">Na rozdíl od klasických bitů, uvolňování paměti je trochu více zapojeno, protože nevidomé resetující qubits může mít nežádoucí důsledky zbývajícího výpočtu, pokud qubits stále entangled.</span><span class="sxs-lookup"><span data-stu-id="91d02-166">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="91d02-167">Tyto účinky je možné vyhnout tím, že před uvolněním paměti vykonává správné "rušení" prováděných výpočtů.</span><span class="sxs-lookup"><span data-stu-id="91d02-167">These effects can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="91d02-168">Běžným vzorem pro výpočetní výkon je následující:</span><span class="sxs-lookup"><span data-stu-id="91d02-168">A common pattern in quantum computing is hence the following:</span></span> 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

<span data-ttu-id="91d02-169">Q# podporuje příkaz conjugation, který implementuje předchozí transformaci.</span><span class="sxs-lookup"><span data-stu-id="91d02-169">Q# supports a conjugation statement that implements the preceding transformation.</span></span> <span data-ttu-id="91d02-170">Pomocí tohoto příkazu `ApplyWith` může být operace implementována následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="91d02-170">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
<span data-ttu-id="91d02-171">Takový příkaz conjugation se stává užitečnou, pokud vnější a vnitřní transformace nejsou snadno dostupné jako operace, ale místo toho jsou vhodnější pro popis pomocí bloku skládajícího se z několika příkazů.</span><span class="sxs-lookup"><span data-stu-id="91d02-171">Such a conjugation statement becomes useful if the outer and inner transformations are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="91d02-172">Inverzní transformace pro příkazy definované v rámci bloku je automaticky generována kompilátorem a spuštěna po dokončení bloku Apply.</span><span class="sxs-lookup"><span data-stu-id="91d02-172">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and run after the apply-block completes.</span></span>
<span data-ttu-id="91d02-173">Vzhledem k tomu, že jakékoli proměnlivé proměnné použité jako součást bloku nelze znovu svázat v bloku Apply, je vygenerovaná transformace zaručena jako sousední v výpočtu v bloku.</span><span class="sxs-lookup"><span data-stu-id="91d02-173">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 

## <a name="return-statement"></a><span data-ttu-id="91d02-174">Return – příkaz</span><span class="sxs-lookup"><span data-stu-id="91d02-174">Return Statement</span></span>

<span data-ttu-id="91d02-175">Příkaz return ukončí běh operace nebo funkce a vrátí hodnotu volajícímu.</span><span class="sxs-lookup"><span data-stu-id="91d02-175">The return statement ends the run of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="91d02-176">Skládá se z klíčového slova `return` , následovaný výrazem příslušného typu a ukončující středník.</span><span class="sxs-lookup"><span data-stu-id="91d02-176">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="91d02-177">Příklad:</span><span class="sxs-lookup"><span data-stu-id="91d02-177">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="91d02-178">nebo</span><span class="sxs-lookup"><span data-stu-id="91d02-178">or</span></span>
```qsharp
return (results, qubits);
```

* <span data-ttu-id="91d02-179">Navrácená instance, která vrací prázdnou řazenou kolekci členů, nevyžaduje `()` příkaz return.</span><span class="sxs-lookup"><span data-stu-id="91d02-179">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
* <span data-ttu-id="91d02-180">Chcete-li zadat předčasné ukončení operace nebo funkce, použijte `return ();` .</span><span class="sxs-lookup"><span data-stu-id="91d02-180">To specify an early exit from the operation or function, use `return ();`.</span></span>
<span data-ttu-id="91d02-181">Volat, které vracejí jiný typ, vyžadují konečný návratový příkaz.</span><span class="sxs-lookup"><span data-stu-id="91d02-181">Callables that return any other type require a final return statement.</span></span>
* <span data-ttu-id="91d02-182">V rámci operace není maximální počet návratových příkazů.</span><span class="sxs-lookup"><span data-stu-id="91d02-182">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="91d02-183">Kompilátor může vygenerovat upozornění, pokud příkazy následují příkaz return v rámci bloku.</span><span class="sxs-lookup"><span data-stu-id="91d02-183">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

   
## <a name="fail-statement"></a><span data-ttu-id="91d02-184">Příkaz selhání</span><span class="sxs-lookup"><span data-stu-id="91d02-184">Fail statement</span></span>

<span data-ttu-id="91d02-185">Příkaz selhání ukončí běh operace a vrátí volajícímu hodnotu chyby.</span><span class="sxs-lookup"><span data-stu-id="91d02-185">The fail statement ends the run of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="91d02-186">Skládá se z klíčového slova `fail` následovaných řetězcem a zakončeným středníkem.</span><span class="sxs-lookup"><span data-stu-id="91d02-186">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="91d02-187">Příkaz vrátí řetězec klasického ovladače jako chybovou zprávu.</span><span class="sxs-lookup"><span data-stu-id="91d02-187">The statement returns the string to the classical driver as the error message.</span></span>

<span data-ttu-id="91d02-188">Počet příkazů selhání v rámci operace není nijak omezen.</span><span class="sxs-lookup"><span data-stu-id="91d02-188">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="91d02-189">Kompilátor může vygenerovat upozornění, pokud příkazy následují po příkazu neúspěchu v rámci bloku.</span><span class="sxs-lookup"><span data-stu-id="91d02-189">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="91d02-190">Příklad:</span><span class="sxs-lookup"><span data-stu-id="91d02-190">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="91d02-191">nebo použití [interpolované řetězce](xref:microsoft.quantum.guide.expressions#interpolated-strings)</span><span class="sxs-lookup"><span data-stu-id="91d02-191">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="91d02-192">Příklady opakování do až po úspěch</span><span class="sxs-lookup"><span data-stu-id="91d02-192">Repeat-until-success examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="91d02-193">RU vzor pro jednoduché qubit otočení o ose Irrational</span><span class="sxs-lookup"><span data-stu-id="91d02-193">RUS pattern for single-qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="91d02-194">V typickém případu použití následující Q# operace implementuje otočení kolem osy Irrational $ (I + 2i Z)/\sqrt {5} $ v koule Bloch.</span><span class="sxs-lookup"><span data-stu-id="91d02-194">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="91d02-195">Implementace používá známý vzor ru:</span><span class="sxs-lookup"><span data-stu-id="91d02-195">The implementation uses a known RUS pattern:</span></span>

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a><span data-ttu-id="91d02-196">RU smyčka se proměnlivou proměnnou v oboru</span><span class="sxs-lookup"><span data-stu-id="91d02-196">RUS loop with a mutable variable in scope</span></span>

<span data-ttu-id="91d02-197">Tento příklad ukazuje použití proměnlivé proměnné, `finished` , která je v rámci rozsahu celé smyčky Repeat-to-refixup a která je inicializována před smyčkou a aktualizována v kroku opravy.</span><span class="sxs-lookup"><span data-stu-id="91d02-197">This example shows the use of a mutable variable, `finished`, which is within the scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

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

### <a name="rus-without-fixup"></a><span data-ttu-id="91d02-198">RU bez `fixup`</span><span class="sxs-lookup"><span data-stu-id="91d02-198">RUS without `fixup`</span></span>

<span data-ttu-id="91d02-199">Tento příklad ukazuje smyčku ru bez kroku opravy.</span><span class="sxs-lookup"><span data-stu-id="91d02-199">This example shows an RUS loop without the fixup step.</span></span> <span data-ttu-id="91d02-200">Kód je okruh pravděpodobnostní, který implementuje důležitou rotující bránu $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ pomocí `H` bran a `T` .</span><span class="sxs-lookup"><span data-stu-id="91d02-200">The code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="91d02-201">Smyčka končí v průměru v $ \frac {8} {5} $ opakování.</span><span class="sxs-lookup"><span data-stu-id="91d02-201">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="91d02-202">Další podrobnosti najdete v tématu [*opakování až po úspěch: nedeterministické rozklady qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick a Svore, 2014).</span><span class="sxs-lookup"><span data-stu-id="91d02-202">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

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

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="91d02-203">RU pro přípravu stavu pro stav</span><span class="sxs-lookup"><span data-stu-id="91d02-203">RUS to prepare a quantum state</span></span>

<span data-ttu-id="91d02-204">Tady je příklad ru vzoru pro přípravu stavového pole $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, počínaje ze stavu $ \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="91d02-204">Finally, here is an example of an RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>

<span data-ttu-id="91d02-205">Mezi významné programové funkce uvedené v této operaci patří:</span><span class="sxs-lookup"><span data-stu-id="91d02-205">Notable programmatic features shown in this operation are:</span></span>

* <span data-ttu-id="91d02-206">Složitější `fixup` součást smyčky, která zahrnuje operace po částech.</span><span class="sxs-lookup"><span data-stu-id="91d02-206">A more complex `fixup` part of the loop, which involves quantum operations.</span></span> 
* <span data-ttu-id="91d02-207">Použití `AssertMeasurementProbability` příkazů k zjištění pravděpodobnosti měření stavu v určitém počtu bodů v programu.</span><span class="sxs-lookup"><span data-stu-id="91d02-207">The use of `AssertMeasurementProbability` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>

<span data-ttu-id="91d02-208">Další informace o [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) operacích a naleznete v tématu [testování a ladění](xref:microsoft.quantum.guide.testingdebugging).</span><span class="sxs-lookup"><span data-stu-id="91d02-208">For more information about the [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) and [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) operations, see [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging).</span></span>

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

<span data-ttu-id="91d02-209">Další informace najdete v tématu [Ukázka testování částí, která je k dispozici ve standardní knihovně](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="91d02-209">For more information, see [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

## <a name="next-steps"></a><span data-ttu-id="91d02-210">Další kroky</span><span class="sxs-lookup"><span data-stu-id="91d02-210">Next steps</span></span>

<span data-ttu-id="91d02-211">Přečtěte si o [testování a ladění](xref:microsoft.quantum.guide.testingdebugging) v Q# .</span><span class="sxs-lookup"><span data-stu-id="91d02-211">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>
