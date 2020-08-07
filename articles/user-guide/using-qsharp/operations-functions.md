---
title: Operace a funkce vQ#
description: Definování a volání operací a funkcí, jakož i specializace řízených a sousedících operací.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
no-loc:
- Q#
- $$v
ms.openlocfilehash: 76437c83df894fa86409e680f961d97e267c6869
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867875"
---
# <a name="operations-and-functions-in-no-locq"></a><span data-ttu-id="a0c18-103">Operace a funkce vQ#</span><span class="sxs-lookup"><span data-stu-id="a0c18-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="a0c18-104">Definování nových operací</span><span class="sxs-lookup"><span data-stu-id="a0c18-104">Defining New Operations</span></span>

<span data-ttu-id="a0c18-105">Operace jsou základem Q# .</span><span class="sxs-lookup"><span data-stu-id="a0c18-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="a0c18-106">Po deklarování mohou být buď volány z klasických aplikací .NET, například pomocí simulátoru nebo jiných operací v rámci Q# .</span><span class="sxs-lookup"><span data-stu-id="a0c18-106">Once declared, they can either be called from classical .NET applications, for example, using a simulator or by other operations within Q#.</span></span>
<span data-ttu-id="a0c18-107">Každá operace definovaná v nástroji Q# může volat libovolný počet jiných operací, včetně integrovaných vnitřních operací definovaných jazykem.</span><span class="sxs-lookup"><span data-stu-id="a0c18-107">Each operation defined in Q# can call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="a0c18-108">Konkrétní způsob, jakým Q# tyto vnitřní operace definují, závisí na cílovém počítači.</span><span class="sxs-lookup"><span data-stu-id="a0c18-108">The particular way in which Q# defines these intrinsic operations depends on the target machine.</span></span>
<span data-ttu-id="a0c18-109">Při kompilaci je každá operace reprezentována jako typ třídy .NET, který lze poskytnout cílovým počítačům.</span><span class="sxs-lookup"><span data-stu-id="a0c18-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="a0c18-110">Každý Q# zdrojový soubor může definovat libovolný počet operací.</span><span class="sxs-lookup"><span data-stu-id="a0c18-110">Each Q# source file can define any number of operations.</span></span>
<span data-ttu-id="a0c18-111">Název operace musí být v rámci oboru názvů jedinečný a nemůže být v konfliktu s názvy typu nebo funkce.</span><span class="sxs-lookup"><span data-stu-id="a0c18-111">Operation names must be unique within a namespace and can not conflict with type or function names.</span></span>

<span data-ttu-id="a0c18-112">Deklarace operace se skládá z klíčového slova `operation` následovaný symbolem, který představuje název operace, typ řazené kolekce členů definující argumenty operace, dvojtečku `:` , anotaci typu, která popisuje typ výsledku operace, volitelně poznámku s charakteristikou operace, levou složenou závorku a pak tělo deklarace operace uzavřené v závorkách `{ }` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace, and then the body of the operation declaration, enclosed in braces `{ }`.</span></span>

<span data-ttu-id="a0c18-113">Každá operace provede vstup, vytvoří výstup a určí implementaci pro jednu nebo více specializací operace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="a0c18-114">Možné specializace a jejich definování a volání jsou podrobně popsány v různých částech tohoto článku.</span><span class="sxs-lookup"><span data-stu-id="a0c18-114">The possible specializations, and how to define and call them, are detailed in the different sections of this article.</span></span>
<span data-ttu-id="a0c18-115">Prozatím zvažte následující operaci, která definuje jenom výchozí specializaci těla a jako svůj vstup přebírá jeden qubit, a pak na tomto vstupu zavolá vestavěnou <xref:microsoft.quantum.intrinsic.x> operaci:</span><span class="sxs-lookup"><span data-stu-id="a0c18-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:microsoft.quantum.intrinsic.x> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="a0c18-116">Klíčové slovo `operation` zahájí definici operace následovaný názvem; zde, `BitFlip` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-116">The keyword `operation` begins the operation definition, followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="a0c18-117">Dále je typ vstupu definován ( `Qubit` ), spolu s názvem, `target` pro odkazování na vstup v rámci nové operace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-117">Next, the type of input is defined (`Qubit`), along with a name, `target`, for referring to the input within the new operation.</span></span>
<span data-ttu-id="a0c18-118">Nakonec `Unit` definuje, že výstup operace je prázdný.</span><span class="sxs-lookup"><span data-stu-id="a0c18-118">Lastly, `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="a0c18-119">`Unit`se používá podobně `void` v jazyce C# a dalších imperativních jazycích a je ekvivalentní s jazykem `unit` F # a dalšími funkčními jazyky.</span><span class="sxs-lookup"><span data-stu-id="a0c18-119">`Unit` is used similarly to `void` in C# and other imperative languages and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="a0c18-120">Operace mohou také vracet zajímavější typy než `Unit` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="a0c18-121">Například <xref:microsoft.quantum.intrinsic.m> operace vrátí výstup typu `Result` , který představuje vykonání měření.</span><span class="sxs-lookup"><span data-stu-id="a0c18-121">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span>  <span data-ttu-id="a0c18-122">Můžete ji předat z operace do jiné operace nebo ji použít s `let` klíčovým slovem k definování nové proměnné.</span><span class="sxs-lookup"><span data-stu-id="a0c18-122">You can pass it from an operation to another operation or use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="a0c18-123">Tento přístup umožňuje, aby představoval klasický výpočet, který komunikuje s provozními operacemi na nízké úrovni, jako je například v [hustém kódování](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span><span class="sxs-lookup"><span data-stu-id="a0c18-123">This approach allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span></span>

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
> <span data-ttu-id="a0c18-124">Každá operace v Q# používá přesně jeden vstup a vrací přesně jeden výstup.</span><span class="sxs-lookup"><span data-stu-id="a0c18-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="a0c18-125">Více vstupů a výstupů je znázorněno pomocí *řazených kolekcí členů*, které shromažďují více hodnot dohromady do jedné hodnoty.</span><span class="sxs-lookup"><span data-stu-id="a0c18-125">Multiple inputs and outputs are represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="a0c18-126">V tomto ohledu je jazyk řazené kolekce členů (Tuple Q# ).</span><span class="sxs-lookup"><span data-stu-id="a0c18-126">In this regard, Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="a0c18-127">Po tomto konceptu by měla být sada prázdných závorek `()` načtena jako "prázdná" řazená kolekce členů, která má typ `Unit` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-127">Following this concept, a set of empty parentheses, `()`, should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="a0c18-128">Řízené a sousedící operace</span><span class="sxs-lookup"><span data-stu-id="a0c18-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="a0c18-129">Pokud operace implementuje jednotnou transformaci, jako je případ mnoha operací v nástroji Q# , je možné definovat způsob, jakým operace funguje při *adjointed* nebo *řízení*.</span><span class="sxs-lookup"><span data-stu-id="a0c18-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="a0c18-130">*Sousedící* specializace operace určuje způsob, jakým operace "INVERT" operace funguje, zatímco *řízená* specializace určuje, jak operace funguje, když je její aplikace podmíněně ve stavu konkrétního registru.</span><span class="sxs-lookup"><span data-stu-id="a0c18-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="a0c18-131">Adjoints operací je zásadní pro mnoho aspektů výpočetních operací.</span><span class="sxs-lookup"><span data-stu-id="a0c18-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="a0c18-132">Příklad jedné takové situace popsané společně s užitečnou Q# programovací technikou najdete v tématu [conjugations](#conjugations) v tomto článku.</span><span class="sxs-lookup"><span data-stu-id="a0c18-132">For an example of one such situation discussed alongside a useful Q# programming technique, see [Conjugations](#conjugations) in this article.</span></span> 

<span data-ttu-id="a0c18-133">Řízená verze operace je nová operace, která efektivně aplikuje základní operaci pouze v případě, že všechny qubits ovládacího prvku jsou v zadaném stavu.</span><span class="sxs-lookup"><span data-stu-id="a0c18-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="a0c18-134">Pokud je qubits ovládacího prvku na pozici, pak je základní operace použita v souvislém umístění na příslušné straně.</span><span class="sxs-lookup"><span data-stu-id="a0c18-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="a0c18-135">Proto se pro generování entanglement často používají kontrolované operace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="a0c18-136">Přirozeně by mohla existovat *řízená sousední* specializace a určení řízené aplikace sousedícího prvku operace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="a0c18-137">Pokud se $U $ jedná o jednotnou transformaci implementovanou operací `U` , pak `Adjoint U` představuje jednotnou transformaci $U ^ \dagger $, což je komplexní sdružená transformace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="a0c18-138">Po sobě jdoucí použití operace a poté jejího souseda se stavem opustí stav beze změny, jak je znázorněno ve skutečnosti, že $UU ^ \dagger = U ^ \dagger U = \id $, matici identity.</span><span class="sxs-lookup"><span data-stu-id="a0c18-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="a0c18-139">Jednotná reprezentace kontrolované operace je trochu větší odlišit, ale další podrobnosti najdete na stránce s přehledem [výpočetních konceptů: více qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="a0c18-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="a0c18-140">Následující část popisuje, jak volat tyto různé specializace v Q# kódu a jak definovat operace pro jejich podporu.</span><span class="sxs-lookup"><span data-stu-id="a0c18-140">The following section describes how to call these various specializations in your Q# code, and how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="a0c18-141">Specializace operací volání</span><span class="sxs-lookup"><span data-stu-id="a0c18-141">Calling operation specializations</span></span>

<span data-ttu-id="a0c18-142">*Funktor* v Q# je objekt pro vytváření, který definuje novou operaci z jiné operace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-142">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="a0c18-143">Dvě standardní funktory v Q# jsou `Adjoint` a `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-143">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="a0c18-144">Funktory má přístup k implementaci základní operace při definování implementace nové operace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-144">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="a0c18-145">Proto může funktory provádět složitější funkce než tradiční funkce vyšší úrovně.</span><span class="sxs-lookup"><span data-stu-id="a0c18-145">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="a0c18-146">Funktory v Q# systému typů není reprezentace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-146">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="a0c18-147">V současné době není možné je navazovat na proměnnou nebo předat jako argumenty.</span><span class="sxs-lookup"><span data-stu-id="a0c18-147">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="a0c18-148">Použijte funktor, protože ho použijete k operaci, která vrací novou operaci.</span><span class="sxs-lookup"><span data-stu-id="a0c18-148">Use a functor by applying it to an operation, which returns a new operation.</span></span>
<span data-ttu-id="a0c18-149">Například použití `Adjoint` funktor pro `Y` operaci vrátí novou operaci `Adjoint Y` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-149">For example, applying the `Adjoint` functor to the `Y` operation returns the new operation `Adjoint Y`.</span></span> <span data-ttu-id="a0c18-150">Novou operaci můžete vyvolat jako jakoukoli jinou operaci.</span><span class="sxs-lookup"><span data-stu-id="a0c18-150">You can invoke the new operation like any other operation.</span></span>
<span data-ttu-id="a0c18-151">Aby operace podporovala aplikaci `Adjoint` nebo `Controlled` funktory, její návratový typ nutně musí být `Unit` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-151">For an operation to support the application of the `Adjoint` or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="a0c18-152">`Adjoint`funktor</span><span class="sxs-lookup"><span data-stu-id="a0c18-152">`Adjoint` functor</span></span>

