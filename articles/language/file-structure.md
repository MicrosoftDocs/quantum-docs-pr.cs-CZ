---
title: 'Struktura souborů Q #'
description: 'Naučte se strukturovat obory názvů a deklarace operací, funkcí a uživatelsky definovaných typů v programech a knihovnách Q #.'
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b4bb7d4d70677dbd5d921a9f68313760499a56a1
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907388"
---
# <a name="file-structure"></a><span data-ttu-id="ed34e-103">Struktura souborů</span><span class="sxs-lookup"><span data-stu-id="ed34e-103">File Structure</span></span>

<span data-ttu-id="ed34e-104">Soubor Q # se skládá z sekvence deklarací oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="ed34e-104">A Q# file consists of a sequence of namespace declarations.</span></span>
<span data-ttu-id="ed34e-105">Každá deklarace oboru názvů obsahuje deklarace pro uživatelsky definované typy, operace a funkce.</span><span class="sxs-lookup"><span data-stu-id="ed34e-105">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="ed34e-106">Deklarace oboru názvů může obsahovat libovolný počet každého typu deklarace a v libovolném pořadí.</span><span class="sxs-lookup"><span data-stu-id="ed34e-106">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="ed34e-107">Jediný text, který se může zobrazit mimo deklaraci oboru názvů, je komentáře.</span><span class="sxs-lookup"><span data-stu-id="ed34e-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="ed34e-108">Konkrétně dokumentační komentáře pro obor názvů předcházejí deklaraci.</span><span class="sxs-lookup"><span data-stu-id="ed34e-108">In particular, documentation comments for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="ed34e-109">Deklarace oboru názvů</span><span class="sxs-lookup"><span data-stu-id="ed34e-109">Namespace Declarations</span></span>

<span data-ttu-id="ed34e-110">Soubor Q # má obvykle přesně jednu deklaraci oboru názvů, ale může mít hodnotu None (a být prázdný nebo obsahovat pouze komentáře) nebo může obsahovat více oborů názvů.</span><span class="sxs-lookup"><span data-stu-id="ed34e-110">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="ed34e-111">Deklarace oboru názvů nesmí být vnořené.</span><span class="sxs-lookup"><span data-stu-id="ed34e-111">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="ed34e-112">Stejný obor názvů může být deklarován ve více souborech Q #, které jsou kompilovány společně, pokud neexistují deklarace typu, operace nebo funkce se stejným názvem.</span><span class="sxs-lookup"><span data-stu-id="ed34e-112">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="ed34e-113">Konkrétně je neplatný pro definování stejného typu ve stejném oboru názvů ve více souborech, a to i v případě, že deklarace jsou identické.</span><span class="sxs-lookup"><span data-stu-id="ed34e-113">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="ed34e-114">Deklarace oboru názvů se skládá z klíčového slova `namespace`následovaný názvem oboru názvů, levou složenou závorkou `{`, deklaracemi obsaženými v oboru názvů a `}`uzavírací závorkou.</span><span class="sxs-lookup"><span data-stu-id="ed34e-114">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="ed34e-115">Názvy oborů názvů následují podle vzoru .NET sekvence jednoho nebo více přípustných symbolů oddělených tečkami `.`.</span><span class="sxs-lookup"><span data-stu-id="ed34e-115">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="ed34e-116">Například `MyQuantumStuff` a `Microsoft.Quantum.Canon` jsou platné názvy oborů názvů.</span><span class="sxs-lookup"><span data-stu-id="ed34e-116">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Canon` are valid namespace names.</span></span>
<span data-ttu-id="ed34e-117">Podle konvence jsou symboly v názvu oboru názvů velkými písmeny, ale to není vyžadováno.</span><span class="sxs-lookup"><span data-stu-id="ed34e-117">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="ed34e-118">Deklarace můžou být v libovolném pořadí v deklaraci oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="ed34e-118">Declarations may appear in any order in a namespace declaration.</span></span>
<span data-ttu-id="ed34e-119">Odkazy na typy nebo volat deklarované níže v souboru jsou správně vyřešeny. není nutné, aby deklarace typu, operace nebo funkce předcházely odkaz na ni.</span><span class="sxs-lookup"><span data-stu-id="ed34e-119">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="ed34e-120">Otevřít direktivy</span><span class="sxs-lookup"><span data-stu-id="ed34e-120">Open Directives</span></span>

