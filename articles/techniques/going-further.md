---
title: 'Přejdeme k dalším technikám Q # | Microsoft Docs'
description: 'Přejdeme k dalším technikám Q #'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.going-further
ms.openlocfilehash: bd2b799d4001e280baccb04158247891b9cbb5bc
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820194"
---
# <a name="going-further"></a><span data-ttu-id="69b25-103">Dál</span><span class="sxs-lookup"><span data-stu-id="69b25-103">Going Further</span></span> #

<span data-ttu-id="69b25-104">Teď, když jste se seznámili s tím, jak psát zajímavé programy v Q #, se tato část doplní o několik pokročilých témat, která by se měla ukázat jako užitečná.</span><span class="sxs-lookup"><span data-stu-id="69b25-104">Now that you've seen how to write interesting quantum programs in Q#, this section goes further by introducing a few more advanced topics that should prove useful going forward.</span></span>


## <a name="generic-operations-and-functions"></a><span data-ttu-id="69b25-105">Obecné operace a funkce</span><span class="sxs-lookup"><span data-stu-id="69b25-105">Generic Operations and Functions</span></span> ##

> [!TIP]
> <span data-ttu-id="69b25-106">V této části se předpokládá některá základní znalost [obecného prostředí v C# ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), [obecných typech F# ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [ C++ šablonách](https://docs.microsoft.com/cpp/cpp/templates-cpp)nebo podobných přístupů k metaprogramování šablonou v jiných jazycích.</span><span class="sxs-lookup"><span data-stu-id="69b25-106">This section assumes some basic familiarity with [generics in C#](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), [generics in F#](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [C++ templates](https://docs.microsoft.com/cpp/cpp/templates-cpp), or similar approaches to metaprogramming in other languages.</span></span>

<span data-ttu-id="69b25-107">Mnoho funkcí a operací, které můžeme chtít definovat, se ve skutečnosti nespoléhá na typy jejich vstupů, ale místo toho pouze implicitně používají jejich typy prostřednictvím jiné funkce nebo operace.</span><span class="sxs-lookup"><span data-stu-id="69b25-107">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="69b25-108">Představte si třeba koncept *mapy* společný pro mnoho funkčních jazyků. po předané funkci $f (x) $ a kolekci hodnot $\{x_1, x_2, \dots, x_n\}$, map vrátí novou kolekci $\{f (x_1), f (x_2), \dots, f (x_n)\}$.</span><span class="sxs-lookup"><span data-stu-id="69b25-108">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="69b25-109">K implementaci tohoto v Q # můžeme využít výhod těchto funkcí jako první třídy.</span><span class="sxs-lookup"><span data-stu-id="69b25-109">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="69b25-110">Pojďme si napsat rychlý příklad `Map`, při použití ★ jako zástupného symbolu, přičemž zjistíme, jaké typy potřebujeme.</span><span class="sxs-lookup"><span data-stu-id="69b25-110">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : ★ -> ★, values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="69b25-111">Všimněte si, že tato funkce vypadá velmi stejně bez ohledu na to, jaké vlastní typy nahrazujíme.</span><span class="sxs-lookup"><span data-stu-id="69b25-111">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="69b25-112">Mapa z celých čísel na Paul, například vypadá podobně jako mapa z čísel s plovoucí desetinnou čárkou na řetězce:</span><span class="sxs-lookup"><span data-stu-id="69b25-112">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

```qsharp
function MapIntsToPaulis(fn : Int -> Pauli, values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : Double -> String, values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="69b25-113">V podstatě jsme mohli napsat verzi `Map` pro každou dvojici typů, ke kterým dochází, ale to přináší řadu potíží.</span><span class="sxs-lookup"><span data-stu-id="69b25-113">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="69b25-114">Pokud například v `Map`zjistíte chybu, je nutné zajistit, aby se oprava používala jednotně napříč všemi verzemi `Map`.</span><span class="sxs-lookup"><span data-stu-id="69b25-114">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="69b25-115">Kromě toho, Pokud vytvoříme nové řazené kolekce členů nebo UDT, je teď také potřeba vytvořit nový `Map` k tomu, aby bylo možné přejít i k novému typu.</span><span class="sxs-lookup"><span data-stu-id="69b25-115">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="69b25-116">I když je to pro malý počet takových funkcí rušivý, protože shromažďujeme více a více funkcí stejné formy jako `Map`, náklady na zavedení nových typů se v poměrně krátkém pořadí stávají nepřiměřeně veliké.</span><span class="sxs-lookup"><span data-stu-id="69b25-116">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="69b25-117">Mnohé z těchto potíží se ale nedostaly do tohoto kompilátoru informace, které potřebuje k tomu, abyste zjistili, jak různé verze `Map` souvisejí.</span><span class="sxs-lookup"><span data-stu-id="69b25-117">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="69b25-118">Chceme, aby kompilátor považoval `Map` jako nějaký druh matematické funkce od Q *# do funkcí q #.*</span><span class="sxs-lookup"><span data-stu-id="69b25-118">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>
<span data-ttu-id="69b25-119">Tento pojem je formální tím, že povoluje funkce a operace pro *parametry typu*a také jejich běžné parametry řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="69b25-119">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="69b25-120">V předchozích příkladech si chceme představit `Map` jako parametry typu `Int, Pauli` v prvním případě a `Double, String` ve druhém případě.</span><span class="sxs-lookup"><span data-stu-id="69b25-120">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="69b25-121">Ve většině případů lze tyto parametry typu použít, jako by se jednalo o běžné typy: používáme hodnoty parametrů typu k vytváření polí a řazených kolekcí členů, volání funkcí a operací a přiřazení k běžným nebo proměnlivým proměnným.</span><span class="sxs-lookup"><span data-stu-id="69b25-121">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="69b25-122">Největší případ nepřímých závislostí je, že qubits, kde se program Q # nemůže přímo spoléhat na strukturu `Qubit`ho typu, ale **musí** předat takové typy jiným operacím a funkcím.</span><span class="sxs-lookup"><span data-stu-id="69b25-122">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="69b25-123">Po návratu do výše uvedeného příkladu vidíte, že potřebujeme `Map`, aby bylo možné zadat parametry typu, jeden pro reprezentaci vstupu `fn` a druhý, který představuje výstup z `fn`.</span><span class="sxs-lookup"><span data-stu-id="69b25-123">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="69b25-124">V Q # se to zapisuje přidáním lomených závorek (to `<>`, nikoli brakets $ \braket{}$!) za názvem funkce nebo operace v deklaraci a výpisem každého parametru typu.</span><span class="sxs-lookup"><span data-stu-id="69b25-124">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="69b25-125">Název každého parametru typu musí začínat `'`em Tick, což značí, že se jedná o parametr typu, a ne běžný typ (označovaný také jako *konkrétní* typ).</span><span class="sxs-lookup"><span data-stu-id="69b25-125">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="69b25-126">Pro `Map`zapisujeme:</span><span class="sxs-lookup"><span data-stu-id="69b25-126">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : 'Input -> 'Output, values : 'Input[]) : 'Output {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="69b25-127">Všimněte si, že definice `Map<'Input, 'Output>` vypadá extrémně podobně jako verze, které jsme předtím napsali.</span><span class="sxs-lookup"><span data-stu-id="69b25-127">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="69b25-128">Jediným rozdílem je, že explicitně informovali kompilátor, že `Map` přímo nezávisí na tom, co `'Input` a `'Output` jsou, ale funguje pro všechny dva typy pomocí nepřímo prostřednictvím `fn`.</span><span class="sxs-lookup"><span data-stu-id="69b25-128">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="69b25-129">Po definování `Map<'Input, 'Output>` tímto způsobem můžeme zavolat, jako by šlo o běžnou funkci:</span><span class="sxs-lookup"><span data-stu-id="69b25-129">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="69b25-130">Zápis obecných funkcí a operací je jedním z míst, kde "řazená kolekce členů" v řazené kolekci členů "je velmi užitečným způsobem, jak se zamyslet na funkce a operace Q #.</span><span class="sxs-lookup"><span data-stu-id="69b25-130">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="69b25-131">Vzhledem k tomu, že každá funkce přebírá přesně jeden vstup a vrátí přesně jeden výstup, vstup typu `'T -> 'U` odpovídá *libovolné* funkci Q #.</span><span class="sxs-lookup"><span data-stu-id="69b25-131">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="69b25-132">Podobně lze každou operaci předat do vstupu typu `'T => 'U`.</span><span class="sxs-lookup"><span data-stu-id="69b25-132">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="69b25-133">V druhém příkladu zvažte, jak napsat funkci, která vrací kompozici dvou dalších funkcí:</span><span class="sxs-lookup"><span data-stu-id="69b25-133">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="69b25-134">V tomto případě je nutné přesně zadat, co `A`, `B`a `C` jsou, proto vážně omezují nástroj naší nové `Compose` funkce.</span><span class="sxs-lookup"><span data-stu-id="69b25-134">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="69b25-135">Po všech `Compose` závisí jenom na `A`, `B`a `C` *prostřednictvím* `innerFn` a `outerFn`.</span><span class="sxs-lookup"><span data-stu-id="69b25-135">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="69b25-136">Alternativně můžeme přidat parametry typu do `Compose`, které naznačují, že funguje pro *všechny* `A`, `B`a `C`, pokud tyto parametry odpovídají následujícím parametrům, které očekává `innerFn` a `outerFn`:</span><span class="sxs-lookup"><span data-stu-id="69b25-136">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="69b25-137">Standardní knihovny Q # poskytují rozsah takových operací, které jsou parametrizované pro typ, a usnadňují tak vyjádření toku řízení vyšším řádu.</span><span class="sxs-lookup"><span data-stu-id="69b25-137">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="69b25-138">Tyto postupy jsou podrobněji popsány v [příručce ke standardní knihovně Q #](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="69b25-138">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="borrowing-qubits"></a><span data-ttu-id="69b25-139">Výpůjčka Qubits</span><span class="sxs-lookup"><span data-stu-id="69b25-139">Borrowing Qubits</span></span> ##