<span data-ttu-id="a0c18-153">Proto `Adjoint Y(q1)` použije `Adjoint` funktor k `Y` operaci pro vygenerování nové operace a použije tuto novou operaci na `q1` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-153">Thus, `Adjoint Y(q1)` applies the `Adjoint` functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="a0c18-154">Nová operace má stejný podpis a typ jako základní operace `Y` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-154">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="a0c18-155">Konkrétně Nová operace také podporuje `Adjoint` a podporuje `Controlled` pouze v případě, že došlo k základní operaci.</span><span class="sxs-lookup"><span data-stu-id="a0c18-155">In particular, the new operation also supports `Adjoint`, and supports `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="a0c18-156">`Adjoint`Funktor je vlastní Inverted; to znamená, že je `Adjoint Adjoint Op` vždy stejný jako `Op` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-156">The `Adjoint` functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="a0c18-157">`Controlled`funktor</span><span class="sxs-lookup"><span data-stu-id="a0c18-157">`Controlled` functor</span></span>

<span data-ttu-id="a0c18-158">Obdobně `Controlled X(controls, target)` aplikuje `Controlled` funktor na `X` operaci pro vygenerování nové operace a použije tuto novou operaci na `controls` a `target` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-158">Similarly, `Controlled X(controls, target)` applies the `Controlled` functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="a0c18-159">V Q# rámci jsou řízené verze vždy přebírat pole qubits ovládacího prvku a ovládací prvek je vždy založen na všech kontrolních qubits ve stavu výpočty ( `PauliZ` ) `One` , $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="a0c18-159">In Q#, controlled versions always take an array of control qubits, and the controlling is always based on all of the control qubits being in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="a0c18-160">Řízení založené na dalších stavech se dosahuje tím, že se pro kontrolní qubits před kontrolovaným provozem aplikuje příslušná Jednotková operace a po kontrolované operaci se použijí inverzní funkce pro jednotnou operaci.</span><span class="sxs-lookup"><span data-stu-id="a0c18-160">Controlling based on other states is achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="a0c18-161">Například použití `X` operace na ovládací prvek qubit před a poté, co řízená operace způsobí, že operace bude řídit `Zero` stav ($ \ket {0} $) pro tento qubit; použití `H` operace před a po ovládacích prvcích ve `PauliX` `One` stavu, to znamená-1 eigenvalue z Pauli X, $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt $, a {2} ne na `PauliZ` `One` stav.</span><span class="sxs-lookup"><span data-stu-id="a0c18-161">For example, applying an `X` operation to a control qubit before and after a controlled operation causes the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after controls on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="a0c18-162">S ohledem na výraz operace můžete vytvořit nový výraz operace pomocí `Controlled` funktor.</span><span class="sxs-lookup"><span data-stu-id="a0c18-162">Given an operation expression, you can form a new operation expression by using the `Controlled` functor.</span></span>
<span data-ttu-id="a0c18-163">Signatura nové operace vychází z podpisu původní operace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-163">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="a0c18-164">Typ výsledku je stejný, ale vstupní typ je dvě n-tice s polem qubit, které obsahuje ovládací qubit (y) ovládacího prvku jako první prvek a argumenty původní operace jako druhý prvek.</span><span class="sxs-lookup"><span data-stu-id="a0c18-164">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="a0c18-165">Nová operace podporuje `Controlled` a bude podporovat `Adjoint` pouze v případě, že původní operace proběhla.</span><span class="sxs-lookup"><span data-stu-id="a0c18-165">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="a0c18-166">V případě, že původní operace trvala pouze jeden argument, přichází v úvahu [rovnocennost řazené kolekce členů](xref:microsoft.quantum.guide.types) do hry.</span><span class="sxs-lookup"><span data-stu-id="a0c18-166">If the original operation took only a single argument, then [singleton tuple equivalence](xref:microsoft.quantum.guide.types) comes into play here.</span></span>
<span data-ttu-id="a0c18-167">Například `Controlled X` je řízená verze `X` operace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-167">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="a0c18-168">`X`má typ `(Qubit => Unit is Adj + Ctl)` , takže je `Controlled X` typu `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; vzhledem k rovnosti v řazené kolekci členů, je to stejné jako `((Qubit[], Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-168">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="a0c18-169">Pokud základní operace trvala několik argumentů, nezapomeňte do závorek uzavřít odpovídající argumenty kontrolované verze operace v závorkách, aby je bylo možné převést na řazenou kolekci členů.</span><span class="sxs-lookup"><span data-stu-id="a0c18-169">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="a0c18-170">Například `Controlled Rz` je řízená verze `Rz` operace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-170">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="a0c18-171">`Rz`má typ `((Double, Qubit) => Unit is Adj + Ctl)` , takže `Controlled Rz` je typu `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-171">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="a0c18-172">Proto `Controlled Rz(controls, (0.1, target))` by bylo platné vyvolání `Controlled Rz` (Poznamenejte si závorky kolem `0.1, target` ).</span><span class="sxs-lookup"><span data-stu-id="a0c18-172">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="a0c18-173">Jako další příklad `CNOT(control, target)` lze implementovat jako `Controlled X([control], target)` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-173">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="a0c18-174">Pokud má cíl být řízen dvěma ovládacími qubits (CCNOT), použijte `Controlled X([control1, control2], target)` příkaz.</span><span class="sxs-lookup"><span data-stu-id="a0c18-174">If a target should be controlled by two control qubits (CCNOT), use a `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="a0c18-175">`Controlled`Funktory a dokončí `Adjoint` dojíždění, takže není rozdíl mezi použitím `Controlled Adjoint Op` nebo `Adjoint Controlled Op` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-175">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="a0c18-176">Definování řízených a sousedících implementací</span><span class="sxs-lookup"><span data-stu-id="a0c18-176">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="a0c18-177">V deklaraci první operace v předchozích příkladech operace `BitFlip` a `DecodeSuperdense` byly definovány s podpisy a v `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="a0c18-177">In the first operation declaration in the previous examples, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="a0c18-178">Jak `DecodeSuperdense` zahrnuje měření, nejedná se o jednotkovou operaci, a proto by nemohly nastavovat žádné specializace nesousedících a (vrátit související požadavek, který taková operace vrátí `Unit` ).</span><span class="sxs-lookup"><span data-stu-id="a0c18-178">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="a0c18-179">Jak ale `BitFlip` jednoduše provede jednotnou <xref:microsoft.quantum.intrinsic.x> operaci, můžete ji definovat s oběma specializacemi.</span><span class="sxs-lookup"><span data-stu-id="a0c18-179">However, as `BitFlip` simply performs the unitary <xref:microsoft.quantum.intrinsic.x> operation, you could have defined it with both specializations.</span></span>