<span data-ttu-id="ed34e-121">V rámci bloku oboru názvů lze použít direktivu `open` pro import všech typů a volání, která jsou definována v určitém oboru názvů a odkazují na ně podle jejich nekvalifikovaného názvu.</span><span class="sxs-lookup"><span data-stu-id="ed34e-121">Within a namespace block, the `open` directive may be used to import all types and callables defined in a certain namespace and refer to them by their unqualified name.</span></span> 

<span data-ttu-id="ed34e-122">Taková direktiva `open` sestává z klíčového slova `open` následovaným oborem názvů, který se má otevřít, a koncovým středníkem.</span><span class="sxs-lookup"><span data-stu-id="ed34e-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

<span data-ttu-id="ed34e-123">Například</span><span class="sxs-lookup"><span data-stu-id="ed34e-123">For instance,</span></span>

```qsharp
open Microsoft.Quantum.Canon;
```

<span data-ttu-id="ed34e-124">Volitelně může být definován krátký název pro otevřený obor názvů tak, aby všechny elementy z tohoto oboru názvů mohly (a musí) být kvalifikovány definovaným krátkým názvem.</span><span class="sxs-lookup"><span data-stu-id="ed34e-124">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="ed34e-125">Tento krátký název je definován přidáním klíčového slova `as` následovaný požadovaným krátkým názvem před středníkem v direktivě `open`:</span><span class="sxs-lookup"><span data-stu-id="ed34e-125">Such a short name is defined by adding the keyword `as` followed by the desired short name before the semicolon in an `open` directive:</span></span>

```qsharp
open Microsoft.Quantum.Math as Math;
```

<span data-ttu-id="ed34e-126">Všechny direktivy `open` musí být uvedeny před všemi deklaracemi `function`, `operation`nebo `newtype` v bloku Namespace.</span><span class="sxs-lookup"><span data-stu-id="ed34e-126">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>
<span data-ttu-id="ed34e-127">Direktiva `open` se vztahuje na celý blok oboru názvů v rámci souboru.</span><span class="sxs-lookup"><span data-stu-id="ed34e-127">The `open` directive applies to the entire namespace block within a file.</span></span>

## <a name="user-defined-type-declarations"></a><span data-ttu-id="ed34e-128">Deklarace uživatelem definovaných typů</span><span class="sxs-lookup"><span data-stu-id="ed34e-128">User-Defined Type Declarations</span></span>

<span data-ttu-id="ed34e-129">Q # poskytuje uživatelům způsob, jak deklarovat nové uživatelsky definované typy, jak je popsáno v části [model typu Q #](xref:microsoft.quantum.language.type-model) .</span><span class="sxs-lookup"><span data-stu-id="ed34e-129">Q# provides a way for users to declare new user-defined types, as described in the [Q# type model](xref:microsoft.quantum.language.type-model) section.</span></span>
<span data-ttu-id="ed34e-130">Uživatelsky definované typy jsou odlišné, i když základní typy jsou identické.</span><span class="sxs-lookup"><span data-stu-id="ed34e-130">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="ed34e-131">Konkrétně neexistuje žádný automatický převod mezi hodnotami dvou uživatelsky definovaných typů i v případě, že jsou základní typy identické.</span><span class="sxs-lookup"><span data-stu-id="ed34e-131">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

<span data-ttu-id="ed34e-132">Uživatelsky definovaná deklarace typu se skládá z klíčového slova `newtype`následovaný názvem uživatelsky definovaného typu, `=`, platné specifikace typu a ukončující středník.</span><span class="sxs-lookup"><span data-stu-id="ed34e-132">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="ed34e-133">Příklad:</span><span class="sxs-lookup"><span data-stu-id="ed34e-133">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="ed34e-134">Každý zdrojový soubor Q # může deklarovat libovolný počet uživatelsky definovaných typů.</span><span class="sxs-lookup"><span data-stu-id="ed34e-134">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="ed34e-135">Názvy typů musí být v rámci oboru názvů jedinečné a nemusí být v konfliktu s názvy operací a funkcí.</span><span class="sxs-lookup"><span data-stu-id="ed34e-135">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="ed34e-136">Mezi uživatelsky definovanými typy není možné definovat cyklické závislosti.</span><span class="sxs-lookup"><span data-stu-id="ed34e-136">It is not possible to define circular dependencies between user defined types.</span></span> <span data-ttu-id="ed34e-137">Rekurzivní typy nejsou proto možné v rámci Q #.</span><span class="sxs-lookup"><span data-stu-id="ed34e-137">Recursive types are thus not possible within Q#.</span></span>

