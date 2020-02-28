---
title: 'Operace a funkce Q #'
description: 'Přečtěte si o operacích a funkcích Q # a o tom, jak se používají v programu pro práci za provozu.'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 43f0cf2da192a607e514d0c7de57a9bdd067faf7
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907660"
---
# <a name="q-operations-and-functions"></a><span data-ttu-id="c0b2d-103">Operace a funkce Q #</span><span class="sxs-lookup"><span data-stu-id="c0b2d-103">Q# Operations and Functions</span></span>

<span data-ttu-id="c0b2d-104">Programy Q # se skládají z jednoho nebo více *operací* , které popisují vedlejší účinky. operace mohou mít data za sebou a jednu nebo více *funkcí* , které umožňují úpravy klasických dat.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-104">Q# programs consist of one or more *operations* that describe side effects quantum operations can have on quantum data, and one or more *functions* that allow modifications to classical data.</span></span> <span data-ttu-id="c0b2d-105">Na rozdíl od operací se funkce používají k popisu čistě klasického chování a nemají žádné vlivy na výpočetní výkonové hodnoty v klasickém prostředí.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-105">In contrast to operations, functions are used to describe purely classical behavior and do not have any effects besides computing classical output values.</span></span>

<span data-ttu-id="c0b2d-106">Každá operace definovaná v Q # může potom zavolat libovolný počet dalších operací, včetně integrovaných vnitřních operací definovaných jazykem.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-106">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="c0b2d-107">Konkrétní způsob, jakým jsou tyto vnitřní operace definovány, závisí na cílovém počítači.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-107">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span> <span data-ttu-id="c0b2d-108">Při kompilaci je každá operace reprezentována jako typ třídy .NET, který lze poskytnout cílovým počítačům.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-108">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="c0b2d-109">Definování nových operací</span><span class="sxs-lookup"><span data-stu-id="c0b2d-109">Defining New Operations</span></span>

<span data-ttu-id="c0b2d-110">Jak je popsáno výše, nejzákladnější stavební blok programového prostředí napsaného v Q # je *operace*, kterou je možné volat buď z klasických aplikací .NET, například pomocí simulátoru, nebo jinými operacemi v rámci Q #.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-110">As described above, the most basic building block of a quantum program written in Q# is an *operation*, which can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="c0b2d-111">Každá operace provede vstup, vytvoří výstup a určí implementaci pro jednu nebo více specializací operace.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-111">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="c0b2d-112">Následující operace například definuje pouze výchozí specializaci těla a jako vstup bere jeden qubit a potom na tomto vstupu zavolá integrovanou `X` operaci:</span><span class="sxs-lookup"><span data-stu-id="c0b2d-112">For instance, the following operation defines only a default body specialization and takes a single qubit as its input, then calls the built-in `X` operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="c0b2d-113">Klíčové slovo `operation` zahájí definici operace a následuje název; zde `BitFlip`.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-113">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="c0b2d-114">Dále je typ vstupu definován jako `Qubit`, společně s názvem `target` pro odkazování na vstup v rámci nové operace.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-114">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="c0b2d-115">Podobně `Unit` definuje, že výstup operace je prázdný.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-115">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="c0b2d-116">To se používá podobně jako `void` v C# a dalších imperativních jazycích a je ekvivalentní `unit` v F# a dalších funkčních jazycích.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-116">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

> [!NOTE]
> <span data-ttu-id="c0b2d-117">Podrobněji prozkoumáme níže, ale každá operace v Q # přebírá přesně jeden vstup a vrátí přesně jeden výstup.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-117">We will explore this in more detail below, but each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="c0b2d-118">Několik vstupů a výstupů je pak znázorněno pomocí *řazených kolekcí členů*, které shromažďují více hodnot dohromady do jedné hodnoty.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-118">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="c0b2d-119">Řekněme, že Q # je jazyk řazené kolekce členů (Tuple) v řazené kolekci členů.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-119">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="c0b2d-120">Po tomto konceptu by měl být `()` číst jako "prázdná" řazená kolekce členů, která má typ `Unit`.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-120">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

