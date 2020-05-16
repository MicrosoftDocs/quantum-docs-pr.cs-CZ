---
title: 'Operace a funkce v Q #'
description: Definování a volání operací a funkcí, jakož i specializace řízených a sousedících operací.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: bc9695b85b68807801225ccbc903a4622b450768
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431066"
---
# <a name="operations-and-functions-in-q"></a><span data-ttu-id="865ae-103">Operace a funkce v Q #</span><span class="sxs-lookup"><span data-stu-id="865ae-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="865ae-104">Definování nových operací</span><span class="sxs-lookup"><span data-stu-id="865ae-104">Defining New Operations</span></span>

<span data-ttu-id="865ae-105">Operace jsou základem Q #.</span><span class="sxs-lookup"><span data-stu-id="865ae-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="865ae-106">Po deklaraci je lze volat buď z klasických aplikací .NET, například pomocí simulátoru, nebo jinými operacemi v rámci Q #.</span><span class="sxs-lookup"><span data-stu-id="865ae-106">Once declared, they can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="865ae-107">Každá operace definovaná v Q # může potom zavolat libovolný počet dalších operací, včetně integrovaných vnitřních operací definovaných jazykem.</span><span class="sxs-lookup"><span data-stu-id="865ae-107">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="865ae-108">Konkrétní způsob, jakým jsou tyto vnitřní operace definovány, závisí na cílovém počítači.</span><span class="sxs-lookup"><span data-stu-id="865ae-108">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span>
<span data-ttu-id="865ae-109">Při kompilaci je každá operace reprezentována jako typ třídy .NET, který lze poskytnout cílovým počítačům.</span><span class="sxs-lookup"><span data-stu-id="865ae-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="865ae-110">Každý zdrojový soubor Q # může definovat libovolný počet operací.</span><span class="sxs-lookup"><span data-stu-id="865ae-110">Each Q# source file may define any number of operations.</span></span>
<span data-ttu-id="865ae-111">Názvy operací musí být v rámci oboru názvů jedinečné a nemusí být v konfliktu s názvy typu nebo funkce.</span><span class="sxs-lookup"><span data-stu-id="865ae-111">Operation names must be unique within a namespace and may not conflict with type or function names.</span></span>

