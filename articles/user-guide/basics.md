---
title: Q#Práce
description: Základní konceptyQ#
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4f4a75cdaaa070fd763d7f75429b7c39357d25a5
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869643"
---
# <a name="no-locq-basics"></a><span data-ttu-id="baac4-103">Q#Práce</span><span class="sxs-lookup"><span data-stu-id="baac4-103">Q# Basics</span></span>

<span data-ttu-id="baac4-104">Tento článek představuje stručný úvod do základních stavebních bloků Q# .</span><span class="sxs-lookup"><span data-stu-id="baac4-104">This article presents a brief introduction to the basic building blocks of Q#.</span></span>

<span data-ttu-id="baac4-105">Přehled toho, co je to Q# a kde se zahodí jako základní součást sady pro vývoj pro všechna množství, najdete v tématu [co je Q# ?](xref:microsoft.quantum.overview.q-sharp).</span><span class="sxs-lookup"><span data-stu-id="baac4-105">For an overview of what Q# is and where it fits in as a fundamental component of the Quantum Development Kit, see [What is Q#?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="baac4-106">Co je program pro vydaných hodnot?</span><span class="sxs-lookup"><span data-stu-id="baac4-106">What is a quantum program?</span></span>

<span data-ttu-id="baac4-107">Z technického hlediska je program pro práci s více operačními systémy konkrétní sadou klasických podprocesů, které při volání provádějí určité operace s operačním systémem.</span><span class="sxs-lookup"><span data-stu-id="baac4-107">From a technical perspective, a quantum program is a particular set of classical subroutines which, when called, perform certain operations on a quantum system.</span></span>
<span data-ttu-id="baac4-108">Důležitým rozdílem v tomto zobrazení je, že Q# program přímo nemodeluje qubits sám sebe, ale místo toho popisuje, jak klasický kontrolovaný počítač komunikuje s těmito qubits.</span><span class="sxs-lookup"><span data-stu-id="baac4-108">An important consequence of that view is that a Q# program does not directly model qubits themselves, but rather describes how a classically controlled computer interacts with those qubits.</span></span>
<span data-ttu-id="baac4-109">Podle návrhu Q# nedefinuje stavy plnění nebo jiné vlastnosti přístavení přímo.</span><span class="sxs-lookup"><span data-stu-id="baac4-109">By design, Q# does not define quantum states or other properties of quantum mechanics directly.</span></span>
<span data-ttu-id="baac4-110">Zvažte například stav $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ popsané v tématu Průvodce přístupnými [výpočetními pojmy](xref:microsoft.quantum.concepts.intro) .</span><span class="sxs-lookup"><span data-stu-id="baac4-110">For instance, consider the state $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ discussed in the [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro) guide.</span></span>
<span data-ttu-id="baac4-111">Chcete-li tento stav připravit v Q# , začněte s fakty, že qubits jsou inicializovány ve {0} stavu $ \ket $ a že $ \ket{+} = H\ket {0} $, kde $H $ je [Převod Hadamard](xref:microsoft.quantum.glossary#hadamard), implementovaný [ `H` operací](xref:microsoft.quantum.intrinsic.h).</span><span class="sxs-lookup"><span data-stu-id="baac4-111">To prepare this state in Q#, start with the facts that the qubits are initialized in the $\ket{0}$ state, and that $\ket{+} = H\ket{0}$, where $H$ is the [Hadamard transform](xref:microsoft.quantum.glossary#hadamard), implemented by the [`H` operation](xref:microsoft.quantum.intrinsic.h).</span></span> <span data-ttu-id="baac4-112">Základní Q# kód pro inicializaci a transformaci qubit a pak vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="baac4-112">The basic Q# code to initialize and transform a qubit, then, looks like this:</span></span>

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
<span data-ttu-id="baac4-113">Další informace o inicializaci nebo *přidělování*qubits naleznete v tématu [Working with qubits](xref:microsoft.quantum.guide.qubits).</span><span class="sxs-lookup"><span data-stu-id="baac4-113">For more information on initializing, or *allocating*, qubits, see [Working with qubits](xref:microsoft.quantum.guide.qubits).</span></span>