<span data-ttu-id="69b25-140">Výpůjční mechanizmus umožňuje přidělení qubits, které lze použít jako pomocné místo během výpočtu.</span><span class="sxs-lookup"><span data-stu-id="69b25-140">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span> <span data-ttu-id="69b25-141">Tyto qubits nejsou obecně v čistém stavu, tj., nejsou nutně inicializovány ve známém stavu, například $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="69b25-141">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span> <span data-ttu-id="69b25-142">Jedna z nich také mluví "nequbitscí", protože jejich stav je neznámý a může být dokonce entangled s ostatními částmi paměti počítače.</span><span class="sxs-lookup"><span data-stu-id="69b25-142">One also speaks of "dirty" qubits as their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span> <span data-ttu-id="69b25-143">Mezi známé případy použití undirty qubits jsou implementace více řízených CNOTch bran, které vyžadují jenom velmi málo qubits a implementaci přírůstku.</span><span class="sxs-lookup"><span data-stu-id="69b25-143">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>

<span data-ttu-id="69b25-144">V Canon existují příklady, které používají klíčové slovo `borrowing`, například funkce `MultiControlledXBorrow` definována níže.</span><span class="sxs-lookup"><span data-stu-id="69b25-144">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="69b25-145">Pokud `controls` označuje qubits ovládacího prvku, který má být přidán do operace `X`, bude tato implementace obsahovat celkový `Length(controls)-2` mnoho nezměněných ancillas.</span><span class="sxs-lookup"><span data-stu-id="69b25-145">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