<span data-ttu-id="c0b2d-121">V rámci nové operace lze implementaci zadat přímo v rámci deklarace, pokud je nutné explicitně zadat pouze implementaci výchozí specializace těla.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-121">Within the new operation, the implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to be specified explicitly.</span></span> <span data-ttu-id="c0b2d-122">Kromě toho je možné definovat implementace, například jednu nebo více `functor` operací, jak je uvedeno níže.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-122">Additionally, it is possible to define the implementations of, for example, one or more `functor` operations, as elaborated below.</span></span> <span data-ttu-id="c0b2d-123">V předchozím příkladu je jediným příkazem volání integrované operace Q # <xref:microsoft.quantum.intrinsic.x>.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-123">In the example above, the only statement is to call the built-in Q# operation <xref:microsoft.quantum.intrinsic.x>.</span></span>

<span data-ttu-id="c0b2d-124">Operace mohou také vracet zajímavější typy než `Unit`.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-124">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="c0b2d-125">Například operace <xref:microsoft.quantum.intrinsic.m> vrátí výstup typu `Result`, který představuje vykonání měření.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-125">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="c0b2d-126">Můžete buď předat výstup z operace do jiné operace, nebo ho můžete použít s klíčovým slovem `let` k definování nové proměnné.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-126">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>
<!-- Link to UID for superdense conceptual and example documentation. -->
<span data-ttu-id="c0b2d-127">To umožňuje, aby představovalo klasický výpočet, který komunikuje s provozními operacemi na nízké úrovni, jako je například v hustém kódování:</span><span class="sxs-lookup"><span data-stu-id="c0b2d-127">This allows for representing classical computation that interacts with quantum operations at a low level, such as in superdense coding:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a><span data-ttu-id="c0b2d-128">Funktory, sousední a řízený</span><span class="sxs-lookup"><span data-stu-id="c0b2d-128">Functors, adjoint and controlled</span></span>
<span data-ttu-id="c0b2d-129">Pokud operace implementuje jednotnou transformaci, je možné definovat způsob, jakým operace funguje při *adjointed* nebo *řízených*.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-129">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="c0b2d-130">Sousedící specializace operace určuje, jak funguje při zpětném spuštění, zatímco řízená specializace určuje, jak operace funguje, když se aplikuje v podmínkách pro stav registru.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-130">An adjoint specialization of an operation specifies how it acts when run in reverse, while a controlled specialization specifies how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="c0b2d-131">Existence těchto specializací se dá deklarovat jako součást signatury operace: `is Adj + Ctl` v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-131">The existence of these specializations can be declared as part of the operation signature: `is Adj + Ctl` in the following example.</span></span> <span data-ttu-id="c0b2d-132">Odpovídající implementace pro každou takovou implicitně deklarovanou specializaci je následně vygenerována kompilátorem.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-132">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> <span data-ttu-id="c0b2d-133">Mnoho operací v Q # představuje jednotnou branu.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-133">Many operations in Q# represent unitary gates.</span></span>
> <span data-ttu-id="c0b2d-134">Pokud $U $ je Jednotná brána reprezentovaná operací `U`, pak `Adjoint U` představuje jednotkovou bránu $U ^ \dagger $.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-134">If $U$ is the unitary gate represented by an operation `U`, then `Adjoint U` represents the unitary gate $U^\dagger$.</span></span>