## <a name="quantum-states-in-no-locq"></a><span data-ttu-id="baac4-114">Stavy vQ#</span><span class="sxs-lookup"><span data-stu-id="baac4-114">Quantum states in Q#</span></span>

<span data-ttu-id="baac4-115">Důležité: předchozí program výslovně neodkazuje na stav v rámci, Q# ale popisuje, jak náš program *transformoval* stav.</span><span class="sxs-lookup"><span data-stu-id="baac4-115">Importantly, the previous program does not explicitly refer to the state within Q# but described how our program *transformed* the state.</span></span>
<span data-ttu-id="baac4-116">Díky tomuto přístupu můžete být zcela nezávislá o tom, co *je* stav bez limitu, i na každém cílovém počítači, což může mít různé interpretace v závislosti na počítači.</span><span class="sxs-lookup"><span data-stu-id="baac4-116">With this approach, you can be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="baac4-117">Q#Program se nemůže introspect do stavu qubit.</span><span class="sxs-lookup"><span data-stu-id="baac4-117">A Q# program cannot introspect into the state of a qubit.</span></span>
<span data-ttu-id="baac4-118">Místo toho může program volat operace, jako je například, [`Measure`](xref:microsoft.quantum.intrinsic.measure) k získání informací z qubit a volání operací, jako je [`X`](xref:microsoft.quantum.intrinsic.x) a [`H`](xref:microsoft.quantum.intrinsic.h) k jednání ve stavu qubit.</span><span class="sxs-lookup"><span data-stu-id="baac4-118">Instead, a program can call operations such as [`Measure`](xref:microsoft.quantum.intrinsic.measure) to learn information from a qubit, and call operations such as [`X`](xref:microsoft.quantum.intrinsic.x) and [`H`](xref:microsoft.quantum.intrinsic.h) to act on the state of a qubit.</span></span>
<span data-ttu-id="baac4-119">K *tomu* , aby tyto operace skutečně fungovaly, se dá použít jenom konkrétní cílový počítač, který se používá ke spuštění konkrétního Q# programu.</span><span class="sxs-lookup"><span data-stu-id="baac4-119">What these operations actually *do* is only made concrete by the target machine used to run the particular Q# program.</span></span>
<span data-ttu-id="baac4-120">Pokud například spustíte program na našem simulátoru, simulátor provede odpovídající matematické operace do simulovaného systému pro [nastavování](xref:microsoft.quantum.machines.full-state-simulator).</span><span class="sxs-lookup"><span data-stu-id="baac4-120">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator performs the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="baac4-121">Ale prohlížíte se do budoucna, když je cílový počítač skutečným počítačem s více operačními systémy, volání těchto operací v Q# systému směruje počítač s operačním systémem do provozu, aby provedl odpovídající *reálné* operace v *reálném čase* , například přesné časované laserové impulsy.</span><span class="sxs-lookup"><span data-stu-id="baac4-121">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# directs the quantum computer to perform the corresponding *real* operations on the *real* quantum system, for example, precisely timed laser pulses).</span></span>

<span data-ttu-id="baac4-122">Q#Program znovu sloučí tyto operace, jak jsou definovány cílovým počítačem, a vytvoří tak nové operace vyšší úrovně pro expresní výpočty.</span><span class="sxs-lookup"><span data-stu-id="baac4-122">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="baac4-123">Tímto způsobem Q# usnadňuje vyjádření logiky podkladových a hybridních neřízených – klasických a běžných algoritmů, a to i v souvislosti s strukturou cílového počítače nebo simulátoru.</span><span class="sxs-lookup"><span data-stu-id="baac4-123">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

## <a name="no-locq-operations-and-functions"></a><span data-ttu-id="baac4-124">Q#operace a funkce</span><span class="sxs-lookup"><span data-stu-id="baac4-124">Q# operations and functions</span></span>

<span data-ttu-id="baac4-125">Konkrétní Q# program zahrnuje *operace*, *funkce*a libovolné uživatelsky definované typy.</span><span class="sxs-lookup"><span data-stu-id="baac4-125">Concretely, a Q# program comprises *operations*, *functions*, and any user-defined types.</span></span> 