<span data-ttu-id="69b25-146">Všimněte si, že rozsáhlé použití `With` kombinátorem---ve formuláři, které platí pro operace, které podporují sousední, tj. `WithA`---byly provedeny v tomto příkladu, což je dobrý programovací styl jako přidání ovládacího prvku do struktur zahrnující `With` pouze rozšíření ovládacího prvku do vnitřní operace.</span><span class="sxs-lookup"><span data-stu-id="69b25-146">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example which is good programming style as adding control to structures involving `With` only propagates control to the inner operation.</span></span> <span data-ttu-id="69b25-147">Dále si všimněte, že kromě `body` operace byla explicitně poskytnuta implementace `controlled` těla operace, nikoli použití příkazu `controlled auto`.</span><span class="sxs-lookup"><span data-stu-id="69b25-147">Further note that here in addition to the `body` of the operation an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span> <span data-ttu-id="69b25-148">Důvodem je to, že ví od struktury okruhu, jak snadno přidat další ovládací prvky, které jsou ve srovnání s přidáním ovládacího prvku do každé a každé samostatné brány v `body`vhodné.</span><span class="sxs-lookup"><span data-stu-id="69b25-148">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="69b25-149">Tento kód se dá porovnávat s jinou funkcí Canon `MultiControlledXClean`, která dosahuje stejného cíle implementace `X` operace řízené vynásobením, ale používá několik čistých qubits pomocí mechanismu `using`.</span><span class="sxs-lookup"><span data-stu-id="69b25-149">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 