## <a name="operation-declarations"></a><span data-ttu-id="ed34e-138">Deklarace operací</span><span class="sxs-lookup"><span data-stu-id="ed34e-138">Operation Declarations</span></span>

<span data-ttu-id="ed34e-139">Operace jsou základem Q #, zhruba podobným funkcím v jiných jazycích.</span><span class="sxs-lookup"><span data-stu-id="ed34e-139">Operations are the core of Q#, roughly analogous to functions in other languages.</span></span>
<span data-ttu-id="ed34e-140">Každý zdrojový soubor Q # může definovat libovolný počet operací.</span><span class="sxs-lookup"><span data-stu-id="ed34e-140">Each Q# source file may define any number of operations.</span></span>

<span data-ttu-id="ed34e-141">Názvy operací musí být v rámci oboru názvů jedinečné a nemusí být v konfliktu s názvy typu a funkce.</span><span class="sxs-lookup"><span data-stu-id="ed34e-141">Operation names must be unique within a namespace and may not conflict with type and function names.</span></span>

<span data-ttu-id="ed34e-142">Deklarace operací se skládají z klíčového slova `operation`následovaný symbolem, který představuje název operace, typ řazené kolekce členů definující argumenty operace, dvojtečku `:`, anotaci typu, která popisuje typ výsledku operace, volitelně poznámku s charakteristikou operace, levou složenou závorku `{`, tělo deklarace operace a Poslední uzavírací závorku `}`.</span><span class="sxs-lookup"><span data-stu-id="ed34e-142">An operation declarations consists of the keyword `operation`, followed by the symbol that is the operation’s name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation’s result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="ed34e-143">Tělo deklarace operace se skládá buď z výchozí implementace, nebo ze seznamu specializací.</span><span class="sxs-lookup"><span data-stu-id="ed34e-143">The body of the operation declaration either consists of the default implementation or of a list of specializations.</span></span>
<span data-ttu-id="ed34e-144">Výchozí implementaci lze zadat přímo v rámci deklarace, pokud je nutné explicitně zadat pouze implementaci výchozí specializace těla.</span><span class="sxs-lookup"><span data-stu-id="ed34e-144">The default implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to specified explicitly.</span></span>
<span data-ttu-id="ed34e-145">V tomto případě Poznámka s charakteristikou operace v deklaraci je užitečná pro zajištění, že kompilátor automaticky generuje jiné specializace na základě výchozí implementace.</span><span class="sxs-lookup"><span data-stu-id="ed34e-145">In this case, an annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="ed34e-146">Například</span><span class="sxs-lookup"><span data-stu-id="ed34e-146">For example</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

<span data-ttu-id="ed34e-147">Charakteristiky operace definují, jaké druhy funktory lze použít pro deklarovanou operaci a jaký má vliv.</span><span class="sxs-lookup"><span data-stu-id="ed34e-147">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="ed34e-148">Pokud operace implementuje jednotnou transformaci, je možné definovat způsob, jakým operace funguje při *adjointed* nebo *řízených*.</span><span class="sxs-lookup"><span data-stu-id="ed34e-148">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span>
<span data-ttu-id="ed34e-149">Existence těchto specializací se dá deklarovat jako součást signatury operace.</span><span class="sxs-lookup"><span data-stu-id="ed34e-149">The existence of these specializations can be declared as part of the operation signature.</span></span> <span data-ttu-id="ed34e-150">Odpovídající implementace pro každou takovou implicitně deklarovanou specializaci je následně vygenerována kompilátorem.</span><span class="sxs-lookup"><span data-stu-id="ed34e-150">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> <span data-ttu-id="ed34e-151">V předchozím příkladu jsou v kompilátoru generovány sousední a řízené specializace.</span><span class="sxs-lookup"><span data-stu-id="ed34e-151">In the example above, an adjoint, a controlled, and a controlled adjoint specialization are generated by the compiler.</span></span> 