<span data-ttu-id="865ae-112">Deklarace operace se skládá z klíčového slova `operation` následovaný symbolem, který představuje název operace, typ řazené kolekce členů definující argumenty operace, dvojtečku `:` , anotaci typu, která popisuje typ výsledku operace, volitelně poznámku s charakteristikou operace, levou složenou závorku `{` , tělo deklarace operace a konečnou pravou závorku `}` .</span><span class="sxs-lookup"><span data-stu-id="865ae-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="865ae-113">Každá operace provede vstup, vytvoří výstup a určí implementaci pro jednu nebo více specializací operace.</span><span class="sxs-lookup"><span data-stu-id="865ae-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="865ae-114">Možné specializace a jejich definování nebo volání jsou podrobněji popsané níže.</span><span class="sxs-lookup"><span data-stu-id="865ae-114">The possible specializations, and how to define/call them, are detailed further below.</span></span>
<span data-ttu-id="865ae-115">Prozatím zvažte následující operaci, která definuje jenom výchozí specializaci těla a jako svůj vstup přebírá jeden qubit, a pak na tomto vstupu zavolá vestavěnou <xref:microsoft.quantum.intrinsic.x> operaci:</span><span class="sxs-lookup"><span data-stu-id="865ae-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:microsoft.quantum.intrinsic.x> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="865ae-116">Klíčové slovo `operation` zahájí definici operace a následuje název; zde, `BitFlip` .</span><span class="sxs-lookup"><span data-stu-id="865ae-116">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="865ae-117">Dále je typ vstupu definován jako `Qubit` , společně s názvem `target` pro odkazování na vstup v rámci nové operace.</span><span class="sxs-lookup"><span data-stu-id="865ae-117">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="865ae-118">Podobně `Unit` definuje, že výstup operace je prázdný.</span><span class="sxs-lookup"><span data-stu-id="865ae-118">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="865ae-119">To se používá podobně `void` v jazyce C# a dalších imperativních jazycích a je ekvivalentem `unit` v F # a dalších funkčních jazycích.</span><span class="sxs-lookup"><span data-stu-id="865ae-119">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="865ae-120">Operace mohou také vracet zajímavější typy než `Unit` .</span><span class="sxs-lookup"><span data-stu-id="865ae-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="865ae-121">Například <xref:microsoft.quantum.intrinsic.m> operace vrátí výstup typu `Result` , který představuje vykonání měření.</span><span class="sxs-lookup"><span data-stu-id="865ae-121">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="865ae-122">Můžete buď předat výstup z operace do jiné operace, nebo ho můžete použít s `let` klíčovým slovem k definování nové proměnné.</span><span class="sxs-lookup"><span data-stu-id="865ae-122">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="865ae-123">To umožňuje, aby představovalo klasický výpočet, který komunikuje s provozními operacemi na nízké úrovni, jako je například v [hustém kódování](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span><span class="sxs-lookup"><span data-stu-id="865ae-123">This allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> <span data-ttu-id="865ae-124">Každá operace v Q # přebírá přesně jeden vstup a vrátí přesně jeden výstup.</span><span class="sxs-lookup"><span data-stu-id="865ae-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="865ae-125">Několik vstupů a výstupů je pak znázorněno pomocí *řazených kolekcí členů*, které shromažďují více hodnot dohromady do jedné hodnoty.</span><span class="sxs-lookup"><span data-stu-id="865ae-125">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="865ae-126">Řekněme, že Q # je jazyk řazené kolekce členů (Tuple) v řazené kolekci členů.</span><span class="sxs-lookup"><span data-stu-id="865ae-126">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="865ae-127">Po tomto konceptu `()` by se měla číst jako "prázdná" řazená kolekce členů, která má typ `Unit` .</span><span class="sxs-lookup"><span data-stu-id="865ae-127">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>


## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="865ae-128">Řízené a sousedící operace</span><span class="sxs-lookup"><span data-stu-id="865ae-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="865ae-129">Pokud operace implementuje jednotnou transformaci, jako je případ mnoha operací v Q #, je možné definovat způsob, jakým operace funguje při *adjointed* nebo *řízeném*prvku.</span><span class="sxs-lookup"><span data-stu-id="865ae-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="865ae-130">*Sousedící* specializace operace určuje způsob, jakým operace "INVERT" operace funguje, zatímco *řízená* specializace určuje, jak operace funguje, když je její aplikace podmíněně ve stavu konkrétního registru.</span><span class="sxs-lookup"><span data-stu-id="865ae-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="865ae-131">Adjoints operací je zásadní pro mnoho aspektů výpočetních operací.</span><span class="sxs-lookup"><span data-stu-id="865ae-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="865ae-132">Níže najdete v části [conjugations](#conjugations) jednu takovou situaci popsanou společně s užitečnou programovací technikou Q #.</span><span class="sxs-lookup"><span data-stu-id="865ae-132">Further below, in the [Conjugations](#conjugations) section, you will find one such situation discussed alongside a useful Q# programming technique.</span></span>

<span data-ttu-id="865ae-133">Řízená verze operace je nová operace, která efektivně aplikuje základní operaci pouze v případě, že všechny qubits ovládacího prvku jsou v zadaném stavu.</span><span class="sxs-lookup"><span data-stu-id="865ae-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="865ae-134">Pokud je qubits ovládacího prvku na pozici, pak je základní operace použita v souvislém umístění na příslušné straně.</span><span class="sxs-lookup"><span data-stu-id="865ae-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="865ae-135">Proto se pro generování entanglement často používají kontrolované operace.</span><span class="sxs-lookup"><span data-stu-id="865ae-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="865ae-136">Přirozeně by mohla existovat *řízená sousední* specializace a určení řízené aplikace sousedícího prvku operace.</span><span class="sxs-lookup"><span data-stu-id="865ae-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="865ae-137">Pokud se $U $ jedná o jednotnou transformaci implementovanou operací `U` , pak `Adjoint U` představuje jednotnou transformaci $U ^ \dagger $, což je komplexní sdružená transformace.</span><span class="sxs-lookup"><span data-stu-id="865ae-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="865ae-138">Po sobě jdoucí použití operace a poté jejího souseda se stavem opustí stav beze změny, jak je znázorněno ve skutečnosti, že $UU ^ \dagger = U ^ \dagger U = \id $, matici identity.</span><span class="sxs-lookup"><span data-stu-id="865ae-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="865ae-139">Jednotná reprezentace kontrolované operace je trochu větší odlišit, ale další podrobnosti najdete na stránce s přehledem [výpočetních konceptů: více qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="865ae-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="865ae-140">Následující část popisuje, jak volat tyto různé specializace v kódu Q #.</span><span class="sxs-lookup"><span data-stu-id="865ae-140">The following section describes how to call these various specializations in your Q# code.</span></span>
<span data-ttu-id="865ae-141">Níže najdete podrobné informace o tom, jak definovat operace pro jejich podporu.</span><span class="sxs-lookup"><span data-stu-id="865ae-141">Below, we detail how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="865ae-142">Specializace operací volání</span><span class="sxs-lookup"><span data-stu-id="865ae-142">Calling operation specializations</span></span>

<span data-ttu-id="865ae-143">*Funktor* v Q # je objekt pro vytváření, který definuje novou operaci z jiné operace.</span><span class="sxs-lookup"><span data-stu-id="865ae-143">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="865ae-144">Dvě standardní funktory v Q # jsou `Adjoint` a `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="865ae-144">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="865ae-145">Funktory má přístup k implementaci základní operace při definování implementace nové operace.</span><span class="sxs-lookup"><span data-stu-id="865ae-145">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="865ae-146">Proto může funktory provádět složitější funkce než tradiční funkce vyšší úrovně.</span><span class="sxs-lookup"><span data-stu-id="865ae-146">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="865ae-147">Funktory v systému typů Q # není reprezentace.</span><span class="sxs-lookup"><span data-stu-id="865ae-147">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="865ae-148">V současné době není možné je navazovat na proměnnou nebo předat jako argumenty.</span><span class="sxs-lookup"><span data-stu-id="865ae-148">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="865ae-149">Funktor se používá k tomu, že se použije na operaci a vrátí novou operaci.</span><span class="sxs-lookup"><span data-stu-id="865ae-149">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="865ae-150">Například operace, která je výsledkem použití `Adjoint` funktor pro `Y` operaci, je zapsána jako `Adjoint Y` .</span><span class="sxs-lookup"><span data-stu-id="865ae-150">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="865ae-151">Nová operace se pak může vyvolávat jako jakákoli jiná operace.</span><span class="sxs-lookup"><span data-stu-id="865ae-151">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="865ae-152">Aby operace podporovala aplikace `Adjoint` a/nebo `Controlled` funktory, její návratový typ nutně musí být `Unit` .</span><span class="sxs-lookup"><span data-stu-id="865ae-152">For an operation to support application of the `Adjoint` and/or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="865ae-153">`Adjoint`funktor</span><span class="sxs-lookup"><span data-stu-id="865ae-153">`Adjoint` functor</span></span>

<span data-ttu-id="865ae-154">Proto `Adjoint Y(q1)` používá sousední funktor k `Y` operaci pro vygenerování nové operace a použije tuto novou operaci na `q1` .</span><span class="sxs-lookup"><span data-stu-id="865ae-154">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="865ae-155">Nová operace má stejný podpis a typ jako základní operace `Y` .</span><span class="sxs-lookup"><span data-stu-id="865ae-155">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="865ae-156">Konkrétně Nová operace také povoluje `Adjoint` a povolí `Controlled` pouze v případě základní operace.</span><span class="sxs-lookup"><span data-stu-id="865ae-156">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="865ae-157">Sousední funktor je svou vlastní invertovaná; To znamená, že `Adjoint Adjoint Op` je vždy stejné jako `Op` .</span><span class="sxs-lookup"><span data-stu-id="865ae-157">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="865ae-158">`Controlled`funktor</span><span class="sxs-lookup"><span data-stu-id="865ae-158">`Controlled` functor</span></span>

<span data-ttu-id="865ae-159">Obdobně `Controlled X(controls, target)` aplikuje řízený funktor na `X` operaci pro vygenerování nové operace a použije tuto novou operaci na `controls` a `target` .</span><span class="sxs-lookup"><span data-stu-id="865ae-159">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="865ae-160">V rámci Q # mají řízené verze vždycky převzít pole qubits ovládacího prvku a zadaný stav je vždycky pro všechny qubitsy ovládacího prvku ve stavu výpočty ( `PauliZ` ) `One` , $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="865ae-160">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="865ae-161">Řízení založené na dalších stavech lze dosáhnout použitím příslušné jednotkové operace na qubits ovládacího prvku před řízenou operací a následným použitím inverzních operací po kontrolované operaci.</span><span class="sxs-lookup"><span data-stu-id="865ae-161">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="865ae-162">Například použití `X` operace na qubit ovládacího prvku před a po kontrolované operaci způsobí, že operace bude řídit `Zero` stav ($ \ket {0} $) pro tento qubit; použití `H` operace před a poté bude řídit `PauliX` `One` stav, tj. 1 eigenvalue z Pauli X, $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt {2} $, nikoli `PauliZ` `One` stav.</span><span class="sxs-lookup"><span data-stu-id="865ae-162">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="865ae-163">S ohledem na výraz operace může být pomocí funktor vytvořen nový výraz operace `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="865ae-163">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="865ae-164">Signatura nové operace vychází z podpisu původní operace.</span><span class="sxs-lookup"><span data-stu-id="865ae-164">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="865ae-165">Typ výsledku je stejný, ale vstupní typ je dvě n-tice s polem qubit, které obsahuje ovládací qubit (y) ovládacího prvku jako první prvek a argumenty původní operace jako druhý prvek.</span><span class="sxs-lookup"><span data-stu-id="865ae-165">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="865ae-166">Nová operace podporuje `Controlled` a bude podporovat `Adjoint` pouze v případě, že původní operace proběhla.</span><span class="sxs-lookup"><span data-stu-id="865ae-166">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="865ae-167">V případě, že původní operace trvala pouze jeden argument, budou se sem přicházet ekvivalenty singleton řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="865ae-167">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="865ae-168">Například `Controlled X` je řízená verze `X` operace.</span><span class="sxs-lookup"><span data-stu-id="865ae-168">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="865ae-169">`X`má typ `(Qubit => Unit is Adj + Ctl)` , takže je `Controlled X` typu `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; vzhledem k rovnosti v řazené kolekci členů, je to stejné jako `((Qubit[], Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="865ae-169">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="865ae-170">Pokud základní operace trvala několik argumentů, nezapomeňte do závorek uzavřít odpovídající argumenty kontrolované verze operace v závorkách, aby je bylo možné převést na řazenou kolekci členů.</span><span class="sxs-lookup"><span data-stu-id="865ae-170">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="865ae-171">Například `Controlled Rz` je řízená verze `Rz` operace.</span><span class="sxs-lookup"><span data-stu-id="865ae-171">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="865ae-172">`Rz`má typ `((Double, Qubit) => Unit is Adj + Ctl)` , takže `Controlled Rz` je typu `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="865ae-172">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="865ae-173">Proto `Controlled Rz(controls, (0.1, target))` by bylo platné vyvolání `Controlled Rz` (Poznamenejte si závorky kolem `0.1, target` ).</span><span class="sxs-lookup"><span data-stu-id="865ae-173">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="865ae-174">Jako další příklad `CNOT(control, target)` lze implementovat jako `Controlled X([control], target)` .</span><span class="sxs-lookup"><span data-stu-id="865ae-174">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="865ae-175">Pokud by cíl měl být řízen 2 Control qubits (CCNOT), můžeme použít `Controlled X([control1, control2], target)` příkaz.</span><span class="sxs-lookup"><span data-stu-id="865ae-175">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="865ae-176">`Controlled`Funktory a dokončí `Adjoint` dojíždění, takže není rozdíl mezi použitím `Controlled Adjoint Op` nebo `Adjoint Controlled Op` .</span><span class="sxs-lookup"><span data-stu-id="865ae-176">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="865ae-177">Definování řízených a sousedících implementací</span><span class="sxs-lookup"><span data-stu-id="865ae-177">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="865ae-178">V předchozích příkladech deklarace operace jsou operace `BitFlip` a `DecodeSuperdense` byly definovány s podpisy a v `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="865ae-178">In the first operation declaration examples above, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="865ae-179">Jak `DecodeSuperdense` zahrnuje měření, nejedná se o jednotkovou operaci, a proto by nemohly nastavovat žádné specializace nesousedících a (vrátit související požadavek, který taková operace vrátí `Unit` ).</span><span class="sxs-lookup"><span data-stu-id="865ae-179">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="865ae-180">Jak ale `BitFlip` jednoduše provede jednotnou <xref:microsoft.quantum.intrinsic.x> operaci, můžeme ji definovat s oběma specializacemi.</span><span class="sxs-lookup"><span data-stu-id="865ae-180">However, as `BitFlip` simply performs the unitary <xref:microsoft.quantum.intrinsic.x> operation, we could have defined it with both specializations.</span></span>

<span data-ttu-id="865ae-181">Zde uvádíme podrobné informace o tom, jak zahrnout existenci specializací do deklarací operací Q #, čímž jim umožníte, aby je mohli volat ve spojení s `Adjoint` funktory a/nebo `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="865ae-181">Here, we detail how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` and/or `Controlled` functors.</span></span>
<span data-ttu-id="865ae-182">[Níže](#circumstances-for-validly-defining-specializations)uvádíme některé z situací, ve kterých je buď platná, nebo není platná, aby bylo možné deklarovat určité specializace.</span><span class="sxs-lookup"><span data-stu-id="865ae-182">Further [below](#circumstances-for-validly-defining-specializations), we describe some of the situations in which it is either valid or not valid to declare certain specializations.</span></span>

<span data-ttu-id="865ae-183">Charakteristiky operace definují, jaké druhy funktory lze použít pro deklarovanou operaci a jaký má vliv.</span><span class="sxs-lookup"><span data-stu-id="865ae-183">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="865ae-184">Existence těchto specializací se dá deklarovat jako součást signatury operace, konkrétně prostřednictvím poznámky s charakteristikou operace: buď `is Adj` , `is Ctl` nebo `is Adj + Ctl` .</span><span class="sxs-lookup"><span data-stu-id="865ae-184">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="865ae-185">Vlastní implementace každé specializace může být *implicitně* nebo *explicitně* definovaná.</span><span class="sxs-lookup"><span data-stu-id="865ae-185">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="865ae-186">Implicitní určení implementací</span><span class="sxs-lookup"><span data-stu-id="865ae-186">Implicitly specifying implementations</span></span>

<span data-ttu-id="865ae-187">V tomto případě se tělo deklarace operace skládá výhradně z výchozí implementace.</span><span class="sxs-lookup"><span data-stu-id="865ae-187">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="865ae-188">Příklad:</span><span class="sxs-lookup"><span data-stu-id="865ae-188">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="865ae-189">V tomto případě se odpovídající implementace pro každou z těchto implicitně deklarované specializace automaticky vygeneruje kompilátorem, aby se provedla, pokud se `Adjoint` `Controlled` používají nebo funktory.</span><span class="sxs-lookup"><span data-stu-id="865ae-189">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="865ae-190">Volání by tedy způsobilo, `Adjoint PrepareEntangledPair` že kompilátor implementuje sousední metodu `CNOT` a poté sousední `H` .</span><span class="sxs-lookup"><span data-stu-id="865ae-190">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="865ae-191">Tyto jednotlivé operace jsou samostatně sousedící, takže výsledná `Adjoint PrepareEntangledPair` operace by se jednoduše použila k použití `CNOT(here, there)` a pak `H(here)` .</span><span class="sxs-lookup"><span data-stu-id="865ae-191">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="865ae-192">Proto to můžeme použít k zapsání `DecodeSuperdense` příkladu v kompaktním formátu pomocí sousedícího prvku `PrepareEntangledPair` pro transformaci stavu entangled zpět na dvojici unentangled qubits:</span><span class="sxs-lookup"><span data-stu-id="865ae-192">Hence we can use this to write the `DecodeSuperdense` example above more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="865ae-193">Poznámka s charakteristikami operace v deklaraci je užitečná pro zajištění, že kompilátor automaticky generuje další specializace na základě výchozí implementace.</span><span class="sxs-lookup"><span data-stu-id="865ae-193">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="865ae-194">Při navrhování operací pro použití s funktory je potřeba vzít v úvahu několik důležitých omezení.</span><span class="sxs-lookup"><span data-stu-id="865ae-194">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="865ae-195">Nejdůležitější specializace pro operaci, která používá výstupní hodnotu jakékoli jiné operace, *nelze* automaticky generovat kompilátorem, protože je nejednoznačná, jak změnit pořadí příkazů v takové operaci pro získání stejného efektu.</span><span class="sxs-lookup"><span data-stu-id="865ae-195">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="865ae-196">Proto je často vhodné explicitně zadat různé implementace.</span><span class="sxs-lookup"><span data-stu-id="865ae-196">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="865ae-197">Explicitní určení implementací</span><span class="sxs-lookup"><span data-stu-id="865ae-197">Explicitly specifying implementations</span></span>

<span data-ttu-id="865ae-198">V případě, že se implementace nemůže generovat kompilátorem, je možné ji explicitně zadat.</span><span class="sxs-lookup"><span data-stu-id="865ae-198">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="865ae-199">Tyto explicitní deklarace specializace můžou sestávat z vhodné *direktivy generace* nebo uživatelsky definované implementace.</span><span class="sxs-lookup"><span data-stu-id="865ae-199">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="865ae-200">Poskytujeme celou řadu možností s příklady níže.</span><span class="sxs-lookup"><span data-stu-id="865ae-200">Here we provide the full range of possibilities, with examples following below.</span></span>


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="865ae-201">Explicitní deklarace specializace</span><span class="sxs-lookup"><span data-stu-id="865ae-201">Explicit specialization declarations</span></span>

<span data-ttu-id="865ae-202">Operace Q # můžou obsahovat následující explicitní deklarace specializace:</span><span class="sxs-lookup"><span data-stu-id="865ae-202">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="865ae-203">`body`Specializace určuje implementaci operace bez použití funktory.</span><span class="sxs-lookup"><span data-stu-id="865ae-203">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="865ae-204">`adjoint`Specializace určuje implementaci operace s `Adjoint` použitým funktor.</span><span class="sxs-lookup"><span data-stu-id="865ae-204">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="865ae-205">`controlled`Specializace určuje implementaci operace s `Controlled` použitým funktor.</span><span class="sxs-lookup"><span data-stu-id="865ae-205">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="865ae-206">`controlled adjoint`Specializace určuje implementaci operace s `Adjoint` `Controlled` použitým funktory a.</span><span class="sxs-lookup"><span data-stu-id="865ae-206">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="865ae-207">Tato specializace může mít také název `adjoint controlled` , protože dvě funktory dojíždění.</span><span class="sxs-lookup"><span data-stu-id="865ae-207">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="865ae-208">Specializace operace se skládá z tagu specializace (např. `body` nebo `adjoint` atd.) následovaných jedním z těchto:</span><span class="sxs-lookup"><span data-stu-id="865ae-208">An operation specialization consists of the specialization tag (e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="865ae-209">Explicitní deklarace, jak je popsáno níže.</span><span class="sxs-lookup"><span data-stu-id="865ae-209">An explicit declaration as described below.</span></span>
- <span data-ttu-id="865ae-210">*Direktiva* , která instruuje kompilátor, *jak* vygenerovat specializaci, jedna z těchto:</span><span class="sxs-lookup"><span data-stu-id="865ae-210">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="865ae-211">`intrinsic`, což znamená, že specializace je poskytována cílovým počítačem.</span><span class="sxs-lookup"><span data-stu-id="865ae-211">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="865ae-212">`distribute`, které lze použít s `controlled` `controlled adjoint` specializacemi a.</span><span class="sxs-lookup"><span data-stu-id="865ae-212">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="865ae-213">Při použití s se `controlled` označuje, že kompilátor má vypočítat specializaci použitím `Controlled` pro všechny operace v `body` .</span><span class="sxs-lookup"><span data-stu-id="865ae-213">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="865ae-214">Při použití s se `controlled adjoint` označuje, že kompilátor má vypočítat specializaci použitím `Controlled` pro všechny operace v `adjoint` specializaci.</span><span class="sxs-lookup"><span data-stu-id="865ae-214">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="865ae-215">`invert`, což označuje, že má kompilátor vypočítat `adjoint` specializaci `body` vrácením, tj. zrušením pořadí operací a aplikováním sousedního na každé z nich.</span><span class="sxs-lookup"><span data-stu-id="865ae-215">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="865ae-216">Při použití s se `adjoint controlled` označuje, že kompilátor má vypočítat specializaci vrácením `controlled` specializace.</span><span class="sxs-lookup"><span data-stu-id="865ae-216">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="865ae-217">`self`, abyste označili, že specializace sousedícít je stejná jako `body` specializace.</span><span class="sxs-lookup"><span data-stu-id="865ae-217">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="865ae-218">To je platné pro `adjoint` `adjoint controlled` specializace a.</span><span class="sxs-lookup"><span data-stu-id="865ae-218">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="865ae-219">Pro `adjoint controlled` `self` znamená, že `adjoint controlled` specializace je stejná jako `controlled` specializace.</span><span class="sxs-lookup"><span data-stu-id="865ae-219">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="865ae-220">`auto`, abyste označili, že má kompilátor vybrat vhodnou direktivu, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="865ae-220">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="865ae-221">`auto`nemůže být použit pro `body` specializaci.</span><span class="sxs-lookup"><span data-stu-id="865ae-221">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="865ae-222">Direktivy a `auto` všechny vyžadují uzavírací středník `;` .</span><span class="sxs-lookup"><span data-stu-id="865ae-222">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="865ae-223">`auto`Direktiva se přeloží na následující direktivu generace, pokud je k `body` dispozici explicitní deklarace:</span><span class="sxs-lookup"><span data-stu-id="865ae-223">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="865ae-224">`adjoint`Specializace je vygenerována podle direktivy `invert` .</span><span class="sxs-lookup"><span data-stu-id="865ae-224">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="865ae-225">`controlled`Specializace je vygenerována podle direktivy `distribute` .</span><span class="sxs-lookup"><span data-stu-id="865ae-225">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="865ae-226">`adjoint controlled`Specializace je generována podle direktivy `invert` `controlled` , pokud je zadána explicitní deklarace, ale nikoli jedna pro `adjoint` a `distribute` jinak.</span><span class="sxs-lookup"><span data-stu-id="865ae-226">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="865ae-227">Pokud je operace samostatně sousedící, explicitně určete buď sousední, nebo řízená sousední specializace pomocí direktivy generace, `self` aby kompilátor mohl používat tyto informace pro účely optimalizace.</span><span class="sxs-lookup"><span data-stu-id="865ae-227">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="865ae-228">Deklarace specializace obsahující uživatelsky definovanou implementaci se skládá z argumentů řazené kolekce členů následovaný blokem příkazu Q #, který implementuje specializaci.</span><span class="sxs-lookup"><span data-stu-id="865ae-228">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="865ae-229">V seznamu argumentů `...` se používá k reprezentaci argumentů deklarovaných pro operaci jako celku.</span><span class="sxs-lookup"><span data-stu-id="865ae-229">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="865ae-230">Pro `body` a `adjoint` by měl seznam argumentů vždy být `(...)` ; pro `controlled` a by `adjoint controlled` měl být seznam argumentů symbol reprezentující pole qubits ovládacího prvku následovaný znakem `...` uzavřeným v závorkách, například `(controls,...)` .</span><span class="sxs-lookup"><span data-stu-id="865ae-230">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="865ae-231">Příklady</span><span class="sxs-lookup"><span data-stu-id="865ae-231">Examples</span></span>

<span data-ttu-id="865ae-232">Deklarace operace může být jednoduchá, jak je uvedeno níže, což definuje primitivní operaci Pauli X:</span><span class="sxs-lookup"><span data-stu-id="865ae-232">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="865ae-233">Všimněte si, že sousední funkce operace Pauli X je definována s direktivou, `self` protože podle definice `X` je její vlastní inverzní.</span><span class="sxs-lookup"><span data-stu-id="865ae-233">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="865ae-234">Výše uvedený kód `PrepareEntangledPair` je podobný kódu jako v následujícím příkladu, který obsahuje explicitní deklarace specializace:</span><span class="sxs-lookup"><span data-stu-id="865ae-234">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="865ae-235">Klíčové slovo `auto` označuje, že by měl kompilátor určit, jak se má vygenerovat implementace specializace.</span><span class="sxs-lookup"><span data-stu-id="865ae-235">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="865ae-236">Uživatelsky definovaná implementace specializace</span><span class="sxs-lookup"><span data-stu-id="865ae-236">User-defined specialization implementation</span></span>

<span data-ttu-id="865ae-237">Pokud kompilátor nemůže vygenerovat implementaci pro určitou specializaci automaticky, nebo pokud lze zadat účinnější implementaci, pak může být implementace také ručně definována.</span><span class="sxs-lookup"><span data-stu-id="865ae-237">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

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
<span data-ttu-id="865ae-238">V předchozím příkladu označuje, `adjoint invert;` že specializace sousedící-je vygenerována invertující implementaci těla a `controlled adjoint invert;` označuje, že řízená sousední specializace je generována obrácenou implementací řízené specializace.</span><span class="sxs-lookup"><span data-stu-id="865ae-238">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="865ae-239">Pokud je nutné explicitně deklarovat jednu nebo více specializací, než je výchozí tělo, musí být implementace pro výchozí tělo zabalena do vhodné deklarace specializace:</span><span class="sxs-lookup"><span data-stu-id="865ae-239">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="865ae-240">Okolnosti pro platné definování specializací</span><span class="sxs-lookup"><span data-stu-id="865ae-240">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="865ae-241">Deklarace operací s přiléhajícím/řízeným</span><span class="sxs-lookup"><span data-stu-id="865ae-241">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="865ae-242">Je možné zadat operaci bez sousedících nebo řízených verzí.</span><span class="sxs-lookup"><span data-stu-id="865ae-242">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="865ae-243">Například operace měření nemají ani, protože nejsou inverzi nebo ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="865ae-243">For instance, measurement operations have neither, because they are not invertible or controllable.</span></span>

<span data-ttu-id="865ae-244">Operace podporuje rozhraní `Adjoint` a/nebo `Controlled` funktory, pokud jeho deklarace obsahuje implicitní nebo explicitní deklaraci příslušných specializací.</span><span class="sxs-lookup"><span data-stu-id="865ae-244">An operation supports the `Adjoint` and/or `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="865ae-245">Explicitně deklarovaná sousední a řízená specializace implikuje existenci sousední specializace/řízené specializace.</span><span class="sxs-lookup"><span data-stu-id="865ae-245">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="865ae-246">Pro operaci, jejíž tělo obsahuje smyčky opakování až po úspěšné, nastavte příkazy, měření, návratové příkazy nebo volání jiných operací, které nepodporují `Adjoint` funktor, automatické generování sousední specializace přiléhající podle `invert` `auto` direktivy or není možné.</span><span class="sxs-lookup"><span data-stu-id="865ae-246">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="865ae-247">Pro operaci, jejíž tělo obsahuje volání do jiných operací, které nepodporují `Controlled` funktor, není možné automaticky generovat řízená specializaci následující po `distribute` `auto` direktivě or.</span><span class="sxs-lookup"><span data-stu-id="865ae-247">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="865ae-248">Řízený sousedící</span><span class="sxs-lookup"><span data-stu-id="865ae-248">Controlled Adjoint</span></span>

<span data-ttu-id="865ae-249">Řízená verze inřízených operací operace určuje, jak je implementována verze sousedících operací s řízenou počátečními událostmi.</span><span class="sxs-lookup"><span data-stu-id="865ae-249">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="865ae-250">Je právní určení operace bez řízené sousední verze; například operace měření nemají řízenou sousední verzi, protože nejsou ani ovladatelné ani inverzi.</span><span class="sxs-lookup"><span data-stu-id="865ae-250">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="865ae-251">Řízená sousední specializace pro operaci musí existovat, pokud je a jenom v případě, že existují sousední i řízená specializace.</span><span class="sxs-lookup"><span data-stu-id="865ae-251">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="865ae-252">V takovém případě je existence řízené specializace instalovaná a příslušná specializace je vygenerována kompilátorem, pokud nebyla explicitně definována žádná implementace.</span><span class="sxs-lookup"><span data-stu-id="865ae-252">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="865ae-253">Pro operaci, jejíž tělo obsahuje volání na jiné operace, které nemají řízenou nekontrolovanou verzi, automatické generování sousední specializace na základě `invert` `distribute` `auto` direktivy nebo není možné.</span><span class="sxs-lookup"><span data-stu-id="865ae-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="865ae-254">Kompatibilita typů</span><span class="sxs-lookup"><span data-stu-id="865ae-254">Type Compatibility</span></span>

<span data-ttu-id="865ae-255">Operaci s dalšími podporovanými funktory se dají použít kdekoli operace s menším počtem funktory, ale je očekáván stejný podpis.</span><span class="sxs-lookup"><span data-stu-id="865ae-255">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="865ae-256">Například operaci typu `(Qubit => Unit is Adj)` lze použít všude, kde `(Qubit => Unit)` je očekávána operace typu.</span><span class="sxs-lookup"><span data-stu-id="865ae-256">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="865ae-257">Q # je *kovariantní* s ohledem na možné návratové typy: volat, která vrací typ, `'A` je kompatibilní s typem volat se stejným vstupním typem a typem výsledku, který `'A` je kompatibilní s.</span><span class="sxs-lookup"><span data-stu-id="865ae-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="865ae-258">Q # je *kontravariantní* s ohledem na typy vstupu: dá se volat, který přebírá typ `'A` jako vstup je kompatibilní s typem, který se dá volat se stejným typem výsledku a vstupním typem, který je kompatibilní s `'A` .</span><span class="sxs-lookup"><span data-stu-id="865ae-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="865ae-259">To znamená s ohledem na následující definice:</span><span class="sxs-lookup"><span data-stu-id="865ae-259">That is, given the following definitions:</span></span>

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

<span data-ttu-id="865ae-260">platí následující:</span><span class="sxs-lookup"><span data-stu-id="865ae-260">the following are true:</span></span>

- <span data-ttu-id="865ae-261">Funkci `ConjugateInvertWith` lze vyvolat pomocí `inner` argumentu buď `Invert` nebo `ApplyUnitary` .</span><span class="sxs-lookup"><span data-stu-id="865ae-261">The function `ConjugateInvertWith` may be invoked with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="865ae-262">Funkce `ConjugateUnitaryWith` může být vyvolána s `inner` argumentem `ApplyUnitary` , ale ne `Invert` .</span><span class="sxs-lookup"><span data-stu-id="865ae-262">The function `ConjugateUnitaryWith` may be invoked with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="865ae-263">Hodnota typu `(Qubit[] => Unit is Adj + Ctl)` může být vrácena z `ConjugateInvertWith` .</span><span class="sxs-lookup"><span data-stu-id="865ae-263">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="865ae-264">Otázka č. 0,3 představila značný rozdíl v chování uživatelsky definovaných typů.</span><span class="sxs-lookup"><span data-stu-id="865ae-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="865ae-265">Uživatelsky definované typy jsou považovány za zabalenou verzi základního typu, nikoli jako podtyp.</span><span class="sxs-lookup"><span data-stu-id="865ae-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="865ae-266">To znamená, že hodnota uživatelsky definovaného typu není použitelná, pokud je očekávána hodnota základního typu.</span><span class="sxs-lookup"><span data-stu-id="865ae-266">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>


### <a name="conjugations"></a><span data-ttu-id="865ae-267">Conjugations</span><span class="sxs-lookup"><span data-stu-id="865ae-267">Conjugations</span></span>

<span data-ttu-id="865ae-268">Na rozdíl od klasických bitů, uvolňování paměti je trochu více zapojeno, protože nevidomé resetující qubits může mít nežádoucí důsledky zbývajícího výpočtu, pokud qubits stále entangled.</span><span class="sxs-lookup"><span data-stu-id="865ae-268">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="865ae-269">K tomu je možné se vyhnout tím, že před uvolněním paměti vykonává správné "rušení".</span><span class="sxs-lookup"><span data-stu-id="865ae-269">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="865ae-270">Běžným vzorem pro výpočetní výkon je následující:</span><span class="sxs-lookup"><span data-stu-id="865ae-270">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="865ae-271">Od naší verze 0,9 podporujeme příkaz conjugation, který implementuje transformaci uvedenou výše.</span><span class="sxs-lookup"><span data-stu-id="865ae-271">Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="865ae-272">Pomocí tohoto příkazu `ApplyWith` může být operace implementována následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="865ae-272">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="865ae-273">Takový příkaz conjugation zjevně je mnohem užitečnější, pokud vnější a vnitřní transformace nejsou snadno dostupné jako operace, ale místo toho jsou vhodnější pro popis pomocí bloku skládajícího se z několika příkazů.</span><span class="sxs-lookup"><span data-stu-id="865ae-273">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="865ae-274">Inverzní transformace pro příkazy definované v rámci bloku je automaticky generována kompilátorem a provedena po dokončení bloku Apply.</span><span class="sxs-lookup"><span data-stu-id="865ae-274">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span>
<span data-ttu-id="865ae-275">Vzhledem k tomu, že jakékoli proměnlivé proměnné použité jako součást bloku nelze znovu svázat v bloku Apply, je vygenerovaná transformace zaručena jako sousední v výpočtu v bloku.</span><span class="sxs-lookup"><span data-stu-id="865ae-275">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 


## <a name="defining-new-functions"></a><span data-ttu-id="865ae-276">Definování nových funkcí</span><span class="sxs-lookup"><span data-stu-id="865ae-276">Defining New Functions</span></span>

<span data-ttu-id="865ae-277">Funkce jsou čistě deterministické, klasické rutiny v Q #, které se liší od operací v tom, že nemají dovoleno mít žádné účinky přesahující výpočet výstupní hodnoty.</span><span class="sxs-lookup"><span data-stu-id="865ae-277">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="865ae-278">Konkrétně funkce nemohou volat operace; působit na, přidělit nebo vypůjčit qubits; Ukázka náhodných čísel; nebo jinak závisí na stavu nad rámec vstupní hodnoty s funkcí.</span><span class="sxs-lookup"><span data-stu-id="865ae-278">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="865ae-279">V důsledku toho jsou funkce Q # *čisté*, v tom, že vždycky mapují stejné vstupní hodnoty na stejné výstupní hodnoty.</span><span class="sxs-lookup"><span data-stu-id="865ae-279">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="865ae-280">Kompilátor Q # umožňuje bezpečně změnit pořadí, jak a kdy jsou funkce volány při generování specializací operace.</span><span class="sxs-lookup"><span data-stu-id="865ae-280">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="865ae-281">Každý zdrojový soubor Q # může definovat libovolný počet funkcí.</span><span class="sxs-lookup"><span data-stu-id="865ae-281">Each Q# source file may define any number of functions.</span></span>
<span data-ttu-id="865ae-282">Názvy funkcí musí být v rámci oboru názvů jedinečné a nemusí být v konfliktu s názvy operace nebo typu.</span><span class="sxs-lookup"><span data-stu-id="865ae-282">Function names must be unique within a namespace and may not conflict with operation or type names.</span></span>

<span data-ttu-id="865ae-283">Definování funkce funguje podobně jako při definování operace s tím rozdílem, že pro funkci nelze definovat žádné sousedící a řízené specializace.</span><span class="sxs-lookup"><span data-stu-id="865ae-283">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="865ae-284">Například:</span><span class="sxs-lookup"><span data-stu-id="865ae-284">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="865ae-285">nebo</span><span class="sxs-lookup"><span data-stu-id="865ae-285">or</span></span> 

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="865ae-286">Klasická logika v Functions = = dobrá</span><span class="sxs-lookup"><span data-stu-id="865ae-286">Classical logic in functions == good</span></span>

<span data-ttu-id="865ae-287">Pokaždé, když je to možné, je vhodné napsat klasický Logic z pojmu Functions namísto operací, aby bylo možné snadněji použít v rámci operací.</span><span class="sxs-lookup"><span data-stu-id="865ae-287">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="865ae-288">Pokud jsme například napsali `Square` deklaraci uvedenou výše jako *operaci*, kompilátor by nedokázal zaručit, že volání stejného vstupu by konzistentně vytvořilo stejné výstupy.</span><span class="sxs-lookup"><span data-stu-id="865ae-288">For example, if we had written the `Square` declaration above as an *operation*, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="865ae-289">Pro podtržení rozdílu mezi funkcemi a operacemi zvažte problém klasického vzorkování náhodného čísla v rámci operace Q #:</span><span class="sxs-lookup"><span data-stu-id="865ae-289">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="865ae-290">Pokaždé, když se `U` zavolá, bude mít jinou akci `target` .</span><span class="sxs-lookup"><span data-stu-id="865ae-290">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="865ae-291">Konkrétně kompilátor nemůže zaručit, že pokud jsme přidali `adjoint auto` deklaraci specializace do `U` , pak `U(target); Adjoint U(target);` funguje jako identita (tj. jako No-OP).</span><span class="sxs-lookup"><span data-stu-id="865ae-291">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="865ae-292">To je v rozporu s definicí sousedícího, které jsme viděli v [vektorech a maticích](xref:microsoft.quantum.concepts.vectors), jako je povolení automatického generování sousední specializace v operaci, kde byla volána operace, <xref:microsoft.quantum.math.randomreal> by narušila záruky poskytované kompilátorem <xref:microsoft.quantum.math.randomreal> . Jedná se o operaci, pro kterou neexistuje žádná sousední nebo řízená verze.</span><span class="sxs-lookup"><span data-stu-id="865ae-292">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="865ae-293">Na druhé straně, povolení volání funkcí jako `Square` je bezpečné, v tom, že kompilátor může zajistit, že musí zachovávat pouze vstup, aby bylo možné `Square` zachovat stabilní výstup.</span><span class="sxs-lookup"><span data-stu-id="865ae-293">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="865ae-294">Proto izolování co nejvíc klasických logických funkcí do funkcí umožňuje snadno znovu použít tuto logiku v jiných funkcích a operacích.</span><span class="sxs-lookup"><span data-stu-id="865ae-294">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="865ae-295">Obecné (typ – parametrizované) – volatelné</span><span class="sxs-lookup"><span data-stu-id="865ae-295">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="865ae-296">Mnoho funkcí a operací, které můžeme chtít definovat, se ve skutečnosti nespoléhá na typy jejich vstupů, ale místo toho pouze implicitně používají jejich typy prostřednictvím jiné funkce nebo operace.</span><span class="sxs-lookup"><span data-stu-id="865ae-296">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="865ae-297">Představte si třeba koncept *mapy* společný pro mnoho funkčních jazyků. po předané funkci $f (x) $ a kolekci hodnot $ \{ x_1, x_2, \dots, x_n \} $, map vrátí novou kolekci $ \{ f (x_1), f (x_2), \dots, f (x_n) \} $.</span><span class="sxs-lookup"><span data-stu-id="865ae-297">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="865ae-298">K implementaci tohoto v Q # můžeme využít výhod těchto funkcí jako první třídy.</span><span class="sxs-lookup"><span data-stu-id="865ae-298">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="865ae-299">Pojďme si napsat rychlý příklad `Map` , při použití ★ jako zástupného symbolu, a přitom zjistíme, jaké typy potřebujeme.</span><span class="sxs-lookup"><span data-stu-id="865ae-299">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="865ae-300">Všimněte si, že tato funkce vypadá velmi stejně bez ohledu na to, jaké vlastní typy nahrazujíme.</span><span class="sxs-lookup"><span data-stu-id="865ae-300">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="865ae-301">Mapa z celých čísel na Paul, například vypadá podobně jako mapa z čísel s plovoucí desetinnou čárkou na řetězce:</span><span class="sxs-lookup"><span data-stu-id="865ae-301">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="865ae-302">V podstatě jsme mohli napsat verzi `Map` pro každou dvojici typů, ke kterým došlo, ale to přináší řadu potíží.</span><span class="sxs-lookup"><span data-stu-id="865ae-302">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="865ae-303">Pokud například v nástroji zjistíte chybu, je `Map` nutné zajistit, aby se oprava používala jednotně napříč všemi verzemi nástroje `Map` .</span><span class="sxs-lookup"><span data-stu-id="865ae-303">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="865ae-304">Kromě toho, Pokud vytvoříme nové řazené kolekce členů nebo UDT, je teď také potřeba vytvořit nový `Map` pro přechod k novému typu.</span><span class="sxs-lookup"><span data-stu-id="865ae-304">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="865ae-305">I když se jedná o malý počet takových funkcí, protože shromažďujeme více a více funkcí stejné formy jako `Map` , náklady na zavedení nových typů se v poměrně krátkém pořadí stávají nepřiměřeně velkým.</span><span class="sxs-lookup"><span data-stu-id="865ae-305">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="865ae-306">Mnohé z těchto potíží se ale nedostaly do tohoto kompilátoru informace, které potřebuje k tomu, abyste zjistili, jak různé verze nástroje `Map` souvisejí.</span><span class="sxs-lookup"><span data-stu-id="865ae-306">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="865ae-307">Chceme, aby kompilátor považoval `Map` jako nějaký druh matematické funkce z *typů* q # do funkce q #.</span><span class="sxs-lookup"><span data-stu-id="865ae-307">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="865ae-308">Tento pojem je formální tím, že povoluje funkce a operace pro *parametry typu*a také jejich běžné parametry řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="865ae-308">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="865ae-309">V předchozích příkladech si chceme představit `Map` jako parametry typu `Int, Pauli` v prvním a `Double, String` druhém případě.</span><span class="sxs-lookup"><span data-stu-id="865ae-309">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="865ae-310">Ve většině případů lze tyto parametry typu použít, jako by se jednalo o běžné typy: používáme hodnoty parametrů typu k vytváření polí a řazených kolekcí členů, volání funkcí a operací a přiřazení k běžným nebo proměnlivým proměnným.</span><span class="sxs-lookup"><span data-stu-id="865ae-310">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="865ae-311">Největší případ nepřímých závislostí je qubits, kde program Q # nemůže přímo spoléhat na strukturu `Qubit` typu, ale **musí** předat takové typy jiným operacím a funkcím.</span><span class="sxs-lookup"><span data-stu-id="865ae-311">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="865ae-312">Po návratu do výše uvedeného příkladu vidíte, že potřebujeme `Map` mít parametry typu, jeden pro reprezentaci vstupu `fn` a druhý, který představuje výstup z `fn` .</span><span class="sxs-lookup"><span data-stu-id="865ae-312">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="865ae-313">V Q # se to zapisuje přidáním lomených závorek (to znamená `<>` Not brakets $ \braket {} $!) za názvem funkce nebo operace v deklaraci a výpisem každého parametru typu.</span><span class="sxs-lookup"><span data-stu-id="865ae-313">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="865ae-314">Název každého parametru typu musí začínat značkou `'` , která značí, že se jedná o parametr typu a ne běžný typ (označovaný také jako *konkrétní* typ).</span><span class="sxs-lookup"><span data-stu-id="865ae-314">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="865ae-315">Pro `Map` zapisujeme:</span><span class="sxs-lookup"><span data-stu-id="865ae-315">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="865ae-316">Všimněte si, že definice `Map<'Input, 'Output>` vypadá extrémně podobně jako verze, které jsme předtím napsali.</span><span class="sxs-lookup"><span data-stu-id="865ae-316">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="865ae-317">Jediným rozdílem je, že explicitně uvědomili kompilátor, který `Map` přímo nezávisí na tom `'Input` , co a `'Output` jsou, ale funguje pro všechny dva typy pomocí nepřímo prostřednictvím `fn` .</span><span class="sxs-lookup"><span data-stu-id="865ae-317">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="865ae-318">Po definování `Map<'Input, 'Output>` tímto způsobem můžeme zavolat, jako by šlo o běžnou funkci:</span><span class="sxs-lookup"><span data-stu-id="865ae-318">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="865ae-319">Zápis obecných funkcí a operací je jedním z míst, kde "řazená kolekce členů" v řazené kolekci členů "je velmi užitečným způsobem, jak se zamyslet na funkce a operace Q #.</span><span class="sxs-lookup"><span data-stu-id="865ae-319">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="865ae-320">Vzhledem k tomu, že každá funkce používá přesně jeden vstup a vrátí přesně jeden výstup, vstup typu `'T -> 'U` odpovídá *libovolné* funkci Q #.</span><span class="sxs-lookup"><span data-stu-id="865ae-320">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="865ae-321">Podobně lze každou operaci předat do vstupu typu `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="865ae-321">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="865ae-322">V druhém příkladu zvažte, jak napsat funkci, která vrací kompozici dvou dalších funkcí:</span><span class="sxs-lookup"><span data-stu-id="865ae-322">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="865ae-323">Tady je nutné přesně určit, co `A` , `B` a `C` jsou, a proto silně omezit nástroj naší nové `Compose` funkce.</span><span class="sxs-lookup"><span data-stu-id="865ae-323">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="865ae-324">Po všech případech `Compose` závisí pouze na `A` , a `B` a `C` *pomocí* `innerFn` a `outerFn` .</span><span class="sxs-lookup"><span data-stu-id="865ae-324">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="865ae-325">Alternativně můžeme přidat parametry typu k tomu, aby `Compose` označovali, že funguje pro *všechny* `A` , `B` a `C` , pokud se tyto parametry shodují s hodnotami, které očekává `innerFn` a `outerFn` :</span><span class="sxs-lookup"><span data-stu-id="865ae-325">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="865ae-326">Standardní knihovny Q # poskytují rozsah takových operací, které jsou parametrizované pro typ, a usnadňují tak vyjádření toku řízení vyšším řádu.</span><span class="sxs-lookup"><span data-stu-id="865ae-326">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="865ae-327">Tyto postupy jsou podrobněji popsány v [příručce ke standardní knihovně Q #](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="865ae-327">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="865ae-328">Se bude volat jako hodnoty první třídy.</span><span class="sxs-lookup"><span data-stu-id="865ae-328">Callables as First-Class Values</span></span>

<span data-ttu-id="865ae-329">Jednou z kritických postupů pro rozhodnutí o toku řízení a klasické logice pomocí funkcí místo operací je využití těchto operací a funkcí v Q # jsou *prvními třídami*.</span><span class="sxs-lookup"><span data-stu-id="865ae-329">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="865ae-330">To znamená, že jsou všechny hodnoty v jazyce v pravém.</span><span class="sxs-lookup"><span data-stu-id="865ae-330">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="865ae-331">Například následující je naprosto platný kód Q #, pokud je trochu nepřímá:</span><span class="sxs-lookup"><span data-stu-id="865ae-331">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="865ae-332">Hodnota proměnné `ourH` ve výše uvedeném fragmentu kódu je pak operace <xref:microsoft.quantum.intrinsic.h> , například, můžeme zavolat tuto hodnotu jako jakoukoli jinou operaci.</span><span class="sxs-lookup"><span data-stu-id="865ae-332">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="865ae-333">To nám umožňuje psát operace, které jako součást svého vstupu přijímají operace, které vytvářejí koncepty toku řízení vyššího řádu.</span><span class="sxs-lookup"><span data-stu-id="865ae-333">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="865ae-334">Můžeme si například představit, že se má "čtvercová" operace aplikovat dvakrát na stejný cílový qubit.</span><span class="sxs-lookup"><span data-stu-id="865ae-334">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="865ae-335">Vrácení operací z funkce</span><span class="sxs-lookup"><span data-stu-id="865ae-335">Returning operations from a function</span></span>

<span data-ttu-id="865ae-336">Zdůrazňujeme, že můžeme také vracet operace jako součást výstupů, takže můžeme izolovat některé druhy klasických podmíněných logiky jako klasických funkcí, které v podobě operace vrátí popis programu pro práci s poli.</span><span class="sxs-lookup"><span data-stu-id="865ae-336">We emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="865ae-337">Jednoduchým příkladem je zvážit příklad přenosu, ve kterém strana, která obdrží 16bitovou klasický zprávu, musí zprávu použít k dekódování jejich qubit do správného portu.</span><span class="sxs-lookup"><span data-stu-id="865ae-337">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="865ae-338">Můžeme to napsat s ohledem na funkci, která přebírá tyto dvě klasické bity a vrátí správnou operaci dekódování.</span><span class="sxs-lookup"><span data-stu-id="865ae-338">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="865ae-339">Tato nová funkce je ve skutečnosti funkcí, v takovém případě je volána se stejnými hodnotami `hereBit` a a vrátíme `thereBit` vždy stejnou operaci.</span><span class="sxs-lookup"><span data-stu-id="865ae-339">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="865ae-340">Proto lze dekodér bezpečně spustit uvnitř operací, aniž byste museli mít důvod na to, jak logika dekódování komunikuje s definicemi různých specializací operace.</span><span class="sxs-lookup"><span data-stu-id="865ae-340">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="865ae-341">To znamená, že jsme izolaci klasické logiky uvnitř funkce a zaručili kompilátor, že volání funkce může být přeobjednáno pomocí impunity, pokud je zachován vstup.</span><span class="sxs-lookup"><span data-stu-id="865ae-341">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="865ae-342">Částečná aplikace</span><span class="sxs-lookup"><span data-stu-id="865ae-342">Partial Application</span></span>

<span data-ttu-id="865ae-343">Díky funkcím, které vracejí operace, můžeme použít *částečnou aplikaci*, ve které můžeme zadat jednu nebo více částí vstupu do funkce nebo operace, aniž byste je skutečně volali.</span><span class="sxs-lookup"><span data-stu-id="865ae-343">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="865ae-344">Například `ApplyTwice` opakované volání výše uvedeného příkladu můžeme označit, že nechcete zadat hned, na které qubit by měla vstupní operace platit:</span><span class="sxs-lookup"><span data-stu-id="865ae-344">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="865ae-345">V tomto případě místní proměnná `twiceOp` obsahuje částečně použitou operaci `ApplyTwice(op, _)` , kde jsou části vstupu, které ještě nebyly určeny, označeny `_` .</span><span class="sxs-lookup"><span data-stu-id="865ae-345">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="865ae-346">Když ve skutečnosti voláme na `twiceOp` Další řádek, předáte jako vstup do částečně použité operace všechny zbývající části vstupu do původní operace.</span><span class="sxs-lookup"><span data-stu-id="865ae-346">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="865ae-347">Proto je výše uvedený fragment kódu prakticky stejný jako při `ApplyTwice(op, target)` přímém volání, Uložit pro, že jsme zavedli novou místní proměnnou, která nám umožní zpoždění volání při poskytování některých částí vstupu.</span><span class="sxs-lookup"><span data-stu-id="865ae-347">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="865ae-348">Vzhledem k tomu, že operace, která byla částečně použita, není ve skutečnosti volána, dokud není poskytnut celý vstup, můžeme částečně použít operace i v rámci funkcí.</span><span class="sxs-lookup"><span data-stu-id="865ae-348">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="865ae-349">V zásadě byla klasická logika v rámci `SquareOperation` může být mnohem více zapojena, ale je stále izolovaná od zbytku operace zárukami, které může kompilátor nabízet o funkcích.</span><span class="sxs-lookup"><span data-stu-id="865ae-349">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="865ae-350">Tento přístup se bude používat v rámci celé knihovny Q # pro vyjádření toku klasického řízení způsobem, který se dá snadno použít v rámci programu pro překročení úrovně.</span><span class="sxs-lookup"><span data-stu-id="865ae-350">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>


## <a name="recursion"></a><span data-ttu-id="865ae-351">Rekurze</span><span class="sxs-lookup"><span data-stu-id="865ae-351">Recursion</span></span>

<span data-ttu-id="865ae-352">Je možné, že volat v Q # můžou být přímo nebo nepřímo rekurzivní.</span><span class="sxs-lookup"><span data-stu-id="865ae-352">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="865ae-353">To znamená, že operace nebo funkce může volat sám sebe nebo může volat jinou metodu, kterou přímo nebo nepřímo volá operaci, kterou lze volat.</span><span class="sxs-lookup"><span data-stu-id="865ae-353">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="865ae-354">Existují dva důležité komentáře k použití rekurze, ale:</span><span class="sxs-lookup"><span data-stu-id="865ae-354">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="865ae-355">Použití rekurze v operacích může být v konfliktu s některými optimalizacemi.</span><span class="sxs-lookup"><span data-stu-id="865ae-355">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="865ae-356">To může mít zásadní vliv na dobu provádění algoritmu.</span><span class="sxs-lookup"><span data-stu-id="865ae-356">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="865ae-357">Při provádění na skutečném zařízení ve formátu paměti může být prostor zásobníku omezený a důkladná rekurze může vést k chybě za běhu.</span><span class="sxs-lookup"><span data-stu-id="865ae-357">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="865ae-358">Konkrétně kompilátor Q # a modul runtime neidentifikují a optimalizují koncovou rekurzi.</span><span class="sxs-lookup"><span data-stu-id="865ae-358">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="whats-next"></a><span data-ttu-id="865ae-359">A co dál?</span><span class="sxs-lookup"><span data-stu-id="865ae-359">What's Next?</span></span>
<span data-ttu-id="865ae-360">Přečtěte si o [proměnných](xref:microsoft.quantum.guide.variables) v Q #.</span><span class="sxs-lookup"><span data-stu-id="865ae-360">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>