<span data-ttu-id="baac4-126">Operace slouží k popisu transformací systémů pro plnění a jsou nejdůležitějším stavebním blokem Q# programů.</span><span class="sxs-lookup"><span data-stu-id="baac4-126">Operations are used to describe the transformations of quantum systems and are the most fundamental building block of Q# programs.</span></span> <span data-ttu-id="baac4-127">Každá operace definovaná v nástroji Q# může zavolat libovolný počet dalších operací.</span><span class="sxs-lookup"><span data-stu-id="baac4-127">Each operation defined in Q# may then call any number of other operations.</span></span>

<span data-ttu-id="baac4-128">Na rozdíl od operací se funkce používají k popisu čistě *deterministického* klasického chování a neexistují žádné vlivy na výpočetní funkce Classic.</span><span class="sxs-lookup"><span data-stu-id="baac4-128">In contrast to operations, functions are used to describe purely *deterministic* classical behavior and do not have any effects besides computing classical values.</span></span> <span data-ttu-id="baac4-129">Předpokládejme například, že chcete změřit qubits na konci programu a přidat výsledky měření do pole.</span><span class="sxs-lookup"><span data-stu-id="baac4-129">For example, suppose you want to measure the qubits at the end of a program and add the measurement results to an array.</span></span>
<span data-ttu-id="baac4-130">V tomto případě `Measure` je to *operace* , která instruuje cílový počítač, aby provedl měření na (reálné nebo simulované) qubits.</span><span class="sxs-lookup"><span data-stu-id="baac4-130">In this case, `Measure` is an *operation* that instructs the target machine to perform a measurement on the (real or simulated) qubits.</span></span> <span data-ttu-id="baac4-131">Ve stejnou dobu *funkce* zpracovávají klasický proces přidávání vrácených výsledků do pole.</span><span class="sxs-lookup"><span data-stu-id="baac4-131">At the same time, *functions* handle the classical process of adding the returned results to an array.</span></span>