<span data-ttu-id="c0b2d-135">V případě, že se implementace nemůže generovat kompilátorem, je možné ji explicitně zadat.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-135">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="c0b2d-136">Tyto explicitní deklarace specializace můžou sestávat z vhodné direktivy generace nebo uživatelsky definované implementace.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-136">Such explicit specialization declarations can consist of a suitable generation directive or a user defined implementation.</span></span> <span data-ttu-id="c0b2d-137">Kód v `PrepareEntangledPair` výše je například ekvivalentní následujícímu kódu, který obsahuje explicitní deklarace specializace:</span><span class="sxs-lookup"><span data-stu-id="c0b2d-137">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="c0b2d-138">Klíčové slovo `auto` označuje, že kompilátor by měl určit, jak se má vygenerovat implementace specializace.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-138">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="c0b2d-139">Pokud kompilátor nemůže vygenerovat implementaci pro určitou specializaci automaticky, nebo pokud lze zadat účinnější implementaci, pak může být implementace také ručně definována.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-139">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
<span data-ttu-id="c0b2d-140">Ve výše uvedeném příkladu `adjoint invert;` označuje, že specializace sousedící-by měla být vygenerována vrácením implementace těla a `controlled adjoint invert;` označuje, že řízená specializace, která je řízena, je vygenerována obrácením dané implementace řízené specializace.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-140">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="c0b2d-141">V [toku řízení v horním řádu](xref:microsoft.quantum.concepts.control-flow)se zobrazí další příklady.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-141">We will see more examples of this in [Higher-Order Control Flow](xref:microsoft.quantum.concepts.control-flow).</span></span>