<span data-ttu-id="ed34e-152">V případě, že se implementace nemůže generovat kompilátorem, je možné ji explicitně zadat.</span><span class="sxs-lookup"><span data-stu-id="ed34e-152">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="ed34e-153">Tyto explicitní deklarace specializace mohou být buď tvořeny vhodnou direktivou generace, která vysvětluje, jak je konkrétní specializace sestavena, nebo uživatelem definovaná implementace.</span><span class="sxs-lookup"><span data-stu-id="ed34e-153">Such explicit specialization declarations can either consist of a suitable generation directive that clarify how a certain specialization is to be built, or a user defined implementation.</span></span> <span data-ttu-id="ed34e-154">Kód v `PrepareEntangledPair` výše je například ekvivalentní následujícímu kódu, který obsahuje explicitní deklarace specializace:</span><span class="sxs-lookup"><span data-stu-id="ed34e-154">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

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
<span data-ttu-id="ed34e-155">Klíčové slovo `auto` označuje, že kompilátor by měl určit, jak se má vygenerovat implementace specializace.</span><span class="sxs-lookup"><span data-stu-id="ed34e-155">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="ed34e-156">Pokud kompilátor nemůže vygenerovat implementaci pro určitou specializaci bez dalších pokynů, jako je přesnější direktiva generace, nebo pokud je možné zadat účinnější implementaci, pak může být implementace také ručně definovaná.</span><span class="sxs-lookup"><span data-stu-id="ed34e-156">If the compiler cannot generate the implementation for a certain specialization without further instructions - like a more precise generation directive -, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

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

<span data-ttu-id="ed34e-157">Ve výše uvedeném příkladu `adjoint invert;` označuje, že specializace sousedící-by měla být vygenerována vrácením implementace těla a `controlled adjoint invert;` označuje, že řízená specializace, která je řízena, je vygenerována obrácením dané implementace řízené specializace.</span><span class="sxs-lookup"><span data-stu-id="ed34e-157">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="ed34e-158">Aby operace podporovala použití `Adjoint` a/nebo `Controlled` funktor, musí být jeho návratový typ nutně `Unit`.</span><span class="sxs-lookup"><span data-stu-id="ed34e-158">For an operation to support application of the `Adjoint` and/or `Controlled` functor, its return type necessarily needs to be `Unit`.</span></span> 


### <a name="explicit-specialization-declarations"></a><span data-ttu-id="ed34e-159">Explicitní deklarace specializace</span><span class="sxs-lookup"><span data-stu-id="ed34e-159">Explicit Specialization Declarations</span></span>

