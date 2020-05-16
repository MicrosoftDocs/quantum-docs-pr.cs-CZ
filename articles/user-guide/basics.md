---
title: 'Základy Q #'
description: 'Základní koncepty Q #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: fd0ea47f00b1456ec460808ef7d451c8427677cd
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431151"
---
# <a name="q-basics"></a><span data-ttu-id="0767a-103">Základy Q #</span><span class="sxs-lookup"><span data-stu-id="0767a-103">Q# Basics</span></span>

<span data-ttu-id="0767a-104">V této části uvádíme stručný úvod do základních stavebních bloků Q #.</span><span class="sxs-lookup"><span data-stu-id="0767a-104">In this section we present a brief introduction to the basic building blocks of Q#.</span></span>

<span data-ttu-id="0767a-105">Pokud potřebujete rychlý přehled toho, co je Q # a kde se zahodí jako základní součást sady pro vývoj pro všechna množství, můžete zjistit, [co je q #?](xref:microsoft.quantum.overview.q-sharp).</span><span class="sxs-lookup"><span data-stu-id="0767a-105">For a quick overview of what Q# is and where it fits in as a fundamental component of the Quantum Development Kit, you can check out [What is Q#?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="0767a-106">Co je program pro vydaných hodnot?</span><span class="sxs-lookup"><span data-stu-id="0767a-106">What is a quantum program?</span></span>