<span data-ttu-id="a0c18-180">Tato část podrobně popisuje, jak zahrnout existenci specializace v Q# deklaracích operací, takže jim umožní volat ve spojení s `Adjoint` nebo `Controlled` funktory.</span><span class="sxs-lookup"><span data-stu-id="a0c18-180">This section details how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` or `Controlled` functors.</span></span>
<span data-ttu-id="a0c18-181">Další informace o některých situacích, ve kterých je buď platný, nebo není platný pro deklaraci určitých specializací, naleznete v tématu [okolnosti pro platné definování specializací](#circumstances-for-validly-defining-specializations) v tomto článku.</span><span class="sxs-lookup"><span data-stu-id="a0c18-181">For more information about some of the situations in which it is either valid or not valid to declare certain specializations, see [Circumstances for validly defining specializations](#circumstances-for-validly-defining-specializations) in this article.</span></span>

<span data-ttu-id="a0c18-182">Charakteristiky operace definují, jaké druhy funktory můžete použít pro deklarovanou operaci a jaký má vliv.</span><span class="sxs-lookup"><span data-stu-id="a0c18-182">Operation characteristics define what kinds of functors you can apply to the declared operation, and what effect they have.</span></span> <span data-ttu-id="a0c18-183">Existence těchto specializací se dá deklarovat jako součást signatury operace, konkrétně prostřednictvím poznámky s charakteristikou operace: buď `is Adj` , `is Ctl` nebo `is Adj + Ctl` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-183">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="a0c18-184">Vlastní implementace každé specializace může být *implicitně* nebo *explicitně* definovaná.</span><span class="sxs-lookup"><span data-stu-id="a0c18-184">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="a0c18-185">Implicitní určení implementací</span><span class="sxs-lookup"><span data-stu-id="a0c18-185">Implicitly specifying implementations</span></span>

<span data-ttu-id="a0c18-186">V tomto případě se tělo deklarace operace skládá výhradně z výchozí implementace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-186">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="a0c18-187">Příklad:</span><span class="sxs-lookup"><span data-stu-id="a0c18-187">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="a0c18-188">V tomto případě se odpovídající implementace pro každou z těchto implicitně deklarované specializace automaticky vygeneruje kompilátorem, aby se provedla, pokud se `Adjoint` `Controlled` používají nebo funktory.</span><span class="sxs-lookup"><span data-stu-id="a0c18-188">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="a0c18-189">Volání by tedy způsobilo, `Adjoint PrepareEntangledPair` že kompilátor implementuje sousední metodu `CNOT` a poté sousední `H` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-189">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="a0c18-190">Tyto jednotlivé operace jsou samostatně sousedící, takže výsledná `Adjoint PrepareEntangledPair` operace by se jednoduše použila k použití `CNOT(here, there)` a pak `H(here)` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-190">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="a0c18-191">Proto můžete použít tuto možnost k zapsání `DecodeSuperdense` v předchozím příkladu, a to tak, že pomocí sousedícího prvku `PrepareEntangledPair` vrátíte stav entangled zpět na pár unentangled qubits:</span><span class="sxs-lookup"><span data-stu-id="a0c18-191">Hence you can use this to write the `DecodeSuperdense` in the previous example more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="a0c18-192">Poznámka s charakteristikami operace v deklaraci je užitečná pro zajištění, že kompilátor automaticky generuje další specializace na základě výchozí implementace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-192">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="a0c18-193">Při navrhování operací pro použití s funktory je potřeba vzít v úvahu několik důležitých omezení.</span><span class="sxs-lookup"><span data-stu-id="a0c18-193">There are several important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="a0c18-194">Nejdůležitější specializace pro operaci, která používá výstupní hodnotu jakékoli jiné operace, *nelze* automaticky generovat kompilátorem, protože je nejednoznačná, jak změnit pořadí příkazů v takové operaci pro získání stejného efektu.</span><span class="sxs-lookup"><span data-stu-id="a0c18-194">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="a0c18-195">Proto je často vhodné explicitně zadat různé implementace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-195">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="a0c18-196">Explicitní určení implementací</span><span class="sxs-lookup"><span data-stu-id="a0c18-196">Explicitly specifying implementations</span></span>

<span data-ttu-id="a0c18-197">V případě, že kompilátor nemůže vygenerovat implementaci, můžete ji zadat explicitně.</span><span class="sxs-lookup"><span data-stu-id="a0c18-197">In the case where the compiler cannot generate the implementation, you can specify it explicitly.</span></span> <span data-ttu-id="a0c18-198">Tyto explicitní deklarace specializace můžou sestávat z vhodné *direktivy generace* nebo uživatelsky definované implementace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-198">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="a0c18-199">Následující seznam uvádí celou řadu možností s některými příklady explicitní specializace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-199">Following are the full range of possibilities, with some examples of explicit specialization.</span></span> 


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="a0c18-200">Explicitní deklarace specializace</span><span class="sxs-lookup"><span data-stu-id="a0c18-200">Explicit specialization declarations</span></span>

<span data-ttu-id="a0c18-201">Q#operace mohou obsahovat následující explicitní deklarace specializace:</span><span class="sxs-lookup"><span data-stu-id="a0c18-201">Q# operations can contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="a0c18-202">`body`Specializace určuje implementaci operace bez použití funktory.</span><span class="sxs-lookup"><span data-stu-id="a0c18-202">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="a0c18-203">`adjoint`Specializace určuje implementaci operace s `Adjoint` použitým funktor.</span><span class="sxs-lookup"><span data-stu-id="a0c18-203">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="a0c18-204">`controlled`Specializace určuje implementaci operace s `Controlled` použitým funktor.</span><span class="sxs-lookup"><span data-stu-id="a0c18-204">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="a0c18-205">`controlled adjoint`Specializace určuje implementaci operace s `Adjoint` `Controlled` použitým funktory a.</span><span class="sxs-lookup"><span data-stu-id="a0c18-205">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="a0c18-206">Tato specializace může mít také název `adjoint controlled` , protože dvě funktory dojíždění.</span><span class="sxs-lookup"><span data-stu-id="a0c18-206">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="a0c18-207">Specializace operace se skládá z tagu specializace (například `body` nebo `adjoint` ) následovaného jedním z těchto:</span><span class="sxs-lookup"><span data-stu-id="a0c18-207">An operation specialization consists of the specialization tag (for example, `body` or `adjoint`) followed by one of:</span></span>

- <span data-ttu-id="a0c18-208">Explicitní deklarace, jak je popsáno v následujícím tématu.</span><span class="sxs-lookup"><span data-stu-id="a0c18-208">An explicit declaration as described in the following.</span></span>
- <span data-ttu-id="a0c18-209">*Direktiva* , která instruuje kompilátor, *jak* vygenerovat specializaci, jedna z těchto:</span><span class="sxs-lookup"><span data-stu-id="a0c18-209">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="a0c18-210">`intrinsic`, což znamená, že cílový počítač poskytuje specializaci.</span><span class="sxs-lookup"><span data-stu-id="a0c18-210">`intrinsic`, which indicates that the target machine provides the specialization.</span></span>
  - <span data-ttu-id="a0c18-211">`distribute`, používá se v `controlled` rámci `controlled adjoint` specializace a.</span><span class="sxs-lookup"><span data-stu-id="a0c18-211">`distribute`, used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="a0c18-212">Při použití s se `controlled` označuje, že kompilátor má vypočítat specializaci použitím `Controlled` pro všechny operace v `body` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-212">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="a0c18-213">Při použití s se `controlled adjoint` označuje, že kompilátor má vypočítat specializaci použitím `Controlled` pro všechny operace v `adjoint` specializaci.</span><span class="sxs-lookup"><span data-stu-id="a0c18-213">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="a0c18-214">`invert`, což znamená, že by kompilátor měl vypočítat `adjoint` specializaci tím, že se obrátí `body` , například převrácení pořadí operací a použití sousedícího na každý z nich.</span><span class="sxs-lookup"><span data-stu-id="a0c18-214">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, for example, reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="a0c18-215">Při použití s se `adjoint controlled` označuje, že kompilátor má vypočítat specializaci vrácením `controlled` specializace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-215">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="a0c18-216">`self`, abyste označili, že specializace sousedícít je stejná jako `body` specializace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-216">`self`, to indicate that the adjoint specialization is the same as the `body` specialization.</span></span>
    <span data-ttu-id="a0c18-217">Použití `self` je platné pro `adjoint` `adjoint controlled` specializace a.</span><span class="sxs-lookup"><span data-stu-id="a0c18-217">Using `self` is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="a0c18-218">Pro `adjoint controlled` `self` znamená, že `adjoint controlled` specializace je stejná jako `controlled` specializace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-218">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="a0c18-219">`auto`, abyste označili, že má kompilátor vybrat vhodnou direktivu, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="a0c18-219">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="a0c18-220">`auto`Pro specializaci nelze použít `body` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-220">You cannot use`auto` for the `body` specialization.</span></span>

<span data-ttu-id="a0c18-221">Direktivy a `auto` všechny vyžadují uzavírací středník `;` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-221">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="a0c18-222">`auto`Direktiva se přeloží na následující generovanou direktivu, pokud `body` je zadána explicitní deklarace:</span><span class="sxs-lookup"><span data-stu-id="a0c18-222">The `auto` directive resolves to the following generated directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="a0c18-223">`adjoint`Specializace generuje podle direktivy `invert` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-223">The `adjoint` specialization generates according to the directive `invert`.</span></span>
- <span data-ttu-id="a0c18-224">`controlled`Specializace generuje podle direktivy `distribute` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-224">The `controlled` specialization generates according to the directive `distribute`.</span></span>
- <span data-ttu-id="a0c18-225">`adjoint controlled`Specializace generuje podle direktivy `invert` , pokud je zadána explicitní deklarace `controlled` , ale ne jedna pro `adjoint` a `distribute` jinak.</span><span class="sxs-lookup"><span data-stu-id="a0c18-225">The `adjoint controlled` specialization  generates according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="a0c18-226">Pokud je operace samostatně sousedící, explicitně určete buď sousední, nebo řízená sousední specializace pomocí direktivy generace, `self` aby kompilátor mohl používat tyto informace pro účely optimalizace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-226">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="a0c18-227">Deklarace specializace obsahující uživatelsky definovanou implementaci se skládá z argumentů řazené kolekce členů následovaný blokem příkazu s Q# kódem, který implementuje specializaci.</span><span class="sxs-lookup"><span data-stu-id="a0c18-227">A specialization declaration containing a user-defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="a0c18-228">V seznamu argumentů `...` se používá k reprezentaci argumentů deklarovaných pro operaci jako celku.</span><span class="sxs-lookup"><span data-stu-id="a0c18-228">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="a0c18-229">Pro `body` a `adjoint` by měl seznam argumentů vždy být `(...)` ; pro `controlled` a by `adjoint controlled` měl být seznam argumentů symbol reprezentující pole qubits ovládacího prvku následovaný znakem `...` uzavřeným v závorkách, například `(controls,...)` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-229">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="a0c18-230">Příklady</span><span class="sxs-lookup"><span data-stu-id="a0c18-230">Examples</span></span>

<span data-ttu-id="a0c18-231">Deklarace operace může být jednoduchá, jak je uvedeno níže, což definuje primitivní operaci Pauli X:</span><span class="sxs-lookup"><span data-stu-id="a0c18-231">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="a0c18-232">Všimněte si, že sousední funkce operace Pauli X je definována s direktivou, `self` protože podle definice `X` je její vlastní inverzní.</span><span class="sxs-lookup"><span data-stu-id="a0c18-232">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="a0c18-233">V předchozím `PrepareEntangledPair` příkladu je kód ekvivalentní následujícímu kódu, který obsahuje explicitní deklarace specializace:</span><span class="sxs-lookup"><span data-stu-id="a0c18-233">In the earlier `PrepareEntangledPair` example, the code is equivalent to the following code containing explicit specialization declarations:</span></span> 

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
<span data-ttu-id="a0c18-234">Klíčové slovo `auto` označuje, že by měl kompilátor určit, jak se má vygenerovat implementace specializace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-234">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="a0c18-235">Uživatelsky definovaná implementace specializace</span><span class="sxs-lookup"><span data-stu-id="a0c18-235">User-defined specialization implementation</span></span>

<span data-ttu-id="a0c18-236">Pokud kompilátor nemůže vygenerovat implementaci pro určitou specializaci automaticky, nebo pokud je možné zadat účinnější implementaci, můžete implementovat implementaci ručně.</span><span class="sxs-lookup"><span data-stu-id="a0c18-236">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then you can manually define the implementation.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user-defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
<span data-ttu-id="a0c18-237">V předchozím příkladu označuje, `adjoint invert;` že specializace sousední, má být vygenerována invertující implementaci těla a `controlled adjoint invert;` označuje, že řízená sousední specializace s je vygenerována obrácením dané implementace řízené specializace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-237">In the previous example, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="a0c18-238">Pokud je nutné explicitně deklarovat jednu nebo více specializací, než je výchozí tělo, musí být implementace pro výchozí tělo zabalena do vhodné deklarace specializace:</span><span class="sxs-lookup"><span data-stu-id="a0c18-238">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

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

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="a0c18-239">Okolnosti pro platné definování specializací</span><span class="sxs-lookup"><span data-stu-id="a0c18-239">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="a0c18-240">Deklarace operací s přiléhajícím/řízeným</span><span class="sxs-lookup"><span data-stu-id="a0c18-240">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="a0c18-241">Je možné zadat operaci bez sousedících nebo řízených verzí.</span><span class="sxs-lookup"><span data-stu-id="a0c18-241">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="a0c18-242">Například operace měření nemají ani proto, že nejsou inverzi nebo ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="a0c18-242">For instance, measurement operations have neither because they are not invertible or controllable.</span></span>

<span data-ttu-id="a0c18-243">Operace podporuje rozhraní `Adjoint` a `Controlled` funktory, pokud jeho deklarace obsahuje implicitní nebo explicitní deklaraci příslušných specializací.</span><span class="sxs-lookup"><span data-stu-id="a0c18-243">An operation supports the `Adjoint` and `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="a0c18-244">Explicitně deklarovaná sousední a řízená specializace implikuje existenci sousední specializace/řízené specializace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-244">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="a0c18-245">Pro operaci, jejíž tělo obsahuje smyčky opakování až po úspěšné, nastavte příkazy, měření, návratové příkazy nebo volání jiných operací, které nepodporují `Adjoint` funktor, automatické generování sousední specializace přiléhající podle `invert` `auto` direktivy or není možné.</span><span class="sxs-lookup"><span data-stu-id="a0c18-245">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="a0c18-246">Pro operaci, jejíž tělo obsahuje volání do jiných operací, které nepodporují `Controlled` funktor, není možné automaticky generovat řízená specializaci podle `distribute` `auto` direktivy or.</span><span class="sxs-lookup"><span data-stu-id="a0c18-246">For an operation whose body contains calls to other operations that do not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="a0c18-247">Řízený sousedící</span><span class="sxs-lookup"><span data-stu-id="a0c18-247">Controlled Adjoint</span></span>

<span data-ttu-id="a0c18-248">Řízená sousední verze operace určuje, jak implementovat verzi sousedícího prvku se správou počtu procesorů.</span><span class="sxs-lookup"><span data-stu-id="a0c18-248">The controlled adjoint version of an operation specifies how to implement a quantum-controlled version of the adjoint of the operation.</span></span>
<span data-ttu-id="a0c18-249">Je právní určení operace bez řízené sousední verze; například operace měření nemají řízenou sousední verzi, protože nejsou ani ovladatelné ani inverzi.</span><span class="sxs-lookup"><span data-stu-id="a0c18-249">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="a0c18-250">Řízená sousední specializace pro operaci musí existovat, pokud je a jenom v případě, že existují sousední i řízená specializace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-250">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="a0c18-251">V takovém případě je odvozená existence řízené specializace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-251">In that case, the existence of the controlled adjoint specialization is inferred.</span></span> <span data-ttu-id="a0c18-252">Pokud není explicitně definována žádná implementace, zkompiluje vygeneruje příslušnou specializaci.</span><span class="sxs-lookup"><span data-stu-id="a0c18-252">If no implementation is explicitly defined, the compile generates an appropriate specialization.</span></span>

<span data-ttu-id="a0c18-253">Pro operaci, jejíž tělo obsahuje volání na jiné operace, které nemají řízenou nekontrolovanou verzi, automatické generování sousední specializace přiléhající za `invert` `distribute` direktivou, nebo není `auto` možné.</span><span class="sxs-lookup"><span data-stu-id="a0c18-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute`, or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="a0c18-254">Kompatibilita typů</span><span class="sxs-lookup"><span data-stu-id="a0c18-254">Type Compatibility</span></span>

<span data-ttu-id="a0c18-255">Použijte operaci s dalšími funktory podporovanými kdekoli, kde použijete operaci s méně funktory, ale stejnou signaturou.</span><span class="sxs-lookup"><span data-stu-id="a0c18-255">Use an operation with additional functors supported anywhere you use an operation with fewer functors but the same signature.</span></span> <span data-ttu-id="a0c18-256">Například použijte operaci typu kdekoli, kde používáte `(Qubit => Unit is Adj)` operaci typu `(Qubit => Unit)` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-256">For instance, use an operation of type `(Qubit => Unit is Adj)` anywhere you use an operation of type `(Qubit => Unit)`.</span></span>

<span data-ttu-id="a0c18-257">Q#je *kovariantní* s ohledem na možné návratové typy: volat, které vrací typ, `'A` je kompatibilní s typem volat se stejným vstupním typem a typem výsledku, který je kompatibilní s `'A` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that is compatible with `'A` .</span></span>

<span data-ttu-id="a0c18-258">Q#je *kontravariantní* s ohledem na typy vstupu: dá se volat, který přebírá typ `'A` jako vstup, je kompatibilní s volat se stejným typem výsledku a vstupním typem, který je kompatibilní s `'A` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="a0c18-259">To znamená, že s ohledem na následující definice</span><span class="sxs-lookup"><span data-stu-id="a0c18-259">That is, given the following definitions,</span></span>

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

<span data-ttu-id="a0c18-260">Můžeš</span><span class="sxs-lookup"><span data-stu-id="a0c18-260">you can</span></span>

- <span data-ttu-id="a0c18-261">Vyvolejte funkci `ConjugateInvertWith` s `inner` argumentem buď `Invert` nebo `ApplyUnitary` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-261">Invoke the function `ConjugateInvertWith` with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="a0c18-262">Vyvolejte funkci `ConjugateUnitaryWith` s `inner` argumentem `ApplyUnitary` , ale ne `Invert` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-262">Invoke the function `ConjugateUnitaryWith` with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="a0c18-263">Vrátí hodnotu typu `(Qubit[] => Unit is Adj + Ctl)` z `ConjugateInvertWith` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-263">Return a value of type `(Qubit[] => Unit is Adj + Ctl)` from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0c18-264">Q#0,3 představil v chování uživatelsky definovaných typů značný rozdíl.</span><span class="sxs-lookup"><span data-stu-id="a0c18-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="a0c18-265">Uživatelsky definované typy jsou považovány za zabalenou verzi základního typu, nikoli jako podtyp.</span><span class="sxs-lookup"><span data-stu-id="a0c18-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="a0c18-266">To znamená, že hodnota uživatelsky definovaného typu není použitelná, pokud očekáváte hodnotu základního typu.</span><span class="sxs-lookup"><span data-stu-id="a0c18-266">This means that a value of a user-defined type is not usable where you expect a value of the underlying type is.</span></span>


### <a name="conjugations"></a><span data-ttu-id="a0c18-267">Conjugations</span><span class="sxs-lookup"><span data-stu-id="a0c18-267">Conjugations</span></span>

<span data-ttu-id="a0c18-268">Na rozdíl od klasických bitů, uvolňování paměti je trochu více zapojeno, protože nevidomé resetující qubits může mít nežádoucí důsledky zbývajícího výpočtu, pokud qubits stále entangled.</span><span class="sxs-lookup"><span data-stu-id="a0c18-268">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="a0c18-269">Tyto účinky je možné vyhnout tím, že před uvolněním paměti vykonává správné "rušení" prováděných výpočtů.</span><span class="sxs-lookup"><span data-stu-id="a0c18-269">These effects can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="a0c18-270">Běžným vzorem pro výpočetní výkon je následující:</span><span class="sxs-lookup"><span data-stu-id="a0c18-270">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="a0c18-271">Počínaje verzí 0,9 Q# podporuje příkaz conjugation, který implementuje předchozí transformaci.</span><span class="sxs-lookup"><span data-stu-id="a0c18-271">Starting with our 0.9 release, Q# supports a conjugation statement that implements the preceding transformation.</span></span> <span data-ttu-id="a0c18-272">Pomocí tohoto příkazu `ApplyWith` může být operace implementována následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="a0c18-272">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="a0c18-273">Takový příkaz conjugation je mnohem užitečnější, pokud vnější a vnitřní transformace nejsou okamžitě k dispozici jako operace, ale místo toho jsou vhodnější pro popis pomocí bloku skládajícího se z několika příkazů.</span><span class="sxs-lookup"><span data-stu-id="a0c18-273">Such a conjugation statement becomes far more useful if the outer and inner transformations are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="a0c18-274">Inverzní transformace pro příkazy definované v rámci bloku je automaticky generována kompilátorem a spuštěna po dokončení bloku Apply.</span><span class="sxs-lookup"><span data-stu-id="a0c18-274">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and run after the apply-block completes.</span></span>
<span data-ttu-id="a0c18-275">Vzhledem k tomu, že jakékoli proměnlivé proměnné použité jako součást bloku nelze znovu svázat v bloku Apply, je vygenerovaná transformace zaručena jako sousední v výpočtu v bloku.</span><span class="sxs-lookup"><span data-stu-id="a0c18-275">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 


## <a name="defining-new-functions"></a><span data-ttu-id="a0c18-276">Definování nových funkcí</span><span class="sxs-lookup"><span data-stu-id="a0c18-276">Defining New Functions</span></span>

<span data-ttu-id="a0c18-277">Funkce jsou čistě deterministické, klasické rutiny v Q# , které se liší od operací v tom, že nemají dovoleno mít žádné účinky přesahující výpočet výstupní hodnoty.</span><span class="sxs-lookup"><span data-stu-id="a0c18-277">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="a0c18-278">Konkrétně funkce nemohou volat operace; působit na, přidělit nebo vypůjčit qubits; Ukázka náhodných čísel; nebo jinak závisí na stavu nad rámec vstupní hodnoty s funkcí.</span><span class="sxs-lookup"><span data-stu-id="a0c18-278">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="a0c18-279">V důsledku toho Q# jsou funkce *čisté*, v tom, že vždycky mapují stejné vstupní hodnoty na stejné výstupní hodnoty.</span><span class="sxs-lookup"><span data-stu-id="a0c18-279">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="a0c18-280">Toto chování umožňuje Q# kompilátoru bezpečně změnit pořadí, jak a kdy volat funkce při generování specializací operace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-280">This behavior allows the Q# compiler to safely reorder how and when to call functions when generating operation specializations.</span></span>

<span data-ttu-id="a0c18-281">Každý Q# zdrojový soubor může definovat libovolný počet funkcí.</span><span class="sxs-lookup"><span data-stu-id="a0c18-281">Each Q# source file can define any number of functions.</span></span>
<span data-ttu-id="a0c18-282">Názvy funkcí musí být jedinečné v rámci oboru názvů a nemohou být v konfliktu s názvy operací nebo typů.</span><span class="sxs-lookup"><span data-stu-id="a0c18-282">Function names must be unique within a namespace and cannot conflict with operation or type names.</span></span>

<span data-ttu-id="a0c18-283">Definování funkce funguje podobně jako při definování operace s tím rozdílem, že pro funkci nelze definovat žádné sousedící a řízené specializace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-283">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="a0c18-284">Například:</span><span class="sxs-lookup"><span data-stu-id="a0c18-284">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="a0c18-285">– nebo –</span><span class="sxs-lookup"><span data-stu-id="a0c18-285">or</span></span> 

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

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="a0c18-286">Klasická logika v Functions = = dobrá</span><span class="sxs-lookup"><span data-stu-id="a0c18-286">Classical logic in functions == good</span></span>

<span data-ttu-id="a0c18-287">Kdykoli je to možné, je vhodné napsat klasický Logic z pojmu Functions namísto operací, aby je mohl snadněji použít.</span><span class="sxs-lookup"><span data-stu-id="a0c18-287">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations so that operations can more readily use it.</span></span> <span data-ttu-id="a0c18-288">Například pokud jste napsali předchozí `Square` deklaraci jako *operaci*, kompilátor by nedokázal zaručit, že volání stejného vstupu by konzistentně vytvořilo stejné výstupy.</span><span class="sxs-lookup"><span data-stu-id="a0c18-288">For example, if you had written the earlier `Square` declaration as an *operation*, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="a0c18-289">Pro podtržení rozdílu mezi funkcemi a operacemi zvažte problém klasického vzorkování náhodného čísla v rámci Q# operace:</span><span class="sxs-lookup"><span data-stu-id="a0c18-289">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="a0c18-290">Pokaždé, když `U` se zavolá, má jinou akci `target` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-290">Each time that `U` is called, it has a different action on `target`.</span></span>
<span data-ttu-id="a0c18-291">Konkrétně kompilátor nemůže zaručit, že pokud přidáte `adjoint auto` deklaraci specializace do `U` , `U(target); Adjoint U(target);` funguje jako identita (tj. jako No-OP).</span><span class="sxs-lookup"><span data-stu-id="a0c18-291">In particular, the compiler cannot guarantee that if you add an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="a0c18-292">To je v rozporu s definicí sousedícího prvku definovaného v [vektorech a maticích](xref:microsoft.quantum.concepts.vectors), což umožňuje kompilátoru automaticky generovat sousední specializaci objektu v operaci, při které volání operace <xref:microsoft.quantum.math.randomreal> způsobí přerušení záruk poskytnutých kompilátorem <xref:microsoft.quantum.math.randomreal> . Jedná se o operaci, pro kterou neexistuje žádná sousední nebo řízená verze.</span><span class="sxs-lookup"><span data-stu-id="a0c18-292">This violates the definition of the adjoint defined in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing the compiler to auto-generate an adjoint specialization in an operation where you call the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="a0c18-293">Na druhé straně, povolení volání funkcí, jako `Square` je bezpečná, a zaručuje kompilátor, že musí pouze zachovávat vstup pro `Square` zajištění stabilního výstupu.</span><span class="sxs-lookup"><span data-stu-id="a0c18-293">On the other hand, allowing function calls such as `Square` is safe, and assures the compiler that it only needs to preserve the input to `Square` to keep its output stable.</span></span>
<span data-ttu-id="a0c18-294">Proto izolování co nejvíc klasických logických funkcí do funkcí umožňuje snadno znovu použít tuto logiku v jiných funkcích a operacích.</span><span class="sxs-lookup"><span data-stu-id="a0c18-294">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="a0c18-295">Obecné (typ – parametrizované) – volatelné</span><span class="sxs-lookup"><span data-stu-id="a0c18-295">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="a0c18-296">Mnoho funkcí a operací, které můžete chtít definovat, se ve skutečnosti nespoléhá na typy jejich vstupů, ale místo toho pouze implicitně používají jejich typy prostřednictvím jiné funkce nebo operace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-296">Many functions and operations that you might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="a0c18-297">Představte si třeba koncept *mapy* společný pro mnoho funkčních jazyků. po předané funkci $f (x) $ a kolekci hodnot $ \{ x_1, x_2, \dots, x_n \} $, map vrátí novou kolekci $ \{ f (x_1), f (x_2), \dots, f (x_n) \} $.</span><span class="sxs-lookup"><span data-stu-id="a0c18-297">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="a0c18-298">Chcete-li implementovat tento postup v, využijte Q# výhod fakt, že funkce jsou první třídy.</span><span class="sxs-lookup"><span data-stu-id="a0c18-298">To implement this in Q#, take advantage of the fact that functions are first class.</span></span>
<span data-ttu-id="a0c18-299">Tady je rychlý příklad, který `Map` se používá `T` jako zástupný symbol při zjištění, jaké typy potřebujete.</span><span class="sxs-lookup"><span data-stu-id="a0c18-299">Here is a quick example of `Map`, using `T` as a placeholder while you figure out what types you need.</span></span>

```qsharp
function Map(fn : (T -> T), values : T[]) : T[] {
    mutable mappedValues = new T[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="a0c18-300">Všimněte si, že tato funkce vypadá velmi stejně bez ohledu na to, jaké skutečné typy nahradíte.</span><span class="sxs-lookup"><span data-stu-id="a0c18-300">Note that this function looks very much the same no matter what actual types you substitute in.</span></span>
<span data-ttu-id="a0c18-301">Mapa z celých čísel na Paul, například vypadá podobně jako mapa z čísel s plovoucí desetinnou čárkou na řetězce:</span><span class="sxs-lookup"><span data-stu-id="a0c18-301">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

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

<span data-ttu-id="a0c18-302">V zásadě můžete napsat verzi `Map` pro každou dvojici typů, ke kterým dojde, ale to přináší několik problémů.</span><span class="sxs-lookup"><span data-stu-id="a0c18-302">In principle, you could write a version of `Map` for every pair of types that you encounter, but this introduces several difficulties.</span></span>
<span data-ttu-id="a0c18-303">Pokud například v nástroji narazíte na chybu `Map` , je nutné zajistit, aby se oprava používala jednotně napříč všemi verzemi nástroje `Map` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-303">For instance, if you find a bug in `Map`, then you must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="a0c18-304">Kromě toho, pokud vytváříte nové řazené kolekce členů nebo UDT, musíte nyní také vytvořit nový, aby bylo možné `Map` Přejít k novému typu.</span><span class="sxs-lookup"><span data-stu-id="a0c18-304">Moreover, if you construct a new tuple or UDT, then you must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="a0c18-305">I když je to pro malý počet takových funkcí rušivý, když shromáždíte více a více funkcí stejného formuláře jako `Map` , náklady na zavedení nových typů se v poměrně krátkém pořadí změní na nepřiměřeně velké.</span><span class="sxs-lookup"><span data-stu-id="a0c18-305">While this is tractable for a small number of such functions, as you collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="a0c18-306">Mnohé z těchto potíží však jsou výsledkem faktu, že jste kompilátor neudělili informace, které potřebuje k tomu, abyste rozpoznali, jak různé verze nástroje `Map` souvisejí.</span><span class="sxs-lookup"><span data-stu-id="a0c18-306">However, much of this difficulty results from the fact that you have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="a0c18-307">Efektivně budete chtít, aby kompilátor považoval `Map` jako nějaký druh matematické funkce od Q# *typů* do Q# funkce.</span><span class="sxs-lookup"><span data-stu-id="a0c18-307">Effectively, you want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="a0c18-308">Q#formalizes tento pojem tím, že povolíte funkcím a operacím *parametry typu*a také jejich běžné parametry řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="a0c18-308">Q# formalizes this notion by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="a0c18-309">V předchozích příkladech si přejete si představit `Map` jako parametry typu `Int, Pauli` v prvním a `Double, String` druhém případě.</span><span class="sxs-lookup"><span data-stu-id="a0c18-309">In the previous examples, you wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="a0c18-310">Ve většině případů použijte tyto parametry typu, jako by se jednalo o běžné typy.</span><span class="sxs-lookup"><span data-stu-id="a0c18-310">For the most part, use these type parameters as though they were ordinary types.</span></span> <span data-ttu-id="a0c18-311">Použijte hodnoty parametrů typu pro vytvoření polí a řazených kolekcí členů, volání funkcí a operací a přiřazení k běžným nebo proměnlivým proměnným.</span><span class="sxs-lookup"><span data-stu-id="a0c18-311">Use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="a0c18-312">Nejextrémním případem nepřímé závislosti je to, že qubits, kde Q# program nemůže přímo spoléhat na strukturu `Qubit` typu, ale **musí** předat takové typy jiným operacím a funkcím.</span><span class="sxs-lookup"><span data-stu-id="a0c18-312">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="a0c18-313">Návrat k předchozímu příkladu, vidíte, že `Map` musí mít parametry typu, jeden pro reprezentaci vstupu a druhý, který `fn` představuje výstup z `fn` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-313">Returning to the earlier example, then, you see that `Map` needs to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="a0c18-314">V Q# je tento zápis napsán přidáním lomených závorek (to znamená `<>` Not brakets $ \braket {} $!) za názvem funkce nebo operace v deklaraci a výpisem každého parametru typu.</span><span class="sxs-lookup"><span data-stu-id="a0c18-314">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="a0c18-315">Název každého parametru typu musí začínat značkou `'` , která značí, že se jedná o parametr typu a ne běžný typ (označovaný také jako *konkrétní* typ).</span><span class="sxs-lookup"><span data-stu-id="a0c18-315">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="a0c18-316">Proto `Map` je zapsána:</span><span class="sxs-lookup"><span data-stu-id="a0c18-316">Thus, `Map`, is written:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="a0c18-317">Všimněte si, že definice `Map<'Input, 'Output>` vypadá velmi podobně jako verze previoius.</span><span class="sxs-lookup"><span data-stu-id="a0c18-317">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the previoius versions.</span></span>
<span data-ttu-id="a0c18-318">Jediným rozdílem je, že jste explicitně informovali o kompilátoru, který `Map` přímo nezávisí na tom `'Input` , co a `'Output` jsou, ale funguje pro všechny dva typy pomocí nepřímo prostřednictvím `fn` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-318">The only difference is that you have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="a0c18-319">Po definování `Map<'Input, 'Output>` tímto způsobem ho můžete zavolat, jako by to byla běžná funkce:</span><span class="sxs-lookup"><span data-stu-id="a0c18-319">Once you have defined `Map<'Input, 'Output>` in this way, you can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="a0c18-320">Zápis obecných funkcí a operací je jeden místo, kde "řazená kolekce členů" v řazené kolekci členů "je velmi užitečným způsobem, jak se zabývat Q# funkcemi a operacemi.</span><span class="sxs-lookup"><span data-stu-id="a0c18-320">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="a0c18-321">Vzhledem k tomu, že každá funkce používá přesně jeden vstup a vrátí přesně jeden výstup, vstup typu `'T -> 'U` odpovídá *libovolné* Q# funkci.</span><span class="sxs-lookup"><span data-stu-id="a0c18-321">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="a0c18-322">Podobně můžete předat jakoukoli operaci do vstupu typu `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-322">Similarly, you can pass any operation to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="a0c18-323">V druhém příkladu zvažte, jak napsat funkci, která vrací kompozici dvou dalších funkcí:</span><span class="sxs-lookup"><span data-stu-id="a0c18-323">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="a0c18-324">Tady je nutné přesně určit, co `A` , `B` a `C` jsou, a proto silně omezit nástroj naší nové `Compose` funkce.</span><span class="sxs-lookup"><span data-stu-id="a0c18-324">Here, you must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="a0c18-325">Po všech případech `Compose` závisí pouze na `A` , a `B` a `C` *pomocí* `innerFn` a `outerFn` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-325">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="a0c18-326">Alternativně můžete přidat parametry typu k tomu, aby `Compose` označovali, že funguje pro *jakékoli* `A` , `B` , a `C` , pokud tyto parametry odpovídají očekávaným parametrům `innerFn` a `outerFn` :</span><span class="sxs-lookup"><span data-stu-id="a0c18-326">As an alternative, then, you can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="a0c18-327">Q#Standardní knihovny poskytují rozsah těchto operací s parametrizovanými typy a funkce, které usnadňují vyjádření toku řízení vyšším řádu.</span><span class="sxs-lookup"><span data-stu-id="a0c18-327">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="a0c18-328">Tyto postupy jsou podrobněji popsány v [ Q# příručce ke standardní knihovně](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="a0c18-328">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="a0c18-329">Se bude volat jako hodnoty první třídy.</span><span class="sxs-lookup"><span data-stu-id="a0c18-329">Callables as First-Class Values</span></span>

<span data-ttu-id="a0c18-330">Jedním z kritických postupů pro rozhodnutí o toku řízení a klasické logice pomocí funkcí místo operací je použití těchto operací v nástroji jako Q# *první třídy*.</span><span class="sxs-lookup"><span data-stu-id="a0c18-330">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="a0c18-331">To znamená, že jsou všechny hodnoty v jazyce v pravém.</span><span class="sxs-lookup"><span data-stu-id="a0c18-331">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="a0c18-332">Například následující příklad je naprosto platný Q# kód, pokud je málo nepřímý:</span><span class="sxs-lookup"><span data-stu-id="a0c18-332">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="a0c18-333">Hodnota proměnné `ourH` v předchozím fragmentu kódu je pak operace <xref:microsoft.quantum.intrinsic.h> , například, kterou můžete zavolat jako jakoukoli jinou operaci.</span><span class="sxs-lookup"><span data-stu-id="a0c18-333">The value of the variable `ourH` in the previous snippet is then the operation <xref:microsoft.quantum.intrinsic.h>, such that you can call that value like any other operation.</span></span>
<span data-ttu-id="a0c18-334">Díky této funkci můžete zapisovat operace, které jako součást svého vstupu přijímají operace, a vytvořit tak vyšší koncepty toku řízení.</span><span class="sxs-lookup"><span data-stu-id="a0c18-334">With this ability, you can write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="a0c18-335">Například můžete si představit, že se má "čtvercová" operace aplikovat dvakrát na stejný cílový qubit.</span><span class="sxs-lookup"><span data-stu-id="a0c18-335">For instance, you could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="a0c18-336">Vrácení operací z funkce</span><span class="sxs-lookup"><span data-stu-id="a0c18-336">Returning operations from a function</span></span>

<span data-ttu-id="a0c18-337">Je důležité zdůraznit, že můžete také vracet operace jako součást výstupů, takže můžete izolovat některé druhy klasických podmíněných logických funkcí jako klasických funkcí, které v podobě operace vrátí popis programového množství.</span><span class="sxs-lookup"><span data-stu-id="a0c18-337">It's important to emphasize that you can also return operations as a part of outputs, such that you can isolate some kinds of classical conditional logic as a classical function, which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="a0c18-338">Jednoduchým příkladem je zvážit příklad přenosu, ve kterém strana, která obdrží 16bitovou klasický zprávu, musí zprávu použít k dekódování jejich qubit do správného portu.</span><span class="sxs-lookup"><span data-stu-id="a0c18-338">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="a0c18-339">To můžete napsat z podmínek funkce, která přebírá tyto dvě klasické bity a vrátí správnou operaci dekódování.</span><span class="sxs-lookup"><span data-stu-id="a0c18-339">You could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="a0c18-340">Tato nová funkce je ve skutečnosti funkcí, v tom, že pokud ji zavoláte se stejnými hodnotami `hereBit` a `thereBit` , vždy se vrátí stejná operace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-340">This new function is indeed a function, in that if you call it with the same values of `hereBit` and `thereBit`, you always get back the same operation.</span></span>
<span data-ttu-id="a0c18-341">Proto lze dekodér bezpečně spustit uvnitř operací, aniž byste museli mít důvod na to, jak logika dekódování komunikuje s definicemi různých specializací operace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-341">Thus, the decoder can safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="a0c18-342">To znamená, že klasická logika uvnitř funkce je izolovaná a zaručuje kompilátor, že volání funkce může být přeobjednáno pomocí impunity, pokud je zachováno zadání.</span><span class="sxs-lookup"><span data-stu-id="a0c18-342">That is, the classical logic inside a function is isolated, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="a0c18-343">Částečná aplikace</span><span class="sxs-lookup"><span data-stu-id="a0c18-343">Partial Application</span></span>

<span data-ttu-id="a0c18-344">Díky funkcím, které vracejí operace, můžete s využitím *částečné aplikace*, ve které zadáváte jednu nebo více částí vstupu do funkce nebo operace, provést mnohem více, aniž byste je skutečně volali.</span><span class="sxs-lookup"><span data-stu-id="a0c18-344">You can do significantly more with functions that return operations by using *partial application*, in which you provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="a0c18-345">V předchozím `ApplyTwice` příkladu můžete určit, že nechcete zadat hned, na které qubit by měla vstupní operace platit:</span><span class="sxs-lookup"><span data-stu-id="a0c18-345">In the earlier `ApplyTwice` example, you can indicate that you don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="a0c18-346">V tomto případě místní proměnná `twiceOp` obsahuje částečně aplikovanou operaci `ApplyTwice(op, _)` , kde `_` označuje části vstupu, které ještě nebyly určeny.</span><span class="sxs-lookup"><span data-stu-id="a0c18-346">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where `_` indicates parts of the input that have not yet been specified.</span></span>
<span data-ttu-id="a0c18-347">Při volání na `twiceOp` Další řádek předáte jako vstup do částečně použité operace všechny zbývající části vstupu do původní operace.</span><span class="sxs-lookup"><span data-stu-id="a0c18-347">When you call `twiceOp` in the next line, you pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="a0c18-348">Proto předchozí fragment kódu je prakticky stejný jako při `ApplyTwice(op, target)` přímém volání, uložte pro to, že jste zavedli novou místní proměnnou, abyste mohli zpoždění volání při poskytování některých částí vstupu.</span><span class="sxs-lookup"><span data-stu-id="a0c18-348">Thus, the previous snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that you have introduced a new local variable so you can delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="a0c18-349">Vzhledem k tomu, že operace, která je částečně aplikována, není ve skutečnosti volána, dokud není poskytnut celý vstup, můžete bezpečně použít operace, i když jsou v rámci funkcí.</span><span class="sxs-lookup"><span data-stu-id="a0c18-349">Since an operation that has been partially applied is not actually called until its entire input has been provided, you can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="a0c18-350">V zásadě byla klasická logika v rámci `SquareOperation` může být mnohem více zapojena, ale je stále izolovaná od zbytku operace zárukami, které může kompilátor nabízet o funkcích.</span><span class="sxs-lookup"><span data-stu-id="a0c18-350">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span> <span data-ttu-id="a0c18-351">Q#Standardní knihovna používá tento přístup v celém pro účely exprese klasického toku řízení způsobem, který mohou programy snadno použít.</span><span class="sxs-lookup"><span data-stu-id="a0c18-351">The Q# standard library uses this approach throughout for expressing classical control flow in a way that quantum programs can readily use.</span></span>


## <a name="recursion"></a><span data-ttu-id="a0c18-352">Rekurze</span><span class="sxs-lookup"><span data-stu-id="a0c18-352">Recursion</span></span>

<span data-ttu-id="a0c18-353">Q#je možné, že lze volat přímo nebo nepřímo rekurzivní.</span><span class="sxs-lookup"><span data-stu-id="a0c18-353">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="a0c18-354">To znamená, že operace nebo funkce může volat sám sebe nebo může zavolat jinou metodu, kterou přímo nebo nepřímo volá operaci, kterou lze volat.</span><span class="sxs-lookup"><span data-stu-id="a0c18-354">That is, an operation or function can call itself, or it can call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="a0c18-355">Existují dva důležité komentáře k použití rekurze, ale:</span><span class="sxs-lookup"><span data-stu-id="a0c18-355">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="a0c18-356">Použití rekurze v operacích může být v konfliktu s některými optimalizacemi.</span><span class="sxs-lookup"><span data-stu-id="a0c18-356">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="a0c18-357">Toto rušení může mít zásadní vliv na dobu provádění algoritmu.</span><span class="sxs-lookup"><span data-stu-id="a0c18-357">This interference can have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="a0c18-358">Při spuštění na skutečném zařízení ve formátu paměti může být velikost zásobníku omezená, takže hluboká rekurze může vést k chybě za běhu.</span><span class="sxs-lookup"><span data-stu-id="a0c18-358">When running on an actual quantum device, stack space might be limited, and so deep recursion can lead to a runtime error.</span></span>
  <span data-ttu-id="a0c18-359">Konkrétně Q# kompilátor a modul runtime neidentifikují a optimalizují koncovou rekurzi.</span><span class="sxs-lookup"><span data-stu-id="a0c18-359">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a0c18-360">Další kroky</span><span class="sxs-lookup"><span data-stu-id="a0c18-360">Next steps</span></span>

<span data-ttu-id="a0c18-361">Přečtěte si o [proměnných](xref:microsoft.quantum.guide.variables) v Q# .</span><span class="sxs-lookup"><span data-stu-id="a0c18-361">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>