<span data-ttu-id="ed34e-160">Operace Q # můžou obsahovat následující explicitní deklarace specializace:</span><span class="sxs-lookup"><span data-stu-id="ed34e-160">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="ed34e-161">Specializace `body` určuje implementaci operace bez použití funktory.</span><span class="sxs-lookup"><span data-stu-id="ed34e-161">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="ed34e-162">Specializace `adjoint` určuje implementaci operace s aplikovaným `Adjoint` funktor.</span><span class="sxs-lookup"><span data-stu-id="ed34e-162">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="ed34e-163">Specializace `controlled` určuje implementaci operace s aplikovaným `Controlled` funktor.</span><span class="sxs-lookup"><span data-stu-id="ed34e-163">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="ed34e-164">Specializace `controlled adjoint` určuje implementaci operace s použitým `Adjoint`m i `Controlled`m funktory.</span><span class="sxs-lookup"><span data-stu-id="ed34e-164">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="ed34e-165">Tato specializace může mít také název `adjoint controlled`, protože dvě dojíždění do funktory.</span><span class="sxs-lookup"><span data-stu-id="ed34e-165">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="ed34e-166">Specializace operace se skládá z tagu specializace (například `body`nebo `adjoint`atd.) následovaný jedním z těchto:</span><span class="sxs-lookup"><span data-stu-id="ed34e-166">An operation specialization consists of the specialization tag (like e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="ed34e-167">Explicitní deklarace, jak je popsáno níže.</span><span class="sxs-lookup"><span data-stu-id="ed34e-167">An explicit declaration as described below.</span></span>
- <span data-ttu-id="ed34e-168">Direktiva, která instruuje kompilátor, jak vygenerovat specializaci, jedna z těchto:</span><span class="sxs-lookup"><span data-stu-id="ed34e-168">A directive that tells the compiler how to generate the specialization, one of:</span></span>
  - <span data-ttu-id="ed34e-169">`intrinsic`, která označuje, že specializace je poskytována cílovým počítačem.</span><span class="sxs-lookup"><span data-stu-id="ed34e-169">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="ed34e-170">`distribute`, které lze použít s specializacemi `controlled` a `controlled adjoint`.</span><span class="sxs-lookup"><span data-stu-id="ed34e-170">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="ed34e-171">Při použití s `controlled`označuje, že má kompilátor vypočítat specializaci použitím `Controlled` na všechny operace v `body`.</span><span class="sxs-lookup"><span data-stu-id="ed34e-171">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="ed34e-172">Při použití s `controlled adjoint`označuje, že má kompilátor vypočítat specializaci použitím `Controlled` na všechny operace v rámci `adjoint` specializace.</span><span class="sxs-lookup"><span data-stu-id="ed34e-172">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="ed34e-173">`invert`, která označuje, že má kompilátor vypočítat `adjoint` specializaci, vrácením `body`, tj. zrušením pořadí operací a aplikováním sousedících na každý.</span><span class="sxs-lookup"><span data-stu-id="ed34e-173">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="ed34e-174">Při použití s `adjoint controlled`to znamená, že kompilátor má vypočítat specializaci vrácením `controlled` specializace.</span><span class="sxs-lookup"><span data-stu-id="ed34e-174">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="ed34e-175">`self`pro indikaci, že specializace přiléhajícího je stejná jako `body` specializace.</span><span class="sxs-lookup"><span data-stu-id="ed34e-175">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="ed34e-176">To je platné pro `adjoint` a `adjoint controlled` specializace.</span><span class="sxs-lookup"><span data-stu-id="ed34e-176">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="ed34e-177">Pro `adjoint controlled``self` znamená, že specializace `adjoint controlled` je stejná jako `controlled` specializace.</span><span class="sxs-lookup"><span data-stu-id="ed34e-177">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="ed34e-178">`auto`, aby označoval, že má kompilátor vybrat vhodnou direktivu, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="ed34e-178">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="ed34e-179">`auto` se nedá použít pro specializaci `body`.</span><span class="sxs-lookup"><span data-stu-id="ed34e-179">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="ed34e-180">Direktivy a `auto` všechny vyžadují uzavírání středníkem `;`.</span><span class="sxs-lookup"><span data-stu-id="ed34e-180">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="ed34e-181">Direktiva `auto` překládá na následující direktivu generace, pokud je k dispozici explicitní deklarace `body`:</span><span class="sxs-lookup"><span data-stu-id="ed34e-181">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="ed34e-182">Specializace `adjoint` je vygenerována podle direktivy `invert`.</span><span class="sxs-lookup"><span data-stu-id="ed34e-182">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="ed34e-183">Specializace `controlled` je vygenerována podle direktivy `distribute`.</span><span class="sxs-lookup"><span data-stu-id="ed34e-183">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="ed34e-184">Specializace `adjoint controlled` je vygenerována podle direktivy `invert`, pokud je zadána explicitní deklarace pro `controlled`, ale ne jednu pro `adjoint`a `distribute` jinak.</span><span class="sxs-lookup"><span data-stu-id="ed34e-184">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="ed34e-185">Pokud je operace samostatně sousedící, explicitně určete buď sousední, nebo řízená sousední specializace, pomocí direktivy generace `self`, aby kompilátor mohl používat tyto informace pro účely optimalizace.</span><span class="sxs-lookup"><span data-stu-id="ed34e-185">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="ed34e-186">Deklarace specializace obsahující uživatelsky definovanou implementaci se skládá z argumentů řazené kolekce členů následovaný blokem příkazu Q #, který implementuje specializaci.</span><span class="sxs-lookup"><span data-stu-id="ed34e-186">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="ed34e-187">V seznamu argumentů se `...` slouží k reprezentaci argumentů deklarovaných pro operaci jako celku.</span><span class="sxs-lookup"><span data-stu-id="ed34e-187">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="ed34e-188">Pro `body` a `adjoint`by měl být seznam argumentů vždy `(...)`; v případě `controlled` a `adjoint controlled`by měl být seznam argumentů symbolem, který představuje pole ovládacího prvku qubits, po kterém následuje `...`, uzavřené v závorkách. například `(controls,...)`.</span><span class="sxs-lookup"><span data-stu-id="ed34e-188">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

<span data-ttu-id="ed34e-189">Pokud je nutné explicitně deklarovat jednu nebo více specializací, než je výchozí tělo, musí být implementace pro výchozí tělo zabalena do vhodné deklarace specializace:</span><span class="sxs-lookup"><span data-stu-id="ed34e-189">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

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