<span data-ttu-id="c0b2d-142">Chcete-li volat specializaci operace, použijte klíčová slova `Adjoint` nebo `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-142">To call a specialization of an operation, use the `Adjoint` or `Controlled` keywords.</span></span>
<span data-ttu-id="c0b2d-143">Například příklad výše uvedeného ukázkového kódu lze zapsat kompaktnější pomocí přiléhajícího prvku `PrepareEntangledPair` k transformaci stavu entangled zpět na pár unentangled qubits:</span><span class="sxs-lookup"><span data-stu-id="c0b2d-143">For example, the superdense coding example above can be written more compactly by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="c0b2d-144">Při navrhování operací pro použití s funktory je potřeba vzít v úvahu několik důležitých omezení.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-144">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="c0b2d-145">Nejdůležitější specializace pro operaci, která používá výstupní hodnotu jakékoli jiné operace, nelze automaticky generovat kompilátorem, protože je nejednoznačná, jak změnit pořadí příkazů v takové operaci pro získání stejného efektu.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-145">Most critically, specializations for an operation that uses the output value of any other operation cannot be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>


## <a name="defining-new-functions"></a><span data-ttu-id="c0b2d-146">Definování nových funkcí</span><span class="sxs-lookup"><span data-stu-id="c0b2d-146">Defining New Functions</span></span>

<span data-ttu-id="c0b2d-147">Q # také umožňuje definovat *funkce*, které se liší od operací v tom, že nesmí mít žádné účinky přesahující výpočet výstupní hodnoty.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-147">Q# also allows for defining *functions*, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="c0b2d-148">Konkrétně funkce nemohou volat operace, pracovat na qubits, vzorkovat náhodná čísla nebo jinak závisí na stavu mimo vstupní hodnotu funkce.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-148">In particular, functions cannot call operations, act on qubits, sample random numbers, or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="c0b2d-149">V důsledku toho jsou funkce Q # *čisté*, v tom, že vždycky mapují stejné vstupní hodnoty na stejné výstupní hodnoty.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-149">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="c0b2d-150">Kompilátor Q # umožňuje bezpečně změnit pořadí, jak a kdy jsou funkce volány při generování specializací operace.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-150">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="c0b2d-151">Definování funkce funguje podobně jako při definování operace s tím rozdílem, že pro funkci nelze definovat žádné sousedící a řízené specializace.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-151">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="c0b2d-152">Příklad:</span><span class="sxs-lookup"><span data-stu-id="c0b2d-152">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
<span data-ttu-id="c0b2d-153">Pokaždé, když je to možné, je vhodné napsat klasický Logic z pojmu Functions namísto operací, aby bylo možné snadněji použít v rámci operací.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-153">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="c0b2d-154">Pokud jsme napsali `Square` jako operaci, například, kompilátor by nedokázal zaručit, že volání stejného vstupu by konzistentně vytvořilo stejné výstupy.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-154">If we had written `Square` as an operation, for example, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="c0b2d-155">Pro podtržení rozdílu mezi funkcemi a operacemi zvažte problém klasického vzorkování náhodného čísla v rámci operace Q #:</span><span class="sxs-lookup"><span data-stu-id="c0b2d-155">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="c0b2d-156">Pokaždé, když se zavolá `U`, bude mít při `target`jinou akci.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-156">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="c0b2d-157">Konkrétně kompilátor nemůže zaručit, že pokud jsme do `U`přidali deklaraci specializace `adjoint auto`, pak `U(target); Adjoint U(target);` fungovat jako identita (to znamená No-OP).</span><span class="sxs-lookup"><span data-stu-id="c0b2d-157">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="c0b2d-158">To je v rozporu s definicí sousedícího, které jsme viděli v [vektorech a maticích](xref:microsoft.quantum.concepts.vectors), což umožňuje automatické generování sousední specializace v rámci operace, kde jsme volali operaci <xref:microsoft.quantum.math.randomreal> by se přerušily záruky poskytované kompilátorem. <xref:microsoft.quantum.math.randomreal> je operace, pro kterou neexistuje žádná sousední nebo řízená verze.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-158">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="c0b2d-159">Na druhé straně, povolení volání funkcí, jako je například `Square`, je bezpečné, v tom, že kompilátor může mít jistotu, že musí zachovávat vstup pouze pro `Square`, aby bylo možné zachovat stabilní výstup.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-159">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="c0b2d-160">Proto izolování co nejvíc klasických logických funkcí do funkcí umožňuje snadno znovu použít tuto logiku v jiných funkcích a operacích.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-160">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>

## <a name="control-flow"></a><span data-ttu-id="c0b2d-161">Tok řízení</span><span class="sxs-lookup"><span data-stu-id="c0b2d-161">Control Flow</span></span>

<span data-ttu-id="c0b2d-162">V rámci operace nebo funkce se každý příkaz provede v uvedeném pořadí, podobně jako u nejběžnějších imperativních klasických jazyků.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-162">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="c0b2d-163">Tento tok řízení lze změnit, ale třemi různými způsoby:</span><span class="sxs-lookup"><span data-stu-id="c0b2d-163">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="c0b2d-164">Příkazy `if`</span><span class="sxs-lookup"><span data-stu-id="c0b2d-164">`if` Statements</span></span>
- <span data-ttu-id="c0b2d-165">`for` smyčky</span><span class="sxs-lookup"><span data-stu-id="c0b2d-165">`for` Loops</span></span>
- <span data-ttu-id="c0b2d-166">`repeat`-`until` smyčky</span><span class="sxs-lookup"><span data-stu-id="c0b2d-166">`repeat`-`until` Loops</span></span>

<span data-ttu-id="c0b2d-167">Podíváme se na to, dokud se nebudeme rozmluvit, [dokud neproběhne úspěšně (ru)](xref:microsoft.quantum.techniques.qubits#measurements) okruhy.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-167">We defer discussion of the latter until we discuss [Repeat Until Success (RUS)](xref:microsoft.quantum.techniques.qubits#measurements) circuits.</span></span>
<span data-ttu-id="c0b2d-168">`if` a `for` konstrukce toku řízení, ale pokračujte známým smyslem většiny klasických programovacích jazyků.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-168">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>
<span data-ttu-id="c0b2d-169">Konkrétně příkaz `if` může podniknout určitou podmínku, za kterou může následovat jeden nebo více příkazů `elif` a může končit `else`:</span><span class="sxs-lookup"><span data-stu-id="c0b2d-169">In particular, an `if` statement can take a condition, may be followed by one or more `elif` statements, and may end with an `else`:</span></span>

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

<span data-ttu-id="c0b2d-170">Podobně `for` smyčky označují iteraci v rozsahu celých čísel nebo nad prvky pole:</span><span class="sxs-lookup"><span data-stu-id="c0b2d-170">Similarly, `for` loops indicate iteration over a range of integers or over the elements of an array:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

<span data-ttu-id="c0b2d-171">Důležité je, `for` smyčky a příkazy `if` mohou být použity i v operacích, pro které jsou automaticky generovány specializace.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-171">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="c0b2d-172">V takovém případě sousedící smyčka smyčky `for` obrátí směr a převezme sousedícího typu každé iterace.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-172">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="c0b2d-173">Tento postup se řídí principem "obuv-a-SOCKS": Pokud chcete vrátit zpět vložení do aplikace SOCKS a pak provést operaci, je nutné vrátit zpět na obuv a pak zrušit uvedení na SOCKS.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-173">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="c0b2d-174">V takovém případě stále ještě méně se nedaří vyzkoušet a pořídit si své služby SOCKS, dokud budete mít pořád na svou obuv.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-174">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="operations-and-functions-as-first-class-values"></a><span data-ttu-id="c0b2d-175">Operace a funkce jako hodnoty první třídy</span><span class="sxs-lookup"><span data-stu-id="c0b2d-175">Operations and Functions as First-Class Values</span></span>

<span data-ttu-id="c0b2d-176">Jednou z kritických postupů pro rozhodnutí o toku řízení a klasické logice pomocí funkcí místo operací je využití těchto operací a funkcí v Q # jsou *prvními třídami*.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-176">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="c0b2d-177">To znamená, že jsou všechny hodnoty v jazyce v pravém.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-177">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="c0b2d-178">Například následující je naprosto platný kód Q #, pokud je trochu nepřímá:</span><span class="sxs-lookup"><span data-stu-id="c0b2d-178">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="c0b2d-179">Hodnota proměnné `ourH` ve výše uvedeném fragmentu kódu je pak <xref:microsoft.quantum.intrinsic.h>operace, například tuto hodnotu můžeme zavolat jako jakoukoli jinou operaci.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-179">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="c0b2d-180">To nám umožňuje psát operace, které jako součást svého vstupu přijímají operace, které vytvářejí koncepty toku řízení vyššího řádu.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-180">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="c0b2d-181">Můžeme si například představit, že se má "čtvercová" operace aplikovat dvakrát na stejný cílový qubit.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-181">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="c0b2d-182">V tomto příkladu se šipka `=>`, která se zobrazí v typu `(Qubit => Unit)`, označuje, že vstupní pole `op` je operace, která přebírá jako svůj vstup typ `Qubit` a vytváří prázdnou řazenou kolekci členů jako svůj výstup.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-182">In this example, the `=>` arrow that appears in the type `(Qubit => Unit)` denotes that the input field `op` is an operation which takes as its input the type `Qubit` and produces an empty tuple as its output.</span></span>
<span data-ttu-id="c0b2d-183">Dále určíme vlastnosti tohoto typu operace, které obsahují informace o tom, které funktory jsou podporovány.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-183">Additionally we specify the characteristics of that operation type, which contain the information about which functors are supported.</span></span>
<span data-ttu-id="c0b2d-184">Operace typu `(Qubit => Unit)` nepodporuje ani `Adjoint` ani `Controlled` funktor.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-184">An operation of type `(Qubit => Unit)` supports neither the `Adjoint` nor the `Controlled` functor.</span></span> <span data-ttu-id="c0b2d-185">Pokud chceme indikovat, že operace tohoto typu musí podporovat například `Adjoint` funktor, je nutné ji deklarovat jako sousední.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-185">If we want to indicate that an operation of that type has to support e.g. the `Adjoint` functor, we have to declare it as being adjointable.</span></span> <span data-ttu-id="c0b2d-186">K tomu je potřeba použít anotaci `is Adj` k typu.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-186">This is done by using the annotation `is Adj` to the type.</span></span> <span data-ttu-id="c0b2d-187">Podobně `(Qubit => Unit is Ctl)` označuje, že operace tohoto typu podporuje `Controlled` funktor.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-187">Similarly, `(Qubit => Unit is Ctl)` denotes that an operation of that type supports the `Controlled` functor.</span></span> <span data-ttu-id="c0b2d-188">Podíváme se, až budeme projednávat [typy v Q #](xref:microsoft.quantum.language.type-model) obecněji.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-188">We will explore this further when we discuss [types in Q#](xref:microsoft.quantum.language.type-model) more generally.</span></span>

<span data-ttu-id="c0b2d-189">Teď zdůrazňujeme, že můžeme také vracet operace jako součást výstupů, takže můžeme izolovat některé druhy klasických podmíněných logických funkcí jako klasických funkcí, které v podobě operace vrátí popis programového množství.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-189">For now, we emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="c0b2d-190">Jednoduchým příkladem je zvážit příklad přenosu, ve kterém strana, která obdrží 16bitovou klasický zprávu, musí zprávu použít k dekódování jejich qubit do správného portu.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-190">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="c0b2d-191">Můžeme to napsat s ohledem na funkci, která přebírá tyto dvě klasické bity a vrátí správnou operaci dekódování.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-191">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

<span data-ttu-id="c0b2d-192">Tato nová funkce je ve skutečnosti funkcí, v tom, že pokud ji zavoláte se stejnými hodnotami `hereBit` a `thereBit`, vrátíme vždycky stejnou operaci.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-192">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="c0b2d-193">Proto lze dekodér bezpečně spustit uvnitř operací, aniž byste museli mít důvod na to, jak logika dekódování komunikuje s definicemi různých specializací operace.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-193">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="c0b2d-194">To znamená, že jsme izolaci klasické logiky uvnitř funkce a zaručili kompilátor, že volání funkce může být přeobjednáno pomocí impunity, pokud je zachován vstup.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-194">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>

<span data-ttu-id="c0b2d-195">Funkce můžeme také považovat za hodnoty první třídy, protože se vám podíváme podrobněji na [operace a typy funkcí](#operations-and-functions-as-first-class-values).</span><span class="sxs-lookup"><span data-stu-id="c0b2d-195">We can also treat functions as first-class values, as we will see in more detail when we discuss [operations and function types](#operations-and-functions-as-first-class-values).</span></span>

## <a name="partially-applying-operations-and-functions"></a><span data-ttu-id="c0b2d-196">Částečně se aplikují operace a funkce.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-196">Partially Applying Operations and Functions</span></span>

<span data-ttu-id="c0b2d-197">Díky funkcím, které vracejí operace, můžeme použít *částečnou aplikaci*, ve které můžeme zadat jednu nebo více částí vstupu do funkce nebo operace, aniž byste je skutečně volali.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-197">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="c0b2d-198">Například opakované volání `ApplyTwice` výše můžeme indikovat, že nechcete zadat hned, na které qubit by měla vstupní operace platit:</span><span class="sxs-lookup"><span data-stu-id="c0b2d-198">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="c0b2d-199">V takovém případě místní proměnná `twiceOp` obsahuje částečně aplikované operace `ApplyTwice(op, _)`, kde jsou části vstupu, které ještě nebyly určeny, označeny `_`.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-199">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="c0b2d-200">Když ve skutečnosti voláme `twiceOp` v dalším řádku, předáte jako vstup do částečně použité operace všechny zbývající části vstupu do původní operace.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-200">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="c0b2d-201">Proto je výše uvedený fragment kódu prakticky shodný s tím, že se `ApplyTwice(op, target)` přímo, uložte pro to, že jsme zavedli novou místní proměnnou, která nám umožní zpoždění volání při poskytování některých částí vstupu.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-201">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="c0b2d-202">Vzhledem k tomu, že operace, která byla částečně použita, není ve skutečnosti volána, dokud není poskytnut celý vstup, můžeme částečně použít operace i v rámci funkcí.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-202">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="c0b2d-203">V zásadě byla klasická logika v rámci `SquareOperation` mnohem více zapojena, ale je stále izolovaná od zbytku operace zárukami, které kompilátor může nabízet o funkcích.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-203">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="c0b2d-204">Tento přístup se bude používat v rámci celé knihovny Q # pro vyjádření toku klasického řízení způsobem, který se dá snadno použít v rámci programu pro překročení úrovně.</span><span class="sxs-lookup"><span data-stu-id="c0b2d-204">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>