<span data-ttu-id="baac4-132">Operace a funkce se společně označují jako *volatelné*.</span><span class="sxs-lookup"><span data-stu-id="baac4-132">Together, operations and functions are known as *callables*.</span></span> <span data-ttu-id="baac4-133">Jejich podkladová struktura a chování jsou zavedeny a podrobně popsány v [operacích a funkcích v Q# ](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="baac4-133">Their underlying structure and behavior are introduced and detailed in [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>


## <a name="no-locq-syntax-overview"></a><span data-ttu-id="baac4-134">Q#Přehled syntaxe</span><span class="sxs-lookup"><span data-stu-id="baac4-134">Q# syntax overview</span></span>

<span data-ttu-id="baac4-135">Syntaxe jazyka popisuje různé kombinace symbolů, které tvoří syntakticky správný program.</span><span class="sxs-lookup"><span data-stu-id="baac4-135">The syntax of a language describes the different combinations of symbols that form a syntactically correct program.</span></span>
<span data-ttu-id="baac4-136">V nástroji Q# prvky syntaxe jsou klasifikovány do tří různých skupin: typy, výrazy a příkazy.</span><span class="sxs-lookup"><span data-stu-id="baac4-136">In Q#, syntax elements are classified into three different groups: types, expressions, and statements.</span></span>

### <a name="types"></a><span data-ttu-id="baac4-137">Typy</span><span class="sxs-lookup"><span data-stu-id="baac4-137">Types</span></span>
<span data-ttu-id="baac4-138">Q#je jazyk silného typu, aby mohl kompilátor poskytovat silné záruky týkající se Q# programů v době kompilace, může to přispět k pečlivému použití typů.</span><span class="sxs-lookup"><span data-stu-id="baac4-138">Q# is a strongly-typed language, such that careful use of types can help the compiler provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="baac4-139">Kromě standardních a vestavěných primitivních typů, například,, a `Int` `Bool` `Qubit` `Result` , Q# poskytuje podporu pro uživatelsky definované typy.</span><span class="sxs-lookup"><span data-stu-id="baac4-139">In addition to standard and quantum-specific built-in primitive types, for example, `Int`, `Bool`, `Qubit`, and `Result`, Q# provides support for user-defined types.</span></span>

<span data-ttu-id="baac4-140">Popisy všech primitivních typů, podrobnosti o typech pole a řazené kolekce členů a kroky pro definování nových typů v rámci Q# souboru naleznete [v tématu typy Q# v ](xref:microsoft.quantum.guide.types).</span><span class="sxs-lookup"><span data-stu-id="baac4-140">For descriptions of all the primitive types, details for array and tuple types, and steps to define new types within a Q# file, see [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

### <a name="expressions"></a><span data-ttu-id="baac4-141">Výrazy</span><span class="sxs-lookup"><span data-stu-id="baac4-141">Expressions</span></span>
<span data-ttu-id="baac4-142">Výraz v programovacím jazyce je kombinací jedné nebo více konstant, proměnných, operátorů a funkcí, které programovací jazyk interpretuje a vyhodnocuje na konkrétní hodnotu.</span><span class="sxs-lookup"><span data-stu-id="baac4-142">An expression in a programming language is a combination of one or more constants, variables, operators, and functions that the programming language interprets and evaluates to a specific value.</span></span>
<span data-ttu-id="baac4-143">Nejvíce jednoduché pro každý typ v jazyce, výrazy tohoto typu mohou být buď *literály* , nebo symboly vázané na hodnotu daného typu.</span><span class="sxs-lookup"><span data-stu-id="baac4-143">Most simply, for every type in a language, expressions of that type can be either *literals* or symbols bound to a value of that type.</span></span>
<span data-ttu-id="baac4-144">Například `5` je `Int` literál (tedy také výraz typu `Int` ), a pokud `count` je symbol svázán s celočíselnou hodnotou `5` , `count` je také výraz celého čísla.</span><span class="sxs-lookup"><span data-stu-id="baac4-144">For example, `5` is an `Int` literal (thus also an expression of type `Int`), and if the symbol `count` is bound to the integer value `5`, then `count` is also an integer expression.</span></span>

<span data-ttu-id="baac4-145">Kromě toho výraz může obsahovat jiné výrazy kombinované konkrétními operátory.</span><span class="sxs-lookup"><span data-stu-id="baac4-145">Additionally, an expression can consist of other expressions combined by certain operators.</span></span>
<span data-ttu-id="baac4-146">Například jiný `Int` výraz, který je vyhodnocen jako `5` `2+3` .</span><span class="sxs-lookup"><span data-stu-id="baac4-146">For example, another `Int` expression that evaluates to `5` is `2+3`.</span></span>

<span data-ttu-id="baac4-147">Další informace o výrazech a kompatibilních operátorech v naleznete v Q# tématu [výrazy typu Q# v ](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="baac4-147">For more information about expressions and compatible operators in Q#, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span> 

### <a name="statements"></a><span data-ttu-id="baac4-148">Příkazy</span><span class="sxs-lookup"><span data-stu-id="baac4-148">Statements</span></span> 
<span data-ttu-id="baac4-149">Příkaz je syntaktickou jednotkou imperativního programovacího jazyka, která vyjadřuje určitou akci pro provedení. Příkazy na rozdíl od výrazů v těchto příkazech nevracejí výsledky a jsou spouštěny výhradně pro své vedlejší účinky.</span><span class="sxs-lookup"><span data-stu-id="baac4-149">A statement is a syntactic unit of an imperative programming language that expresses some action to carry out. Statements contrast with expressions in that statements do not return results and are executed solely for their side effects.</span></span> <span data-ttu-id="baac4-150">Výrazy ale vždycky vracejí výsledek a často nemají vedlejší účinky.</span><span class="sxs-lookup"><span data-stu-id="baac4-150">Expressions, however, always return a result and often do not have side effects at all.</span></span> <span data-ttu-id="baac4-151">V krátké Q# době jsou příkazy provedeny, zatímco jsou výrazy vyhodnocovány.</span><span class="sxs-lookup"><span data-stu-id="baac4-151">In short, Q# statements are executed, while expressions are evaluated.</span></span>

<span data-ttu-id="baac4-152">Jednoduchý příklad příkazu v nástroji Q# přiřazuje symbol ke výrazu:</span><span class="sxs-lookup"><span data-stu-id="baac4-152">A simple example of a statement in Q# is assigning a symbol to an expression:</span></span>
```qsharp
let count = 5;
```

<span data-ttu-id="baac4-153">Zajímavějším příkladem je `for` příkaz, který podporuje iteraci a obsahuje *blok příkazu*.</span><span class="sxs-lookup"><span data-stu-id="baac4-153">A more interesting example is the `for` statement which supports iteration and includes a *statement block*.</span></span>
<span data-ttu-id="baac4-154">Předpokládejme `qubits` je symbol vázaný k registru qubits (technicky typu `Qubit[]` nebo pole `Qubit` typů).</span><span class="sxs-lookup"><span data-stu-id="baac4-154">Suppose `qubits` is the symbol bound to a register of qubits (technically of type `Qubit[]`, or an array of `Qubit` types).</span></span> <span data-ttu-id="baac4-155">Pak...</span><span class="sxs-lookup"><span data-stu-id="baac4-155">Then</span></span>
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
<span data-ttu-id="baac4-156">je příkaz, který prochází každou qubit v registru a provádí `H` operaci na každém z nich.</span><span class="sxs-lookup"><span data-stu-id="baac4-156">is a statement that iterates over each qubit in the register, performing the `H` operation on each one.</span></span> <span data-ttu-id="baac4-157">Všimněte si, že `H(qubit);` je také samotný příkaz.</span><span class="sxs-lookup"><span data-stu-id="baac4-157">Note that `H(qubit);` is a statement in itself as well.</span></span>

<span data-ttu-id="baac4-158">Můžete použít libovolný výraz volání typu `Unit` ( `Unit` typ nevrací žádné informace) jako příkaz.</span><span class="sxs-lookup"><span data-stu-id="baac4-158">You can use any call expression of type `Unit` (a `Unit` type does not return any information) as a statement.</span></span>
<span data-ttu-id="baac4-159">Tento typ výrazu je užitečný při volání operací na qubits, která se vrátí, `Unit` protože účelem příkazu je upravit implicitní stav.</span><span class="sxs-lookup"><span data-stu-id="baac4-159">This type of expression is useful when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="baac4-160">Příkazy vyhodnocení výrazu vyžadují ukončující středník.</span><span class="sxs-lookup"><span data-stu-id="baac4-160">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="baac4-161">Příkazy můžete použít k sestavení téměř všech aspektů Q# programu a žádná jediná stránka by nemohla zahrnovat všechny informace, které se na ně vztahují.</span><span class="sxs-lookup"><span data-stu-id="baac4-161">You use statements to build nearly every aspect of a Q# program, and no single page could encompass all the information relating to them.</span></span>
<span data-ttu-id="baac4-162">Další informace o jejich lexikální struktuře a formátování naleznete v tématu [ Q# struktura souborů](xref:microsoft.quantum.guide.filestructure); informace o přiřazení a rozsahu vazby symbolů naleznete [v tématu Q# Variables in ](xref:microsoft.quantum.guide.variables)a pro smyčky toku řízení, například `for` , [v tématu řízení toku Q# v ](xref:microsoft.quantum.guide.controlflow).</span><span class="sxs-lookup"><span data-stu-id="baac4-162">For more information about their lexical structure and formatting, see [Q# File Structure](xref:microsoft.quantum.guide.filestructure); for symbol binding assignment and scope, see [Variables in Q#](xref:microsoft.quantum.guide.variables); and for control flow loops such as `for`, see [Control Flow in Q#](xref:microsoft.quantum.guide.controlflow).</span></span>

## <a name="next-steps"></a><span data-ttu-id="baac4-163">Další kroky</span><span class="sxs-lookup"><span data-stu-id="baac4-163">Next steps</span></span>

<span data-ttu-id="baac4-164">Začněte se učit o [typech Q# v ](xref:microsoft.quantum.guide.types).</span><span class="sxs-lookup"><span data-stu-id="baac4-164">Start learning about [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="baac4-165">Další informace o základech a motivaci na pozadí Q# najdete v tématu [Proč to Q# ](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)potřebujeme.</span><span class="sxs-lookup"><span data-stu-id="baac4-165">For more background about the foundations and motivation behind Q#, see [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>