### <a name="adjoint"></a><span data-ttu-id="ed34e-190">Sousednít</span><span class="sxs-lookup"><span data-stu-id="ed34e-190">Adjoint</span></span>

<span data-ttu-id="ed34e-191">Sousední operace v operaci určuje, jak je implementace komplexní sdružené operace implementována, tj. způsob, jakým operace funguje v opačném případě.</span><span class="sxs-lookup"><span data-stu-id="ed34e-191">The adjoint of an operation specifies how the complex conjugate transpose of the operation is implemented, i.e. how the operation acts when "run in reverse".</span></span>
<span data-ttu-id="ed34e-192">Je právní určení operace bez souseda; například operace měření nemají žádný sousední, protože nejsou inverzi.</span><span class="sxs-lookup"><span data-stu-id="ed34e-192">It is legal to specify an operation with no adjoint; for instance, measurement operations have no adjoint because they are not invertible.</span></span>
<span data-ttu-id="ed34e-193">Operace podporuje `Adjoint` funktor, pokud jeho deklarace obsahuje implicitní nebo explicitní deklaraci sousední specializace.</span><span class="sxs-lookup"><span data-stu-id="ed34e-193">An operation supports the `Adjoint` functor if its declaration contains an implicit or explicit declaration of an adjoint specialization.</span></span>
<span data-ttu-id="ed34e-194">Explicitně deklarovaná řízená specializace typu předpokládá existenci sousedící specializace.</span><span class="sxs-lookup"><span data-stu-id="ed34e-194">An explicitly declared controlled adjoint specialization implies the existence of an adjoint specialization.</span></span> 

<span data-ttu-id="ed34e-195">Pro operaci, jejíž tělo obsahuje smyčky Repeat-do-úspěch, nastavte příkazy, měření, příkazy Return nebo volání jiných operací, které nepodporují `Adjoint` funktor, automatické generování sousední specializace ' po `invert` nebo `auto` direktivy není možné.</span><span class="sxs-lookup"><span data-stu-id="ed34e-195">For operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

### <a name="controlled"></a><span data-ttu-id="ed34e-196">Kontrol</span><span class="sxs-lookup"><span data-stu-id="ed34e-196">Controlled</span></span>