<span data-ttu-id="0767a-107">Z technického hlediska je program pro práci s více operačními systémy zobrazený jako konkrétní sada klasických podprocesů, které při volání provádějí určité operace s operačním systémem.</span><span class="sxs-lookup"><span data-stu-id="0767a-107">From a technical perspective, a quantum program can be seen as a particular set of classical subroutines which, when called, perform certain operations on a quantum system.</span></span>
<span data-ttu-id="0767a-108">Důležitým vlivem tohoto zobrazení je to, že program napsaný v Q # přímo nemodeluje qubits sám sebe, ale místo toho popisuje, jak počítač s klasickým ovládacím prvkem komunikuje s těmito qubits.</span><span class="sxs-lookup"><span data-stu-id="0767a-108">An important consequence of that view is that a program written in Q# does not directly model qubits themselves, but rather describes how a classical control computer interacts with those qubits.</span></span>
<span data-ttu-id="0767a-109">Podle návrhu, Q # proto nedefinuje stavy, které jsou ve stavu plnění, ani jiné vlastnosti nestavového mechanismu.</span><span class="sxs-lookup"><span data-stu-id="0767a-109">By design, Q# thus does not define quantum states or other properties of quantum mechanics directly.</span></span>
<span data-ttu-id="0767a-110">Zvažte například stav $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ popsané v tématu Průvodce přístupnými [výpočetními pojmy](xref:microsoft.quantum.concepts.intro) .</span><span class="sxs-lookup"><span data-stu-id="0767a-110">For instance, consider the state $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ discussed in the [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro) guide.</span></span>
<span data-ttu-id="0767a-111">Chcete-li tento stav připravit v Q #, používáme fakty, že qubits jsou inicializovány ve {0} stavu $ \ket $ a že $ \ket{+} = H\ket {0} $, kde $H $ je převod Hadamard, implementovaný pomocí [ `H` operace] (] (odkazy XREF: Microsoft. NázevOperace. vnitřní. H):</span><span class="sxs-lookup"><span data-stu-id="0767a-111">To prepare this state in Q#, we use the facts that the qubits are initialized in the $\ket{0}$ state, and that $\ket{+} = H\ket{0}$, where $H$ is the Hadamard transform, implemented by the [`H` operation](](xref:microsoft.quantum.intrinsic.h):</span></span>

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0⟩.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0⟩ = |+⟩, as we wanted.
}
```

## <a name="quantum-states-in-q"></a><span data-ttu-id="0767a-112">Stavy v Q #</span><span class="sxs-lookup"><span data-stu-id="0767a-112">Quantum states in Q#</span></span>

<span data-ttu-id="0767a-113">Při psaní výše uvedeného programu jsme v rámci tohoto programu explicitně neodkazovali na stav ve Q #, ale místo toho jsme popsali, jak byl stav *transformován* náš program.</span><span class="sxs-lookup"><span data-stu-id="0767a-113">Importantly, in writing the above program, we did not explicitly refer to the state within Q#, but rather described how the state was *transformed* by our program.</span></span>
<span data-ttu-id="0767a-114">To nám umožní zcela nezávislá informace o tom, co *je* stav bez nároku na každém cílovém počítači, což může mít různé interpretace v závislosti na počítači.</span><span class="sxs-lookup"><span data-stu-id="0767a-114">This allows us to be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="0767a-115">Program Q # nemá žádnou schopnost introspect do stavu qubit.</span><span class="sxs-lookup"><span data-stu-id="0767a-115">A Q# program has no ability to introspect into the state of a qubit.</span></span>
<span data-ttu-id="0767a-116">Program může spíše volat operace, jako je například, [`Measure`](xref:microsoft.quantum.intrinsic.measure) k získání informací z qubit a volání operací, jako je [`X`](xref:microsoft.quantum.intrinsic.x) a [`H`](xref:microsoft.quantum.intrinsic.h) k jednání ve stavu qubit.</span><span class="sxs-lookup"><span data-stu-id="0767a-116">Rather, a program can call operations such as [`Measure`](xref:microsoft.quantum.intrinsic.measure) to learn information from a qubit, and call operations such as [`X`](xref:microsoft.quantum.intrinsic.x) and [`H`](xref:microsoft.quantum.intrinsic.h) to act on the state of a qubit.</span></span>
<span data-ttu-id="0767a-117">Díky *tomu* se tyto operace skutečně provádějí jenom v cílovém počítači, který používáme ke spuštění konkrétního programu Q #.</span><span class="sxs-lookup"><span data-stu-id="0767a-117">What these operations actually *do* is only made concrete by the target machine we use to run the particular Q# program.</span></span>
<span data-ttu-id="0767a-118">Například pokud je program spuštěný v [celém kompletním simulátoru](xref:microsoft.quantum.machines.full-state-simulator), simulátor provede odpovídající matematické operace do simulovaného systému.</span><span class="sxs-lookup"><span data-stu-id="0767a-118">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator will perform the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="0767a-119">Ale pokud je cílový počítač skutečným počítačem, který se blíží k budoucnosti, volání takových operací v Q # nasměruje počítač s příznakem do provozu, aby provedl odpovídající *reálné* operace v *reálném* systému doby provozu (například přesně časované laserové Pulse).</span><span class="sxs-lookup"><span data-stu-id="0767a-119">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# will direct the quantum computer to perform the corresponding *real* operations on the *real* quantum system (e.g. precisely timed laser pulses).</span></span>

<span data-ttu-id="0767a-120">Program Q # znovu sloučí tyto operace, jak jsou definovány cílovým počítačem, a vytvoří tak nové operace vyšší úrovně, které budou vyjadřovat výpočetní procesory.</span><span class="sxs-lookup"><span data-stu-id="0767a-120">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="0767a-121">V tomto případě Q # usnadňuje vyjádření logiky podkladových a hybridních životních stojí – klasických algoritmů, a to i v souvislosti se strukturou cílového počítače nebo simulátoru.</span><span class="sxs-lookup"><span data-stu-id="0767a-121">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

## <a name="q-operations-and-functions"></a><span data-ttu-id="0767a-122">Operace a funkce Q #</span><span class="sxs-lookup"><span data-stu-id="0767a-122">Q# operations and functions</span></span>

<span data-ttu-id="0767a-123">V betonu se program Q # skládá z *operací*, *funkcí*a libovolných uživatelsky definovaných typů.</span><span class="sxs-lookup"><span data-stu-id="0767a-123">Concretely, a Q# program is comprised of *operations*, *functions*, and any user-defined types.</span></span> 

<span data-ttu-id="0767a-124">Operace se používají k popisu transformací systémů a jsou to nejzákladnější stavební bloky programů Q #.</span><span class="sxs-lookup"><span data-stu-id="0767a-124">Operations are used to describe the transformations of quantum systems and are the most basic building block of Q# programs.</span></span> <span data-ttu-id="0767a-125">Každá operace definovaná v Q # může potom zavolat libovolný počet dalších operací.</span><span class="sxs-lookup"><span data-stu-id="0767a-125">Each operation defined in Q# may then call any number of other operations.</span></span>

<span data-ttu-id="0767a-126">Na rozdíl od operací se funkce používají k popisu čistě *deterministického* klasického chování a neexistují žádné vlivy na výpočetní funkce Classic.</span><span class="sxs-lookup"><span data-stu-id="0767a-126">In contrast to operations, functions are used to describe purely *deterministic* classical behavior and do not have any effects besides computing classical values.</span></span> <span data-ttu-id="0767a-127">Předpokládejme například, že byste chtěli změřit naše qubits na konci programu a přidat výsledky měření do pole.</span><span class="sxs-lookup"><span data-stu-id="0767a-127">For example, suppose we would like to measure our qubits at the end of a program, and add the measurement results to an array.</span></span>
<span data-ttu-id="0767a-128">V tomto případě `Measure` je to *operace* , která instruuje cílový počítač, aby provedl měření na (reálné nebo simulované) qubits a klasický proces přidávání vrácených výsledků do pole bude zpracován *funkcí Functions*.</span><span class="sxs-lookup"><span data-stu-id="0767a-128">In this case `Measure` is an *operation* which instructs the target machine to perform a measurement on the (real or simulated) qubits, and the classical process of adding the returned results to an array will be handled by *functions*.</span></span>

<span data-ttu-id="0767a-129">Operace a funkce jsou společně označovány jako *volatelné*a jejich podkladová struktura a chování se zavádějí na [operace a funkce na stránce Q #](xref:microsoft.quantum.guide.operationsfunctions) .</span><span class="sxs-lookup"><span data-stu-id="0767a-129">Together, operations and functions are referred to as *callables*, and their underlying structure and behavior is introduced on the [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) page.</span></span>


## <a name="q-syntax-overview"></a><span data-ttu-id="0767a-130">Přehled syntaxe Q #</span><span class="sxs-lookup"><span data-stu-id="0767a-130">Q# syntax overview</span></span>

<span data-ttu-id="0767a-131">Syntaxe jazyka popisuje různé kombinace symbolů, které tvoří syntakticky správný program.</span><span class="sxs-lookup"><span data-stu-id="0767a-131">The syntax of a language describes the different combinations of symbols that form a syntactically correct program.</span></span>
<span data-ttu-id="0767a-132">V Q # můžeme klasifikovat prvky své syntaxe ve třech různých skupinách: typy, výrazy a příkazy.</span><span class="sxs-lookup"><span data-stu-id="0767a-132">In Q# we can classify the elements of its syntax in three different groups: types, expressions and statements.</span></span>

### <a name="types"></a><span data-ttu-id="0767a-133">Typy</span><span class="sxs-lookup"><span data-stu-id="0767a-133">Types</span></span>
<span data-ttu-id="0767a-134">Q # je jazyk silného typu, který může při kompilaci poskytnout pečlivou možnost použití typů za účelem poskytnutí silné záruky na programy Q #.</span><span class="sxs-lookup"><span data-stu-id="0767a-134">Q# is a strongly-typed language, such that careful use of types can help the compiler provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="0767a-135">Kromě standardních a vestavěných primitivních typů (např.,, `Int` `Bool` `Qubit` a `Result` ) v případě, že Q # poskytuje podporu pro uživatelsky definované typy.</span><span class="sxs-lookup"><span data-stu-id="0767a-135">In addition to standard and quantum-specific built-in primitive types (e.g. `Int`, `Bool`, `Qubit`, and `Result`), Q# provides support for user-defined types.</span></span>
<span data-ttu-id="0767a-136">Všechny primitivní typy "Q #" jsou popsány na stránce [typy v souboru q #](xref:microsoft.quantum.guide.types) spolu s podrobnostmi o typech polí a řazené kolekce členů a také o tom, jak definovat nové typy v souboru Q #.</span><span class="sxs-lookup"><span data-stu-id="0767a-136">All of Q#'s various primitive types are described on the [Types in Q#](xref:microsoft.quantum.guide.types) page, along with details on array and tuple types, as well as how to define new types within a Q# file.</span></span>

### <a name="expressions"></a><span data-ttu-id="0767a-137">Výrazy</span><span class="sxs-lookup"><span data-stu-id="0767a-137">Expressions</span></span>
<span data-ttu-id="0767a-138">Výraz v programovacím jazyce je kombinací jedné nebo více konstant, proměnných, operátorů a funkcí, které programovací jazyk interpretuje a vyhodnocuje na konkrétní hodnotu.</span><span class="sxs-lookup"><span data-stu-id="0767a-138">An expression in a programming language is a combination of one or more constants, variables, operators, and functions that the programming language interprets and evaluates to a specific value.</span></span>
<span data-ttu-id="0767a-139">Nejvíce jednoduché pro každý typ v jazyce, výrazy tohoto typu mohou být buď *literály* , nebo symboly vázané na hodnotu daného typu.</span><span class="sxs-lookup"><span data-stu-id="0767a-139">Most simply, for every type in a language, expressions of that type can be either *literals* or symbols bound to a value of that type.</span></span>
<span data-ttu-id="0767a-140">Například `5` je `Int` literál (tedy také výraz typu `Int` ), a pokud `count` je symbol svázán s celočíselnou hodnotou `5` , `count` je také výraz celého čísla.</span><span class="sxs-lookup"><span data-stu-id="0767a-140">For example, `5` is an `Int` literal (thus also an expression of type `Int`), and if the symbol `count` is bound to the integer value `5`, then `count` is also an integer expression.</span></span>

<span data-ttu-id="0767a-141">Kromě toho se výraz může skládat z dalších výrazů v kombinaci s určitými operátory.</span><span class="sxs-lookup"><span data-stu-id="0767a-141">Additionally, an expression can consist of other expressions combined with certain operators.</span></span>
<span data-ttu-id="0767a-142">Proto další příklad `Int` výrazu, který je vyhodnocen jako `5` `2+3` .</span><span class="sxs-lookup"><span data-stu-id="0767a-142">Hence another example of an `Int` expression which evaluates to `5` is `2+3`.</span></span>

<span data-ttu-id="0767a-143">Možné výrazy typů v Q # a také kompatibilní operátory, které lze použít pro jejich vytvoření, jsou popsány na [výrazech typu na stránce Q #](xref:microsoft.quantum.guide.expressions) .</span><span class="sxs-lookup"><span data-stu-id="0767a-143">The possible expressions of types in Q#, as well as the compatible operators that can be used to form them, are detailed on the [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) page.</span></span> 

### <a name="statements"></a><span data-ttu-id="0767a-144">Příkazy</span><span class="sxs-lookup"><span data-stu-id="0767a-144">Statements</span></span> 
<span data-ttu-id="0767a-145">Příkaz je syntaktickou jednotkou imperativního programovacího jazyka, která vyjadřuje určitou akci, která má být provedena. Příkazy kontrastující s výrazy v těchto příkazech nevrací výsledky a jsou spouštěny výhradně pro své vedlejší účinky, zatímco výrazy vždy vracejí výsledek a často nemají vedlejší účinky.</span><span class="sxs-lookup"><span data-stu-id="0767a-145">A statement is a syntactic unit of an imperative programming language that expresses some action to be carried out. Statements contrast with expressions in that statements do not return results and are executed solely for their side effects, while expressions always return a result and often do not have side effects at all.</span></span>
<span data-ttu-id="0767a-146">Tento rozdíl je často pozorován ve slovech: je vyhodnocen výraz, zatímco je proveden příkaz.</span><span class="sxs-lookup"><span data-stu-id="0767a-146">This distinction is frequently observed in wording: an expression is evaluated, whereas a statement is executed.</span></span>

<span data-ttu-id="0767a-147">Velmi základní příklad příkazu v Q # přiřazuje k výrazu symbol:</span><span class="sxs-lookup"><span data-stu-id="0767a-147">A very basic example of a statement in Q# is assigning a symbol to an expression:</span></span>
```qsharp
let count = 5;
```

<span data-ttu-id="0767a-148">Trochu zajímavější příklad je `for` příkaz, který podporuje iteraci a obsahuje *blok příkazu*.</span><span class="sxs-lookup"><span data-stu-id="0767a-148">A slightly more interesting example is the `for` statement which supports iteration and includes a *statement block*.</span></span>
<span data-ttu-id="0767a-149">Předpokládejme `qubits` je symbol vázaný k registru qubits (technicky typu `Qubit[]` , tj. pole `Qubit` typů).</span><span class="sxs-lookup"><span data-stu-id="0767a-149">Suppose `qubits` is the symbol bound to a register of qubits (technically of type `Qubit[]`, i.e. an array of `Qubit` types).</span></span> <span data-ttu-id="0767a-150">Pak...</span><span class="sxs-lookup"><span data-stu-id="0767a-150">Then</span></span>
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
<span data-ttu-id="0767a-151">je příkaz, který projde každou qubit v registru a provede `H` operaci na každém z nich.</span><span class="sxs-lookup"><span data-stu-id="0767a-151">is a statement which iterates over each qubit in the register, performing the `H` operation on each.</span></span> <span data-ttu-id="0767a-152">Všimněte si, že `H(qubit);` je také samotný příkaz.</span><span class="sxs-lookup"><span data-stu-id="0767a-152">Note that `H(qubit);` is a statement in itself as well.</span></span>

<span data-ttu-id="0767a-153">Ve skutečnosti `Unit` může být jako příkaz použit libovolný výraz volání typu (ty, které se dají volat, které nevracejí žádné informace).</span><span class="sxs-lookup"><span data-stu-id="0767a-153">In fact, any call expression of type `Unit` (those callables that do not return any information) may be used as a statement.</span></span>
<span data-ttu-id="0767a-154">To je primárně použito při volání operací na qubits, které vracejí, `Unit` protože účel příkazu je upravit implicitní stav nečinnosti.</span><span class="sxs-lookup"><span data-stu-id="0767a-154">This is primarily of use when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="0767a-155">Příkazy vyhodnocení výrazu vyžadují ukončující středník.</span><span class="sxs-lookup"><span data-stu-id="0767a-155">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="0767a-156">Skoro každý aspekt programu Q # je sestaven pomocí příkazů, takže žádná z nich nemůže zahrnovat všechny informace, které se na ně vztahují.</span><span class="sxs-lookup"><span data-stu-id="0767a-156">Nearly every aspect of a Q# program is built using statements, so no single page could encompass all the information relating to them.</span></span>
<span data-ttu-id="0767a-157">Jejich lexikální struktura a formátování jsou však popsány na stránce [struktury souborů q #](xref:microsoft.quantum.guide.filestructure) , přiřazení symbolů a rozsahu u [proměnných v q #](xref:microsoft.quantum.guide.variables)a v cyklech toku řízení, jako je `for` například [tok řízení v q #](xref:microsoft.quantum.guide.controlflow).</span><span class="sxs-lookup"><span data-stu-id="0767a-157">However, their lexical structure and formatting is described on the [Q# File Structure](xref:microsoft.quantum.guide.filestructure) page, symbol binding assignment and scope at [Variables in Q#](xref:microsoft.quantum.guide.variables), and control flow loops such as `for` at [Control Flow in Q#](xref:microsoft.quantum.guide.controlflow).</span></span>


## <a name="whats-next"></a><span data-ttu-id="0767a-158">Co dále?</span><span class="sxs-lookup"><span data-stu-id="0767a-158">What's next?</span></span>
<span data-ttu-id="0767a-159">V celé zbývající části tohoto průvodce vám ukážeme, jak pomocí Q # vytvářet komplexní programy pro vystavování prostřednictvím základních stavebních bloků operací, funkcí a typů.</span><span class="sxs-lookup"><span data-stu-id="0767a-159">Throughout the rest of this guide, we will show you how to use Q# to construct complex quantum programs through the basic building blocks of operations, functions, and types.</span></span>

<span data-ttu-id="0767a-160">Pokud chcete začít, můžete začít učit se o [typech v Q #](xref:microsoft.quantum.guide.types).</span><span class="sxs-lookup"><span data-stu-id="0767a-160">To get started, you can start learning about [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="0767a-161">Pokud vás zajímá více o základech a motivaci za Q #, podívejte se, [Proč musíme q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span><span class="sxs-lookup"><span data-stu-id="0767a-161">If you are interested in learning more about the foundations and motivation behind Q#, check out [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>