<span data-ttu-id="ed34e-197">Řízená verze operace určuje, jak je verze operace řízená procesorem, tj. to, jak operace funguje, když se aplikuje v podmínkách pro stav registru.</span><span class="sxs-lookup"><span data-stu-id="ed34e-197">The controlled version of an operation specifies how a quantum-controlled version of the operation is implemented, i.e. how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="ed34e-198">V části [řízená](xref:microsoft.quantum.language.type-model#controlled) je uveden Úplnější popis.</span><span class="sxs-lookup"><span data-stu-id="ed34e-198">A more complete description is provided in the [Controlled](xref:microsoft.quantum.language.type-model#controlled) section.</span></span>

<span data-ttu-id="ed34e-199">Je právní určení operace bez řízené verze; například operace měření nemají žádnou řízenou verzi, protože nejsou ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="ed34e-199">It is legal to specify an operation with no controlled version; for instance, measurement operations have no controlled version because they are not controllable.</span></span>
<span data-ttu-id="ed34e-200">Operace podporuje `Controlled` funktor pouze v případě, že deklarace obsahuje implicitní nebo explicitní deklaraci řízené specializace.</span><span class="sxs-lookup"><span data-stu-id="ed34e-200">An operation supports the `Controlled` functor if and only if its declaration contains an implicit or explicit declaration of a controlled specialization.</span></span>
<span data-ttu-id="ed34e-201">Explicitně deklarovaná řízená specializace typu předpokládá existenci řízené specializace.</span><span class="sxs-lookup"><span data-stu-id="ed34e-201">An explicitly declared controlled adjoint specialization implies the existence of a controlled specialization.</span></span> 

<span data-ttu-id="ed34e-202">Pro operaci, jejíž tělo obsahuje volání do jiných operací, které nepodporují `Controlled` funktor, automatické generování řízené specializace následující po `distribute` nebo `auto` direktivy není možné.</span><span class="sxs-lookup"><span data-stu-id="ed34e-202">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

### <a name="controlled-adjoint"></a><span data-ttu-id="ed34e-203">Řízený sousedící</span><span class="sxs-lookup"><span data-stu-id="ed34e-203">Controlled Adjoint</span></span>

<span data-ttu-id="ed34e-204">Řízená verze inřízených operací operace určuje, jak je implementována verze sousedících operací s řízenou počátečními událostmi.</span><span class="sxs-lookup"><span data-stu-id="ed34e-204">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="ed34e-205">Je právní určení operace bez řízené sousední verze; například operace měření nemají řízenou sousední verzi, protože nejsou ani ovladatelné ani inverzi.</span><span class="sxs-lookup"><span data-stu-id="ed34e-205">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="ed34e-206">Řízená sousední specializace pro operaci musí existovat, pokud je a jenom v případě, že existují sousední i řízená specializace.</span><span class="sxs-lookup"><span data-stu-id="ed34e-206">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="ed34e-207">V takovém případě je existence řízené specializace instalovaná a příslušná specializace je vygenerována kompilátorem, pokud nebyla explicitně definována žádná implementace.</span><span class="sxs-lookup"><span data-stu-id="ed34e-207">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="ed34e-208">Pro operaci, jejíž tělo obsahuje volání na jiné operace, které nemají řízenou sousední verzi, automatické generování sousední specializace typu, která následuje po `invert`, `distribute` nebo `auto` direktiva není možná.</span><span class="sxs-lookup"><span data-stu-id="ed34e-208">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="examples"></a><span data-ttu-id="ed34e-209">Příklady</span><span class="sxs-lookup"><span data-stu-id="ed34e-209">Examples</span></span>

<span data-ttu-id="ed34e-210">Deklarace operace může být jednoduchá, jak je uvedeno níže, což definuje primitivní operaci Pauli X:</span><span class="sxs-lookup"><span data-stu-id="ed34e-210">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

<span data-ttu-id="ed34e-211">Následující definuje operaci teleport.</span><span class="sxs-lookup"><span data-stu-id="ed34e-211">The following defines the teleport operation.</span></span>

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation EPR (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        EPR(target, ancilla);

        // Do the teleportation
        Adjoint EPR (ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a><span data-ttu-id="ed34e-212">Deklarace funkcí</span><span class="sxs-lookup"><span data-stu-id="ed34e-212">Function Declarations</span></span>

<span data-ttu-id="ed34e-213">Funkce jsou čistě klasickými rutinami v Q #.</span><span class="sxs-lookup"><span data-stu-id="ed34e-213">Functions are purely classical routines in Q#.</span></span>
<span data-ttu-id="ed34e-214">Každý zdrojový soubor Q # může definovat libovolný počet funkcí.</span><span class="sxs-lookup"><span data-stu-id="ed34e-214">Each Q# source file may define any number of functions.</span></span>

<span data-ttu-id="ed34e-215">Deklarace funkce se skládá z klíčového slova `function`následovaný symbolem, který je název funkce, typ řazené kolekce členů, anotace typu, která popisuje návratový typ funkce, a blok příkazu, který popisuje implementaci funkce.</span><span class="sxs-lookup"><span data-stu-id="ed34e-215">A function declaration consists of the keyword `function`, followed by the symbol that is the function’s name, a typed identifier tuple, a type annotation that describes the function's return type, and a statement block that describes the implementation of the function.</span></span>

<span data-ttu-id="ed34e-216">Blok příkazů definující funkci musí být uzavřený v `{` a `}` jako jakýkoli jiný blok příkazů.</span><span class="sxs-lookup"><span data-stu-id="ed34e-216">The statement block defining a function must be enclosed in `{` and `}` like any other statement block.</span></span>

<span data-ttu-id="ed34e-217">Názvy funkcí musí být jedinečné v rámci oboru názvů a nemusí být v konfliktu s názvy operací a typů.</span><span class="sxs-lookup"><span data-stu-id="ed34e-217">Function names must be unique within a namespace and may not conflict with operation and type names.</span></span>
<span data-ttu-id="ed34e-218">Funkce nemusí přidělovat ani půjčovat qubits nebo volat operace.</span><span class="sxs-lookup"><span data-stu-id="ed34e-218">Functions may not allocate or borrow qubits, or call operations.</span></span> <span data-ttu-id="ed34e-219">Částečné použití operací nebo předávání hodnot typu operace je přesné.</span><span class="sxs-lookup"><span data-stu-id="ed34e-219">Partial application of operations or passing around operation typed values is fine.</span></span>

<span data-ttu-id="ed34e-220">Například:</span><span class="sxs-lookup"><span data-stu-id="ed34e-220">For example,</span></span>

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
