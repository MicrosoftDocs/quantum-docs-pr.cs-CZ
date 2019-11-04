---
title: 'Průvodce stylem Q # | Microsoft Docs'
description: 'Průvodce stylem Q #'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: 56455e9d5cd452b8620ee794f40563d1d3040193
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183841"
---
# <a name="q-style-guide"></a><span data-ttu-id="26b1d-103">Průvodce stylem Q #</span><span class="sxs-lookup"><span data-stu-id="26b1d-103">Q# Style Guide</span></span> #
## <a name="general-conventions"></a><span data-ttu-id="26b1d-104">Obecné konvence</span><span class="sxs-lookup"><span data-stu-id="26b1d-104">General Conventions</span></span> ##

<span data-ttu-id="26b1d-105">Konvence navržené v této příručce jsou určené k tomu, aby usnadnily čtení a pochopení programů a knihoven ve službě Q #.</span><span class="sxs-lookup"><span data-stu-id="26b1d-105">The conventions suggested in this guide are intended to help make programs and libraries written in Q# easier to read and understand.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="26b1d-106">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="26b1d-106">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="26b1d-107">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="26b1d-107">We suggest:</span></span>

- <span data-ttu-id="26b1d-108">Nikdy nepoužívejte konvenci, pokud to neprovedete záměrně za účelem poskytnutí čitelnějšího a srozumitelného kódu pro uživatele.</span><span class="sxs-lookup"><span data-stu-id="26b1d-108">Never disregard a convention unless you’re doing so intentionally in order to provide more readable and understandable code for your users.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="26b1d-109">Příklady</span><span class="sxs-lookup"><span data-stu-id="26b1d-109">Examples</span></span>](#tab/examples)

***

## <a name="naming-conventions"></a><span data-ttu-id="26b1d-110">Zásady vytváření názvů</span><span class="sxs-lookup"><span data-stu-id="26b1d-110">Naming Conventions</span></span> ##

<span data-ttu-id="26b1d-111">V rámci nabídky vývojové sady pro práci s více operačními společnostmi usilujeme o názvy funkcí a operací, které vývojářům usnadňují psaní programů, které se snadno čtou a které minimalizují neočekávaně.</span><span class="sxs-lookup"><span data-stu-id="26b1d-111">In offering the Quantum Development Kit, we strive for function and operation names that help quantum developers write programs that are easy to read and that minimize surprise.</span></span>
<span data-ttu-id="26b1d-112">Důležitou součástí toho je, že když vybíráme názvy pro funkce, operace a typy, vytvoříme *slovník* , který programátoři používají pro vyjádření základních konceptů. Díky našim možnostem vám pomůžeme nebo je bráníme v jejich úsilí, aby mohli jasně komunikovat.</span><span class="sxs-lookup"><span data-stu-id="26b1d-112">An important part of that is that when we choose names for functions, operations, and types, we are establishing the *vocabulary* that programmers use to express quantum concepts; with our choices, we either help or hinder them in their effort to clearly communicate.</span></span>
<span data-ttu-id="26b1d-113">Tím se na nás zaručí zodpovědnost, aby se zajistilo, že názvy, které zavádíme, představují srozumitelnější místo neprůhlednosti.</span><span class="sxs-lookup"><span data-stu-id="26b1d-113">This places a responsibility on us to make sure that the names we introduce offer clarity rather than obscurity.</span></span>
<span data-ttu-id="26b1d-114">V této části podrobně uvádíme, jak splňujeme tuto povinnost z hlediska explicitních pokynů, abychom nám mohli co nejlépe udělat komunitou pro vývoj Q.</span><span class="sxs-lookup"><span data-stu-id="26b1d-114">In this section, we detail how we meet this obligation in terms of explicit guidance that helps us do the best by the Q# development community.</span></span>

### <a name="operations-and-functions"></a><span data-ttu-id="26b1d-115">Operace a funkce</span><span class="sxs-lookup"><span data-stu-id="26b1d-115">Operations and Functions</span></span> ###

<span data-ttu-id="26b1d-116">Jedna z prvních věcí, které by měl název vytvořit, je, zda daný symbol představuje funkci nebo operaci.</span><span class="sxs-lookup"><span data-stu-id="26b1d-116">One of the first things that a name should establish is whether a given symbol represents a function or an operation.</span></span>
<span data-ttu-id="26b1d-117">Rozdíl mezi funkcemi a operacemi je zásadní pro porozumění způsobu, jakým se chová blok kódu.</span><span class="sxs-lookup"><span data-stu-id="26b1d-117">The difference between functions and operations is critical to understanding how a block of code behaves.</span></span>
<span data-ttu-id="26b1d-118">Pro sdělování rozdílů mezi funkcemi a operacemi pro uživatele spoléháme na to, že modely Q # využívají vedlejší účinky na tyto operace.</span><span class="sxs-lookup"><span data-stu-id="26b1d-118">To communicate the distinction between functions and operations to users, we rely on that Q# models quantum operations through the use of side effects.</span></span>
<span data-ttu-id="26b1d-119">To znamená, že operace *dělá* něco.</span><span class="sxs-lookup"><span data-stu-id="26b1d-119">That is, an operation *does* something.</span></span>

<span data-ttu-id="26b1d-120">Naopak funkce popisují matematické vztahy mezi daty.</span><span class="sxs-lookup"><span data-stu-id="26b1d-120">By contrast, functions describe the mathematical relationships between data.</span></span>
<span data-ttu-id="26b1d-121">Výraz `Sin(PI() / 2.0)` *je* `1.0`a nevyjadřuje žádné informace o stavu programu nebo jeho qubits.</span><span class="sxs-lookup"><span data-stu-id="26b1d-121">The expression `Sin(PI() / 2.0)` *is* `1.0`, and implies nothing about the state of a program or its qubits.</span></span>

<span data-ttu-id="26b1d-122">Sumarizace, operace se provádí v době, kdy jsou funkce věcí.</span><span class="sxs-lookup"><span data-stu-id="26b1d-122">Summarizing, operations do things while functions are things.</span></span>
<span data-ttu-id="26b1d-123">Tento rozdíl naznačuje, že pojmenování operací jako operací a funkcí jako podstatných jmen.</span><span class="sxs-lookup"><span data-stu-id="26b1d-123">This distinction suggests that we name operations as verbs and functions as nouns.</span></span>

> [!NOTE]
> <span data-ttu-id="26b1d-124">Když je deklarován uživatelsky definovaný typ, je nová funkce, která vytváří instance daného typu, implicitně definována současně.</span><span class="sxs-lookup"><span data-stu-id="26b1d-124">When a user-defined type is declared, a new function that constructs instances of that type is implicitly defined at the same time.</span></span>
> <span data-ttu-id="26b1d-125">Z této perspektivy by měly být uživatelsky definované typy pojmenovány jako podstatná jména, aby samotný typ i funkce konstruktoru měly konzistentní názvy.</span><span class="sxs-lookup"><span data-stu-id="26b1d-125">From that perspective, user-defined types should be named as nouns so that both the type itself and the constructor function have consistent names.</span></span>

<span data-ttu-id="26b1d-126">Tam, kde je to rozumné, zajistěte, aby názvy operací začaly slovesy, které jasně indikují účinek prováděný operací.</span><span class="sxs-lookup"><span data-stu-id="26b1d-126">Where reasonable, ensure that operation names begin with verbs that clearly indicate the effect taken by the operation.</span></span>
<span data-ttu-id="26b1d-127">Například:</span><span class="sxs-lookup"><span data-stu-id="26b1d-127">For example:</span></span>

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

<span data-ttu-id="26b1d-128">Jeden případ, který zachovává zvláštní zmínku, je v případě, že operace přebírá jinou operaci jako vstup a volá ji.</span><span class="sxs-lookup"><span data-stu-id="26b1d-128">One case that deserves special mention is when an operation takes another operation as input and calls it.</span></span>
<span data-ttu-id="26b1d-129">V takových případech není akce prováděná vstupní operací jasná, když je definovaná vnější operace, takže není správná operace okamžitě jasná.</span><span class="sxs-lookup"><span data-stu-id="26b1d-129">In such cases, the action taken by the input operation is not clear when the outer operation is defined, such that the right verb is not immediately clear.</span></span>
<span data-ttu-id="26b1d-130">Jako v `ApplyIf`, `ApplyToEach`a `ApplyToFirst`doporučujeme použít příkaz `Apply`.</span><span class="sxs-lookup"><span data-stu-id="26b1d-130">We recommend the verb `Apply`, as in `ApplyIf`, `ApplyToEach`, and `ApplyToFirst`.</span></span>
<span data-ttu-id="26b1d-131">V tomto případě mohou být užitečné i jiné akce, jako v `IterateThroughCartesianPower`.</span><span class="sxs-lookup"><span data-stu-id="26b1d-131">Other verbs may be useful in this case as well, as in `IterateThroughCartesianPower`.</span></span>

| <span data-ttu-id="26b1d-132">Operace</span><span class="sxs-lookup"><span data-stu-id="26b1d-132">Verb</span></span> | <span data-ttu-id="26b1d-133">Očekávaný efekt</span><span class="sxs-lookup"><span data-stu-id="26b1d-133">Expected Effect</span></span> |
| ---- | ------ |
| <span data-ttu-id="26b1d-134">Použít</span><span class="sxs-lookup"><span data-stu-id="26b1d-134">Apply</span></span> | <span data-ttu-id="26b1d-135">Nazývá se operace zadaná jako vstup.</span><span class="sxs-lookup"><span data-stu-id="26b1d-135">An operation provided as input is called</span></span> |
| <span data-ttu-id="26b1d-136">Uplatňuje</span><span class="sxs-lookup"><span data-stu-id="26b1d-136">Assert</span></span> | <span data-ttu-id="26b1d-137">Hypotéza o výsledku možného měření doby využívání se kontroluje simulátorem.</span><span class="sxs-lookup"><span data-stu-id="26b1d-137">A hypothesis about the outcome of a possible quantum measurement is checked by a simulator</span></span> |
| <span data-ttu-id="26b1d-138">Ocenění</span><span class="sxs-lookup"><span data-stu-id="26b1d-138">Estimate</span></span> | <span data-ttu-id="26b1d-139">Vrátí se klasická hodnota, která představuje odhad vykreslený z jedné nebo více měření.</span><span class="sxs-lookup"><span data-stu-id="26b1d-139">A classical value is returned, representing an estimate drawn from one or more measurements</span></span> |
| <span data-ttu-id="26b1d-140">Měrné</span><span class="sxs-lookup"><span data-stu-id="26b1d-140">Measure</span></span> | <span data-ttu-id="26b1d-141">Měří se měření po sobě a výsledek se vrátí uživateli.</span><span class="sxs-lookup"><span data-stu-id="26b1d-141">A quantum measurement is performed, and its result is returned to the user</span></span> |
| <span data-ttu-id="26b1d-142">Připravit</span><span class="sxs-lookup"><span data-stu-id="26b1d-142">Prepare</span></span> | <span data-ttu-id="26b1d-143">Daný registr qubits se inicializuje do určitého stavu.</span><span class="sxs-lookup"><span data-stu-id="26b1d-143">A given register of qubits is initialized into a particular state</span></span> |
| <span data-ttu-id="26b1d-144">Ukázka</span><span class="sxs-lookup"><span data-stu-id="26b1d-144">Sample</span></span> | <span data-ttu-id="26b1d-145">Z nějaké distribuce se náhodně vrátí klasická hodnota.</span><span class="sxs-lookup"><span data-stu-id="26b1d-145">A classical value is returned at random from some distribution</span></span> |

<span data-ttu-id="26b1d-146">V případě funkcí doporučujeme vyhnout se použití sloves ve prospěch běžných podstatných jmen (viz doprovodné materiály o řádných podstatných jmenách níže) nebo adjektiva:</span><span class="sxs-lookup"><span data-stu-id="26b1d-146">For functions, we suggest avoiding the use of verbs in favor of common nouns (see guidance on proper nouns below) or adjectives:</span></span>

- `ConstantArray`
- `Head`
- `LookupFunction`

<span data-ttu-id="26b1d-147">Konkrétně v téměř všech případech doporučujeme použít dřívější participles, kde je to vhodné k označení toho, že název funkce je důrazně připojen k akci nebo vedlejšímu účinku jinde v programu pro práci s více událostmi.</span><span class="sxs-lookup"><span data-stu-id="26b1d-147">In particular, in almost all cases, we suggest using past participles where appropriate to indicate that a function name is strongly connected to an action or side effect elsewhere in a quantum program.</span></span>
<span data-ttu-id="26b1d-148">Například `ControlledOnInt` používá participle formuláře příkazu "Control" k označení toho, že funkce funguje jako adjektivum pro úpravu svého argumentu.</span><span class="sxs-lookup"><span data-stu-id="26b1d-148">For example,  `ControlledOnInt` uses the part participle form of the verb "control" to indicate that the function acts as an adjective to modify its argument.</span></span>
<span data-ttu-id="26b1d-149">Tento název má další výhody, které odpovídají sémantikě předdefinovaných `Controlled` funktor, jak je popsáno dále níže.</span><span class="sxs-lookup"><span data-stu-id="26b1d-149">This name has the additional benefit of matching the semantics of the built-in `Controlled` functor, as discussed further below.</span></span>
<span data-ttu-id="26b1d-150">Obdobně lze použít _substantivum agenta_ k vytvoření funkce a názvů UDT z názvů operací, jako v případě názvu `Encoder` pro UDT, který je silně spojen s `Encode`.</span><span class="sxs-lookup"><span data-stu-id="26b1d-150">Similarly, _agent nouns_ can be used to construct function and UDT names from operation names, as in the case of the name `Encoder` for a UDT that is strongly associated with `Encode`.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="26b1d-151">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="26b1d-151">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="26b1d-152">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="26b1d-152">We suggest:</span></span>

- <span data-ttu-id="26b1d-153">Pro názvy operací použijte slovesa.</span><span class="sxs-lookup"><span data-stu-id="26b1d-153">Use verbs for operation names.</span></span>
- <span data-ttu-id="26b1d-154">Pro názvy funkcí použijte podstatná jména nebo jména.</span><span class="sxs-lookup"><span data-stu-id="26b1d-154">Use nouns or adjectives for function names.</span></span>
- <span data-ttu-id="26b1d-155">Používejte podstatná jména pro uživatelsky definované typy a atributy.</span><span class="sxs-lookup"><span data-stu-id="26b1d-155">Use nouns for user-defined types and attributes.</span></span>
- <span data-ttu-id="26b1d-156">Pro všechny názvy, které lze volat, použijte `CamelCase` ve silném předvolbách na `pascalCase`, `snake_case`nebo `ANGRY_CASE`.</span><span class="sxs-lookup"><span data-stu-id="26b1d-156">For all callable names, use `CamelCase` in strong preference to `pascalCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="26b1d-157">Konkrétně se ujistěte, že názvy, které se budou volat, začínají velkým písmenem.</span><span class="sxs-lookup"><span data-stu-id="26b1d-157">In particular, ensure that callable names start with uppercase letters.</span></span>
- <span data-ttu-id="26b1d-158">U všech místních proměnných použijte `pascalCase` v případě silné Předvolby na `CamelCase`, `snake_case`nebo `ANGRY_CASE`.</span><span class="sxs-lookup"><span data-stu-id="26b1d-158">For all local variables, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="26b1d-159">Konkrétně zajistěte, aby místní proměnné byly začínat malými písmeny.</span><span class="sxs-lookup"><span data-stu-id="26b1d-159">In particular, ensure that local variables start with lowercase letters.</span></span>
- <span data-ttu-id="26b1d-160">Vyhněte se použití podtržítek `_` v názvech funkcí a operací; v případě potřeby dalších úrovní hierarchie použijte obory názvů a aliasy oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="26b1d-160">Avoid the use of underscores `_` in function and operation names; where additional levels of hierarchy are needed, use namespaces and namespace aliases.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="26b1d-161">Příklady</span><span class="sxs-lookup"><span data-stu-id="26b1d-161">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="26b1d-162">Name (Název)</span><span class="sxs-lookup"><span data-stu-id="26b1d-162">Name</span></span> | <span data-ttu-id="26b1d-163">Popis</span><span class="sxs-lookup"><span data-stu-id="26b1d-163">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="26b1d-164">☑</span><span class="sxs-lookup"><span data-stu-id="26b1d-164">☑</span></span> | `operation ReflectAboutStart` | <span data-ttu-id="26b1d-165">Zrušením použití příkazu ("reflektování") označíte účinek operace.</span><span class="sxs-lookup"><span data-stu-id="26b1d-165">Clear use of a verb ("reflect") to indicate the effect of the operation.</span></span> |
| <span data-ttu-id="26b1d-166">☒</span><span class="sxs-lookup"><span data-stu-id="26b1d-166">☒</span></span> | <s>`operation XRotation`</s> | <span data-ttu-id="26b1d-167">Místo operace použijte funkci navrhuje fráze substantivum.</span><span class="sxs-lookup"><span data-stu-id="26b1d-167">Use of noun phrase suggests function, rather than operation.</span></span> |
| <span data-ttu-id="26b1d-168">☒</span><span class="sxs-lookup"><span data-stu-id="26b1d-168">☒</span></span> | <s>`operation search_oracle`</s> | <span data-ttu-id="26b1d-169">Použití `snake_case` je v rozporu s zápisem Q #.</span><span class="sxs-lookup"><span data-stu-id="26b1d-169">Use of `snake_case` contravenes Q# notation.</span></span> |
| <span data-ttu-id="26b1d-170">☒</span><span class="sxs-lookup"><span data-stu-id="26b1d-170">☒</span></span> | <s>`operation Search_Oracle`</s> | <span data-ttu-id="26b1d-171">Použití podtržítek s podtržítkem pro název operace je v rozporu s zápisem Q #.</span><span class="sxs-lookup"><span data-stu-id="26b1d-171">Use of underscores internal to operation name contravenes Q# notation.</span></span> |
| <span data-ttu-id="26b1d-172">☑</span><span class="sxs-lookup"><span data-stu-id="26b1d-172">☑</span></span> | `function StatePreparationOracle` | <span data-ttu-id="26b1d-173">Použití fráze substantivum naznačuje, že funkce vrátí operaci.</span><span class="sxs-lookup"><span data-stu-id="26b1d-173">Use of noun phrase suggests that the function returns an operation.</span></span> |
| <span data-ttu-id="26b1d-174">☑</span><span class="sxs-lookup"><span data-stu-id="26b1d-174">☑</span></span> | `function EqualityFact` | <span data-ttu-id="26b1d-175">Zrušte použití podstatného jména ("fakt"), abyste označili, že se jedná o funkci, ale jeho jméno.</span><span class="sxs-lookup"><span data-stu-id="26b1d-175">Clear use of noun ("fact") to indicate that this is a function, while the adjective.</span></span> |
| <span data-ttu-id="26b1d-176">☒</span><span class="sxs-lookup"><span data-stu-id="26b1d-176">☒</span></span> | <s>`function GetRotationAngles`</s> | <span data-ttu-id="26b1d-177">Použití příkazu ("Get") naznačuje, že se jedná o operaci.</span><span class="sxs-lookup"><span data-stu-id="26b1d-177">Use of verb ("get") suggests that this is an operation.</span></span> |
| <span data-ttu-id="26b1d-178">☑</span><span class="sxs-lookup"><span data-stu-id="26b1d-178">☑</span></span> | `newtype GeneratorTerm` | <span data-ttu-id="26b1d-179">Použití fráze substantivum jasně odkazuje na výsledek volání konstruktoru UDT.</span><span class="sxs-lookup"><span data-stu-id="26b1d-179">Use of noun phrase clearly refers to the result of calling the UDT constructor.</span></span> |
| <span data-ttu-id="26b1d-180">☒</span><span class="sxs-lookup"><span data-stu-id="26b1d-180">☒</span></span> | <s>`@Attribute() newtype RunOnce()`</s> | <span data-ttu-id="26b1d-181">Použití příkazového fráze navrhuje, že konstruktor UDT je operace.</span><span class="sxs-lookup"><span data-stu-id="26b1d-181">Use of verb phrase suggests that the UDT constructor is an operation.</span></span> |
| <span data-ttu-id="26b1d-182">☑</span><span class="sxs-lookup"><span data-stu-id="26b1d-182">☑</span></span> | `@Attribute() newtype Deprecated(Reason : String)` | <span data-ttu-id="26b1d-183">Použití fráze substantivum komunikuje s použitím atributu.</span><span class="sxs-lookup"><span data-stu-id="26b1d-183">Use of noun phrase communicates the use of the attribute.</span></span> |

***

### <a name="shorthand-and-abbreviations"></a><span data-ttu-id="26b1d-184">Zkratky a zkratky</span><span class="sxs-lookup"><span data-stu-id="26b1d-184">Shorthand and Abbreviations</span></span> ###

<span data-ttu-id="26b1d-185">Výše uvedená doporučení se neshoduje, existuje mnoho forem zkrácených ve formě běžných a pervasivech použití ve výpočetním prostředí.</span><span class="sxs-lookup"><span data-stu-id="26b1d-185">The above advice notwithstanding, there are many forms of shorthand that see common and pervasive use in quantum computing.</span></span>
<span data-ttu-id="26b1d-186">Doporučujeme používat existující a běžnou zkrácený popis, kde existuje, zejména pro operace, které jsou vnitřní pro provoz cílového počítače.</span><span class="sxs-lookup"><span data-stu-id="26b1d-186">We suggest using existing and common shorthand where it exists, especially for operations that are intrinsic to the operation of a target machine.</span></span>
<span data-ttu-id="26b1d-187">Například zvolíme název `X` místo `ApplyX`a `Rz` místo `RotateAboutZ`.</span><span class="sxs-lookup"><span data-stu-id="26b1d-187">For example, we choose the name `X` instead of `ApplyX`, and `Rz` instead of `RotateAboutZ`.</span></span>
<span data-ttu-id="26b1d-188">Při použití takových zkratek by názvy operací měly být všechna velká (např.: `MAJ`).</span><span class="sxs-lookup"><span data-stu-id="26b1d-188">When using such shorthand, operation names should be all uppercase (e.g.: `MAJ`).</span></span>

<span data-ttu-id="26b1d-189">Při použití této konvence v případě běžně používaných akronymů a initialisms, jako je například "QFT", se vyžaduje určitá péče.</span><span class="sxs-lookup"><span data-stu-id="26b1d-189">Some care is required when applying this convention in the case of commonly used acronyms and initialisms such as "QFT" for "quantum Fourier transform."</span></span>
<span data-ttu-id="26b1d-190">Pro použití akronymů a initialisms v úplných názvech doporučujeme následující obecné konvence rozhraní .NET, které předepisuje, že:</span><span class="sxs-lookup"><span data-stu-id="26b1d-190">We suggest following general .NET conventions for the use of acronyms and initialisms in full names, which prescribe that:</span></span>

- <span data-ttu-id="26b1d-191">zkratky se dvěma písmeny a initialisms se nazývají v horním případě (např.: `BE` pro "big-endian").</span><span class="sxs-lookup"><span data-stu-id="26b1d-191">two-letter acronyms and initialisms are named in upper case (e.g.: `BE` for "big-endian"),</span></span>
- <span data-ttu-id="26b1d-192">všechny delší akronymy a initialisms se pojmenují v `CamelCase` (např.: `Qft` pro "dobu" s "Fourierova transformace").</span><span class="sxs-lookup"><span data-stu-id="26b1d-192">all longer acronyms and initialisms are named in `CamelCase` (e.g.: `Qft` for "quantum Fourier transform")</span></span>

<span data-ttu-id="26b1d-193">Proto operace implementující QFT může být buď volána `QFT` jako zkrácený, nebo jako `ApplyQft`zapsána jako.</span><span class="sxs-lookup"><span data-stu-id="26b1d-193">Thus, an operation implementing the QFT could either be called `QFT` as shorthand, or written out as `ApplyQft`.</span></span>

<span data-ttu-id="26b1d-194">Pro obzvlášť používané operace a funkce může být vhodné zadat zkrácený název jako _alias_ pro delší tvar:</span><span class="sxs-lookup"><span data-stu-id="26b1d-194">For particularly commonly used operations and functions, it may be desirable to provide a shorthand name as an _alias_ for a longer form:</span></span>

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidancetabguidance"></a>[<span data-ttu-id="26b1d-195">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="26b1d-195">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="26b1d-196">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="26b1d-196">We suggest:</span></span>

- <span data-ttu-id="26b1d-197">V případě potřeby zvažte běžně přijatelné a často používané zkrácený název.</span><span class="sxs-lookup"><span data-stu-id="26b1d-197">Consider commonly accepted and widely used shorthand names when appropriate.</span></span>
- <span data-ttu-id="26b1d-198">Pro zkrácený tvar použijte velká písmena.</span><span class="sxs-lookup"><span data-stu-id="26b1d-198">Use uppercase for shorthand.</span></span>
- <span data-ttu-id="26b1d-199">Používejte velká písmena pro krátká (dvě písmena) zkratky a initialisms.</span><span class="sxs-lookup"><span data-stu-id="26b1d-199">Use uppercase for short (two-letter) acronyms and initialisms.</span></span>
- <span data-ttu-id="26b1d-200">Použijte `CamelCase` pro delší (tři nebo více písmen) a initialisms.</span><span class="sxs-lookup"><span data-stu-id="26b1d-200">Use `CamelCase` for longer (three or more letter) acronyms and initialisms.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="26b1d-201">Příklady</span><span class="sxs-lookup"><span data-stu-id="26b1d-201">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="26b1d-202">Name (Název)</span><span class="sxs-lookup"><span data-stu-id="26b1d-202">Name</span></span> | <span data-ttu-id="26b1d-203">Popis</span><span class="sxs-lookup"><span data-stu-id="26b1d-203">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="26b1d-204">☑</span><span class="sxs-lookup"><span data-stu-id="26b1d-204">☑</span></span> | `X` | <span data-ttu-id="26b1d-205">Dobře srozumitelná zkrácený příkaz pro použití transformace $X $</span><span class="sxs-lookup"><span data-stu-id="26b1d-205">Well-understood shorthand for "apply an $X$ transformation"</span></span> |
| <span data-ttu-id="26b1d-206">☑</span><span class="sxs-lookup"><span data-stu-id="26b1d-206">☑</span></span> | `CNOT` | <span data-ttu-id="26b1d-207">Dobře srozumitelná zkrácená zkratka pro "řízená – ne"</span><span class="sxs-lookup"><span data-stu-id="26b1d-207">Well-understood shorthand for "controlled-NOT"</span></span> |
| <span data-ttu-id="26b1d-208">☒</span><span class="sxs-lookup"><span data-stu-id="26b1d-208">☒</span></span> | <s>`Cnot`</s> | <span data-ttu-id="26b1d-209">Zkrácený odkaz by neměl být v `CamelCase`.</span><span class="sxs-lookup"><span data-stu-id="26b1d-209">Shorthand should not be in `CamelCase`.</span></span> |
| <span data-ttu-id="26b1d-210">☑</span><span class="sxs-lookup"><span data-stu-id="26b1d-210">☑</span></span> | `ApplyQft` | <span data-ttu-id="26b1d-211">Běžným počátečním názvem "QFT" se jeví jako součást formátu dlouhého formátu.</span><span class="sxs-lookup"><span data-stu-id="26b1d-211">Common initialism "QFT" appears as a part of a long-form name.</span></span> |
| <span data-ttu-id="26b1d-212">☑</span><span class="sxs-lookup"><span data-stu-id="26b1d-212">☑</span></span> | `QFT` | <span data-ttu-id="26b1d-213">Common initialer "QFT" se zobrazuje jako součást zkrácený název.</span><span class="sxs-lookup"><span data-stu-id="26b1d-213">Common initialism "QFT" appears as a part of a shorthand name.</span></span> |



***


### <a name="proper-nouns-in-names"></a><span data-ttu-id="26b1d-214">Správná jména v názvech</span><span class="sxs-lookup"><span data-stu-id="26b1d-214">Proper Nouns in Names</span></span> ###

<span data-ttu-id="26b1d-215">V rámci fyziky je běžné pojmenování po první osobě, která o nich je publikovaná, většina nephysicistsch není obeznámená s názvy všech a všech historií.</span><span class="sxs-lookup"><span data-stu-id="26b1d-215">While in physics it is common to name things after the first person to publish about them, most non-physicists aren’t familiar with everyone’s names and all of the history.</span></span>
<span data-ttu-id="26b1d-216">Velmi silně spoléhá na konvence pojmenování z fyziky, takže by se měla zabývat značnou překážkou vstupu, protože uživatelé z jiných pozadí se musí seznámit s velkým počtem zdánlivě neprůhledných názvů, aby mohli používat běžné operace a koncepty.</span><span class="sxs-lookup"><span data-stu-id="26b1d-216">Relying too heavily on naming conventions from physics can thus put up a substantial barrier to entry, as users from other backgrounds must learn a large number of seemingly opaque names in order to use common operations and concepts.</span></span>
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
<span data-ttu-id="26b1d-217">Proto doporučujeme, abyste při každém rozumném a běžném výskytu, který popisuje pojem koncept, přijali v rámci silné Předvolby na řádné podstatné jméno, které popisují historii publikace konceptu.</span><span class="sxs-lookup"><span data-stu-id="26b1d-217">Thus, we recommend that wherever reasonable, common nouns that describe a concept be adopted in strong preference to proper nouns that describe the publication history of a concept.</span></span>
<span data-ttu-id="26b1d-218">Jako konkrétní příklad se v rámci akademické literatury často označují samostatně kontrolované SWAPy a dvakrát kontrolované operace, ale v rámci Fredkin se identifikují hlavně jako `CSWAP` a `CCNOT`.</span><span class="sxs-lookup"><span data-stu-id="26b1d-218">As a particular example, the singly controlled SWAP and doubly controlled NOT operations are often called the "Fredkin" and "Toffoli" operations in academic literature, but are identified in Q# primarily as `CSWAP` and `CCNOT`.</span></span>
<span data-ttu-id="26b1d-219">V obou případech komentáře k rozhraní API poskytují synonymum názvů na základě správných podstatných jmen a spolu se všemi příslušnými citacemi.</span><span class="sxs-lookup"><span data-stu-id="26b1d-219">In both cases, the API documentation comments provide synonymous names based on proper nouns, along with all appropriate citations.</span></span>

<span data-ttu-id="26b1d-220">Tato předvolba je obzvláště důležitá vzhledem k tomu, že některé použití řádných podstatných jmen bude vždy nutné – Q # následuje po sadě klasických jazyků, například a odkazuje na `Bool` typy v odkazu na logickou logiku, která je zase pojmenována za akceptovatelné. z logického typu Jiří.</span><span class="sxs-lookup"><span data-stu-id="26b1d-220">This preference is especially important given that some usage of proper nouns will always be necessary — Q# follows the tradition set by many classical languages, for instance, and refers to `Bool` types in reference to Boolean logic, which is in turn named in honor of George Boole.</span></span>
<span data-ttu-id="26b1d-221">Několik základních principů je obdobně pojmenováno podobným způsobem, včetně typu `Pauli` integrovaného do jazyka Q #.</span><span class="sxs-lookup"><span data-stu-id="26b1d-221">A few quantum concepts similarly are named in a similar fashion, including the `Pauli` type built-in to the Q# language.</span></span>
<span data-ttu-id="26b1d-222">Minimalizací použití řádných podstatných jmen, kde takové použití není nezbytné, snižujeme dopad na to, kde nelze rozumně obejít řádná podstatná jména.</span><span class="sxs-lookup"><span data-stu-id="26b1d-222">By minimizing the usage of proper nouns where such usage is not essential, we reduce the impact where proper nouns cannot be reasonably avoided.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="26b1d-223">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="26b1d-223">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="26b1d-224">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="26b1d-224">We suggest:</span></span>

- <span data-ttu-id="26b1d-225">Vyhněte se použití řádných podstatných jmen v názvech.</span><span class="sxs-lookup"><span data-stu-id="26b1d-225">Avoid the use of proper nouns in names.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="26b1d-226">Příklady</span><span class="sxs-lookup"><span data-stu-id="26b1d-226">Examples</span></span>](#tab/examples)

***

### <a name="type-conversions"></a><span data-ttu-id="26b1d-227">Převody typu</span><span class="sxs-lookup"><span data-stu-id="26b1d-227">Type Conversions</span></span> ###

<span data-ttu-id="26b1d-228">Vzhledem k tomu, že Q # je silně a staticky typovaného jazyka, hodnota jednoho typu může být použita pouze jako hodnota jiného typu pomocí explicitního volání funkce pro převod typu.</span><span class="sxs-lookup"><span data-stu-id="26b1d-228">Since Q# is a strongly and staticly typed language, a value of one type can only be used as a value of another type by using an explicit call to a type conversion function.</span></span>
<span data-ttu-id="26b1d-229">To je v kontrastu s jazyky, které umožňují hodnotám měnit typy implicitně (např.: povýšení typu) nebo prostřednictvím přetypování.</span><span class="sxs-lookup"><span data-stu-id="26b1d-229">This is in contrast to languages which allow for values to change types implicitly (e.g.: type promotion), or through casting.</span></span>
<span data-ttu-id="26b1d-230">Výsledkem je, že funkce pro převod typu hrají důležitou roli ve vývoji knihovny Q # a sestávají z nich jedno z častých rozhodnutí o pojmenování.</span><span class="sxs-lookup"><span data-stu-id="26b1d-230">As a result, type conversion functions play an important role in Q# library development, and comprise one of the more commonly encountered decisions about naming.</span></span>
<span data-ttu-id="26b1d-231">Upozorňujeme však, že protože převody typu jsou vždycky _deterministické_, můžou být zapsány jako funkce a tak do výše uvedených rad.</span><span class="sxs-lookup"><span data-stu-id="26b1d-231">We note, however, that since type conversions are always _deterministic_, they can be written as functions and thus fall under the advice above.</span></span>
<span data-ttu-id="26b1d-232">Konkrétně doporučujeme, aby funkce pro převod typu neměly být nikdy pojmenovány jako slovesa (např.: `ConvertToX`) nebo příznakem příznaku příznaku (`ToX`), ale měly by se pojmenovat jako předpozice "adjektivum", které označují zdrojové a cílové typy (`XAsY`).</span><span class="sxs-lookup"><span data-stu-id="26b1d-232">In particular, we suggest that type conversion functions should never be named as verbs (e.g.: `ConvertToX`) or adverb prepositional phrases (`ToX`), but should be named as adjective prepositional phrases that indicate the source and destination types (`XAsY`).</span></span>
<span data-ttu-id="26b1d-233">Při výpisu typů polí v názvech funkcí konverze typu doporučujeme zkrácený `Arr`.</span><span class="sxs-lookup"><span data-stu-id="26b1d-233">When listing array types in type conversion function names, we recommend the shorthand `Arr`.</span></span>
<span data-ttu-id="26b1d-234">Blokování výjimečných okolností, doporučujeme, aby všechny funkce pro převod typů byly pojmenovány pomocí `As`, aby je bylo možné rychle identifikovat.</span><span class="sxs-lookup"><span data-stu-id="26b1d-234">Barring exceptional circumstances, we recommend that all type conversion functions be named using `As` so that they can be quickly identified.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="26b1d-235">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="26b1d-235">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="26b1d-236">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="26b1d-236">We suggest:</span></span>

- <span data-ttu-id="26b1d-237">Pokud funkce převede hodnotu typu `X` na hodnotu typu `Y`, použijte buď název `AsY` nebo `XAsY`.</span><span class="sxs-lookup"><span data-stu-id="26b1d-237">If a function converts a value of type `X` to a value of type `Y`, use either the name `AsY` or `XAsY`.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="26b1d-238">Příklady</span><span class="sxs-lookup"><span data-stu-id="26b1d-238">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="26b1d-239">Name (Název)</span><span class="sxs-lookup"><span data-stu-id="26b1d-239">Name</span></span> | <span data-ttu-id="26b1d-240">Popis</span><span class="sxs-lookup"><span data-stu-id="26b1d-240">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="26b1d-241">☒</span><span class="sxs-lookup"><span data-stu-id="26b1d-241">☒</span></span> | <s>`ToDouble`</s> | <span data-ttu-id="26b1d-242">Výsledkem předpozice "do" je příkazová fráze, která značí operaci a nikoli funkci.</span><span class="sxs-lookup"><span data-stu-id="26b1d-242">The preposition "to" results in a verb phrase, indicating an operation and not a function.</span></span> |
| <span data-ttu-id="26b1d-243">☒</span><span class="sxs-lookup"><span data-stu-id="26b1d-243">☒</span></span> | <s>`AsDouble`</s> | <span data-ttu-id="26b1d-244">Typ vstupu není jasný od názvu funkce.</span><span class="sxs-lookup"><span data-stu-id="26b1d-244">The input type is not clear from the function name.</span></span> |
| <span data-ttu-id="26b1d-245">☒</span><span class="sxs-lookup"><span data-stu-id="26b1d-245">☒</span></span> | <s>`PauliArrFromBoolArr`</s> | <span data-ttu-id="26b1d-246">Vstupní a výstupní typy se zobrazí v nesprávném pořadí.</span><span class="sxs-lookup"><span data-stu-id="26b1d-246">The input and output types appear in the wrong order.</span></span> |
| <span data-ttu-id="26b1d-247">☑</span><span class="sxs-lookup"><span data-stu-id="26b1d-247">☑</span></span> | `ResultArrAsBoolArr` | <span data-ttu-id="26b1d-248">Vstupní typy i výstupní typy jsou jasné.</span><span class="sxs-lookup"><span data-stu-id="26b1d-248">Both the input types and output types are clear.</span></span> |

***

### <a name="private-or-internal-names"></a><span data-ttu-id="26b1d-249">Privátní nebo interní názvy</span><span class="sxs-lookup"><span data-stu-id="26b1d-249">Private or Internal Names</span></span> ###

<span data-ttu-id="26b1d-250">V mnoha případech je název určený výhradně pro použití interního pro knihovnu nebo projekt a není zaručenou součástí rozhraní API nabízeného knihovnou.</span><span class="sxs-lookup"><span data-stu-id="26b1d-250">In many cases, a name is intended strictly for use internal to a library or project, and is not a guaranteed part of the API offered by a library.</span></span>
<span data-ttu-id="26b1d-251">Je vhodné jasně označit, že se jedná o případ, kdy se pojmenují funkce a operace, aby byly náhodné závislosti na kódu pouze v interním kódu.</span><span class="sxs-lookup"><span data-stu-id="26b1d-251">It is helpful to clearly indicate that this is the case when naming functions and operations so that accidental dependencies on internal-only code are made obvious.</span></span>
<span data-ttu-id="26b1d-252">Pokud operace nebo funkce není určena pro přímé použití, ale místo toho by měla být použita odpovídajícím voláním, které funguje na základě částečné aplikace, zvažte použití názvu začínajícího `_` pro volání, které je částečně použito.</span><span class="sxs-lookup"><span data-stu-id="26b1d-252">If an operation or function is not intended for direct use, but rather should be used by a matching callable which acts by partial application, consider using a name starting with `_` for the callable that is partially applied.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="26b1d-253">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="26b1d-253">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="26b1d-254">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="26b1d-254">We suggest:</span></span>

- <span data-ttu-id="26b1d-255">Není-li funkce, operace nebo uživatelsky definovaný typ součástí veřejného rozhraní API pro knihovnu nebo program Q #, ujistěte se, že název začíná počátečním podtržítkem (`_`).</span><span class="sxs-lookup"><span data-stu-id="26b1d-255">When a function, operation, or user-defined type is not a part of the public API for a Q# library or program, ensure that its name begins with a leading underscore (`_`).</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="26b1d-256">Příklady</span><span class="sxs-lookup"><span data-stu-id="26b1d-256">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="26b1d-257">Name (Název)</span><span class="sxs-lookup"><span data-stu-id="26b1d-257">Name</span></span> | <span data-ttu-id="26b1d-258">Popis</span><span class="sxs-lookup"><span data-stu-id="26b1d-258">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="26b1d-259">☒</span><span class="sxs-lookup"><span data-stu-id="26b1d-259">☒</span></span> | <s>`ApplyDecomposedOperation_`</s> | <span data-ttu-id="26b1d-260">Podtržítko `_` nesmí být na konci názvu.</span><span class="sxs-lookup"><span data-stu-id="26b1d-260">The underscore `_` should not appear at the end of the name.</span></span> |
| <span data-ttu-id="26b1d-261">☑</span><span class="sxs-lookup"><span data-stu-id="26b1d-261">☑</span></span> | `_ApplyDecomposedOperation` | <span data-ttu-id="26b1d-262">Podtržítko `_` na začátku jasně označuje, že tato operace je určena pouze pro interní použití.</span><span class="sxs-lookup"><span data-stu-id="26b1d-262">The underscore `_` at the beginning clearly indicates that this operation is for internal use only.</span></span> |

***

### <a name="variants"></a><span data-ttu-id="26b1d-263">Typy</span><span class="sxs-lookup"><span data-stu-id="26b1d-263">Variants</span></span> ###

<span data-ttu-id="26b1d-264">I když toto omezení nemusí být v budoucích verzích Q # trvalé, je v současné době v případě, že budou často skupiny souvisejících operací nebo funkcí, které jsou odlišené funktory jejich vstupy, nebo konkrétními typy jejich argumentů.</span><span class="sxs-lookup"><span data-stu-id="26b1d-264">Though this limitation may not persist in future versions of Q#, it is presently the case that there will often be groups of related operations or functions that are distinguished by which functors their inputs support, or by the concrete types of their arguments.</span></span>
<span data-ttu-id="26b1d-265">Tyto skupiny lze odlišit pomocí stejného kořenového názvu, následovaný jedním nebo dvěma písmeny, která označují jeho variantu.</span><span class="sxs-lookup"><span data-stu-id="26b1d-265">These groups can be distinguished by using the same root name, followed by one or two letters that indicate its variant.</span></span>

| <span data-ttu-id="26b1d-266">Auditování</span><span class="sxs-lookup"><span data-stu-id="26b1d-266">Suffix</span></span> | <span data-ttu-id="26b1d-267">Význam</span><span class="sxs-lookup"><span data-stu-id="26b1d-267">Meaning</span></span> |
|--------|---------|
| `A` | <span data-ttu-id="26b1d-268">Byl očekáván vstup, který podporuje `Adjoint`</span><span class="sxs-lookup"><span data-stu-id="26b1d-268">Input expected to support `Adjoint`</span></span> |
| `C` | <span data-ttu-id="26b1d-269">Byl očekáván vstup, který podporuje `Controlled`</span><span class="sxs-lookup"><span data-stu-id="26b1d-269">Input expected to support `Controlled`</span></span> |
| `CA` | <span data-ttu-id="26b1d-270">Byl očekáván vstup, který podporuje `Controlled` a `Adjoint`</span><span class="sxs-lookup"><span data-stu-id="26b1d-270">Input expected to support `Controlled` and `Adjoint`</span></span> |
| `I` | <span data-ttu-id="26b1d-271">Vstup nebo vstupy jsou typu `Int`</span><span class="sxs-lookup"><span data-stu-id="26b1d-271">Input or inputs are of type `Int`</span></span> |
| `D` | <span data-ttu-id="26b1d-272">Vstup nebo vstupy jsou typu `Double`</span><span class="sxs-lookup"><span data-stu-id="26b1d-272">Input or inputs are of type `Double`</span></span> |
| `L` | <span data-ttu-id="26b1d-273">Vstup nebo vstupy jsou typu `BigInt`</span><span class="sxs-lookup"><span data-stu-id="26b1d-273">Input or inputs are of type `BigInt`</span></span> |

# <a name="guidancetabguidance"></a>[<span data-ttu-id="26b1d-274">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="26b1d-274">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="26b1d-275">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="26b1d-275">We suggest:</span></span>

- <span data-ttu-id="26b1d-276">Pokud funkce nebo operace nesouvisí s podobnými funkcemi nebo operacemi, které typy a funktor podporují jejich vstupy, nepoužívejte příponu.</span><span class="sxs-lookup"><span data-stu-id="26b1d-276">If a function or operation is not related to any similar functions or operations by the types and functor support of their inputs, do not use a suffix.</span></span>
- <span data-ttu-id="26b1d-277">Pokud funkce nebo operace souvisí s podobnými funkcemi nebo operacemi podle typů a funktor podpory jejich vstupů, použijte přípony jako v tabulce výše, abyste rozlišili varianty.</span><span class="sxs-lookup"><span data-stu-id="26b1d-277">If a function or operation is related to any similar functions or operations by the types and functor support of their inputs, use suffixes as in the table above to distinguish variants.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="26b1d-278">Příklady</span><span class="sxs-lookup"><span data-stu-id="26b1d-278">Examples</span></span>](#tab/examples)

***

### <a name="arguments-and-variables"></a><span data-ttu-id="26b1d-279">Argumenty a proměnné</span><span class="sxs-lookup"><span data-stu-id="26b1d-279">Arguments and Variables</span></span> ###

<span data-ttu-id="26b1d-280">Klíčový cíl kódu Q # pro funkci nebo operaci je, aby jej bylo možné snadno přečíst a pochopit.</span><span class="sxs-lookup"><span data-stu-id="26b1d-280">A key goal of the Q# code for a function or operation is for it to be easily read and understood.</span></span>
<span data-ttu-id="26b1d-281">Podobně názvy vstupů a argumentů typu by měly sdělit, jak se bude funkce nebo argument používat, jakmile bude k dispozici.</span><span class="sxs-lookup"><span data-stu-id="26b1d-281">Similarly, the names of inputs and type arguments should communicate how a function or argument will be used once provided.</span></span>


# <a name="guidancetabguidance"></a>[<span data-ttu-id="26b1d-282">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="26b1d-282">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="26b1d-283">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="26b1d-283">We suggest:</span></span>

- <span data-ttu-id="26b1d-284">Pro všechny proměnné a vstupní názvy použijte `pascalCase` v případě silné Předvolby na `CamelCase`, `snake_case`nebo `ANGRY_CASE`.</span><span class="sxs-lookup"><span data-stu-id="26b1d-284">For all variable and input names, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span>
- <span data-ttu-id="26b1d-285">Vstupní názvy by měly být popisné; Vyhněte se jednomu nebo dvěma názvům písmen, pokud je to možné.</span><span class="sxs-lookup"><span data-stu-id="26b1d-285">Input names should be descriptive; avoid one or two letter names where possible.</span></span>
- <span data-ttu-id="26b1d-286">Operace a funkce, které přijímají přesně jeden argument typu, by měly poznamenat, že argument typu je `T`, když je jeho role zřejmá.</span><span class="sxs-lookup"><span data-stu-id="26b1d-286">Operations and functions accepting exactly one type argument should denote that type argument by `T` when its role is obvious.</span></span>
- <span data-ttu-id="26b1d-287">Pokud funkce nebo operace přebírá více argumentů typu nebo pokud role jednoho argumentu typu není zřejmá, zvažte použití krátkého slova, které je `T` (např.: `TOutput`) pro každý typ.</span><span class="sxs-lookup"><span data-stu-id="26b1d-287">If a function or operation takes multiple type arguments, or if the role of a single type argument is not obvious, consider using a short capitalized word prefaced by `T` (e.g.: `TOutput`) for each type.</span></span>
- <span data-ttu-id="26b1d-288">Do názvů argumentů a proměnných nezahrnujte názvy typů; Tyto informace můžou a by měly být poskytované vaším vývojovým prostředím.</span><span class="sxs-lookup"><span data-stu-id="26b1d-288">Do not include type names in argument and variable names; this information can and should be provided by your development environment.</span></span>
- <span data-ttu-id="26b1d-289">Zaznamenejte skalární typy podle jejich názvů literálů (`flagQubit`) a typy polí pomocí plural (`measResults`).</span><span class="sxs-lookup"><span data-stu-id="26b1d-289">Denote scalar types by their literal names (`flagQubit`), and array types by a plural (`measResults`).</span></span>
  <span data-ttu-id="26b1d-290">V případě polí qubits je vhodné zvážit označení těchto typů pomocí `Register`, kde název odkazuje na sekvenci qubits, které úzce souvisejí s nějakým způsobem.</span><span class="sxs-lookup"><span data-stu-id="26b1d-290">For arrays of qubits in particular, consider denoting such types by `Register` where the name refers to a sequence of qubits that are closely related in some way.</span></span>
- <span data-ttu-id="26b1d-291">Proměnné použité jako indexy do polí by měly začínat `idx` a měly by být jednotné (např.: `things[idxThing]`).</span><span class="sxs-lookup"><span data-stu-id="26b1d-291">Variables used as indices into arrays should begin with `idx` and should be singular (e.g.: `things[idxThing]`).</span></span>
  <span data-ttu-id="26b1d-292">Zejména se silně Vyhněte použití názvů proměnných s jedním písmenem jako indexů; Zvažte použití `idx` minimálně.</span><span class="sxs-lookup"><span data-stu-id="26b1d-292">In particular, strongly avoid using single-letter variable names as indices; consider using `idx` at a minimum.</span></span>
- <span data-ttu-id="26b1d-293">Proměnné používané pro uchovávání délek polí by měly začínat `n` a měly by být v množném čísle (např.: `nThings`).</span><span class="sxs-lookup"><span data-stu-id="26b1d-293">Variables used to hold lengths of arrays should begin with `n` and should be pluralized (e.g.: `nThings`).</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="26b1d-294">Příklady</span><span class="sxs-lookup"><span data-stu-id="26b1d-294">Examples</span></span>](#tab/examples)

***

### <a name="user-defined-type-named-items"></a><span data-ttu-id="26b1d-295">Uživatelem definovaný typ s názvem Items</span><span class="sxs-lookup"><span data-stu-id="26b1d-295">User Defined Type Named Items</span></span> ###

<span data-ttu-id="26b1d-296">Pojmenované položky v uživatelsky definovaných typech by měly být pojmenovány jako `CamelCase`, a to i ve vstupu na konstruktory UDT.</span><span class="sxs-lookup"><span data-stu-id="26b1d-296">Named items in user-defined types should be named as `CamelCase`, even in input to UDT constructors.</span></span>
<span data-ttu-id="26b1d-297">To pomáhá při použití notace přistupujícího objektu (např.: `callable::Apply`) nebo zápisu typu Copy-and-Update (`set arr w/= Data <- newData`) jasně oddělit pojmenované položky od odkazů na místně vymezené proměnné.</span><span class="sxs-lookup"><span data-stu-id="26b1d-297">This helps in order to clearly separate named items from references to locally scoped variables when using accessor notation (e.g.: `callable::Apply`) or copy-and-update notation (`set arr w/= Data <- newData`).</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="26b1d-298">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="26b1d-298">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="26b1d-299">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="26b1d-299">We suggest:</span></span>

- <span data-ttu-id="26b1d-300">Pojmenované položky v konstruktorech UDT by měly být pojmenovány jako `CamelCase`; To znamená, že by měly začínat počátečními velkými písmeny.</span><span class="sxs-lookup"><span data-stu-id="26b1d-300">Named items in UDT constructors should be named as `CamelCase`; that is, they should begin with an initial uppercase.</span></span>
- <span data-ttu-id="26b1d-301">Pojmenované položky, které se překládají na operace, by měly být pojmenovány jako fáze operací.</span><span class="sxs-lookup"><span data-stu-id="26b1d-301">Named items that resolve to operations should be named as verb phases.</span></span>
- <span data-ttu-id="26b1d-302">Pojmenované položky, které nelze přeložit na operace, by měly být pojmenovány jako podstatné fráze.</span><span class="sxs-lookup"><span data-stu-id="26b1d-302">Named items that do not resolve to operations should be named as noun phrases.</span></span>
- <span data-ttu-id="26b1d-303">Pro UDT, které zabalí operace, by měla být definována jedna pojmenovaná položka s názvem `Apply`.</span><span class="sxs-lookup"><span data-stu-id="26b1d-303">For UDTs that wrap operations, a single named item called `Apply` should be defined.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="26b1d-304">Příklady</span><span class="sxs-lookup"><span data-stu-id="26b1d-304">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="26b1d-305">Zlomk</span><span class="sxs-lookup"><span data-stu-id="26b1d-305">Snippet</span></span> | <span data-ttu-id="26b1d-306">Popis</span><span class="sxs-lookup"><span data-stu-id="26b1d-306">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="26b1d-307">☑</span><span class="sxs-lookup"><span data-stu-id="26b1d-307">☑</span></span> | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | <span data-ttu-id="26b1d-308">Název `Apply` je příkazová fráze ve formátu `CamelCase`, což naznačuje, že pojmenovaná položka je operace.</span><span class="sxs-lookup"><span data-stu-id="26b1d-308">The name `Apply` is a `CamelCase`-formatted verb phrase, suggesting that the named item is an operation.</span></span> |
| <span data-ttu-id="26b1d-309">☒</span><span class="sxs-lookup"><span data-stu-id="26b1d-309">☒</span></span> | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | <span data-ttu-id="26b1d-310">Pojmenované položky by měly začínat počátečním velkým písmenem.</span><span class="sxs-lookup"><span data-stu-id="26b1d-310">Named items should begin with an initial uppercase letter.</span></span> |
| <span data-ttu-id="26b1d-311">☒</span><span class="sxs-lookup"><span data-stu-id="26b1d-311">☒</span></span> | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | <span data-ttu-id="26b1d-312">Pojmenované položky, které se mají vyhodnotit na Functions, by měly být pojmenovány jako podstatné fráze, nikoli jako slovesová</span><span class="sxs-lookup"><span data-stu-id="26b1d-312">Named items which resolve to functions should be named as noun phrases, not as verb phrases.</span></span> |

***

## <a name="input-conventions"></a><span data-ttu-id="26b1d-313">Vstupní konvence</span><span class="sxs-lookup"><span data-stu-id="26b1d-313">Input Conventions</span></span> ##

<span data-ttu-id="26b1d-314">Pokud vývojář volá operaci nebo funkci, je nutné určit různé vstupy pro tuto operaci nebo funkci v určitém pořadí, čímž se zvýší zátěžové zatížení, které vývojář vytvoří, aby mohli použít knihovnu.</span><span class="sxs-lookup"><span data-stu-id="26b1d-314">When a developer calls into an operation or function, the various inputs to that operation or function must be specified in a particular order, increasing the cognitive load that a developer faces in order to make use of a library.</span></span>
<span data-ttu-id="26b1d-315">Konkrétně úkol přeřazení vstupních objednávek je často z úlohy rušivý: programování implementace algoritmu pro plnění.</span><span class="sxs-lookup"><span data-stu-id="26b1d-315">In particular, the task of remembering input orderings is often a distraction from the task at hand: programming an implementation of a quantum algorithm.</span></span>
<span data-ttu-id="26b1d-316">I když Rozsáhlá podpora integrovaného vývojového prostředí (IDE) může toto omezení zmírnit na velký rozsah, dobrý návrh a uplatnění běžných konvencí, může také pomoci minimalizovat zátěž vypracovanou rozhraním API.</span><span class="sxs-lookup"><span data-stu-id="26b1d-316">Though rich IDE support can mitigate this to a large extent, good design and adherence to common conventions can also help to minimize the cognitive load imposed by an API.</span></span>

<span data-ttu-id="26b1d-317">Pokud je to možné, může být užitečné snížit počet vstupů očekávaných operací nebo funkcí, aby se role každého vstupu načetla okamžitě pro vývojáře, kteří volají tuto operaci nebo funkci, a vývojářům tento kód přečte později.</span><span class="sxs-lookup"><span data-stu-id="26b1d-317">Where possible, it can be helpful to reduce the number of inputs expected by an operation or function, so that the role of each input is more immediately obvious both to developers calling into that operation or function, and to developers reading that code later.</span></span>
<span data-ttu-id="26b1d-318">Zejména v případě, že není možné nebo rozumné snížit počet argumentů operace nebo funkce, je důležité mít konzistentní řazení, které minimalizuje neohlášení chyb uživatelů při předvídání pořadí vstupů.</span><span class="sxs-lookup"><span data-stu-id="26b1d-318">Especially when it is not possible or reasonable to reduce the number of arguments to an operation or function, it is important to have a consistent ordering that minimizes the surprise that a user faces when predicting the order of inputs.</span></span>

<span data-ttu-id="26b1d-319">Doporučujeme konvence pro řazení vstupu, které jsou převážně odvozené z úvahy částečné aplikace jako generalizace procesu curryfikace f (x, y) ≡ f (x) (y).</span><span class="sxs-lookup"><span data-stu-id="26b1d-319">We recommend an input ordering conventions that largely derives from thinking of partial application as a generalization of currying 𝑓(𝑥, 𝑦) ≡ 𝑓(𝑥)(𝑦).</span></span>
<span data-ttu-id="26b1d-320">Proto by částečně použití prvních argumentů mělo být volat, které je užitečné, pokud je to vhodné.</span><span class="sxs-lookup"><span data-stu-id="26b1d-320">Thus, partially applying the first arguments should result in a callable that is useful in its own right whenever that is reasonable.</span></span>
<span data-ttu-id="26b1d-321">Podle tohoto principu zvažte použití následujícího pořadí argumentů:</span><span class="sxs-lookup"><span data-stu-id="26b1d-321">Following this principle, consider using the following order of arguments:</span></span>

- <span data-ttu-id="26b1d-322">Klasické nediskriminační argumenty, jako jsou úhly, vektory a atd.</span><span class="sxs-lookup"><span data-stu-id="26b1d-322">Classical non-callable arguments such as angles, vectors of powers, etc.</span></span>
- <span data-ttu-id="26b1d-323">Argumenty pro možnost volat (funkce a argumenty).</span><span class="sxs-lookup"><span data-stu-id="26b1d-323">Callable arguments (functions and arguments).</span></span>
  <span data-ttu-id="26b1d-324">Pokud jsou funkce a operace provedeny jako argumenty, zvažte umístění operací po funkcích.</span><span class="sxs-lookup"><span data-stu-id="26b1d-324">If both functions and operations are taken as arguments, consider placing operations after functions.</span></span>
- <span data-ttu-id="26b1d-325">Kolekce, na kterých se pracuje, pomocí volání argumentů podobným způsobem, jak `Map`, `Iter`, `Enumerate`a `Fold`.</span><span class="sxs-lookup"><span data-stu-id="26b1d-325">Collections acted upon by callable arguments in a similar way to `Map`, `Iter`, `Enumerate`, and `Fold`.</span></span>
- <span data-ttu-id="26b1d-326">Argumenty qubit slouží jako ovládací prvky.</span><span class="sxs-lookup"><span data-stu-id="26b1d-326">Qubit arguments used as controls.</span></span>
- <span data-ttu-id="26b1d-327">Argumenty qubit slouží jako cíle.</span><span class="sxs-lookup"><span data-stu-id="26b1d-327">Qubit arguments used as targets.</span></span>

<span data-ttu-id="26b1d-328">Vezměte v úvahu operaci `ApplyPhaseEstimationIteration` pro použití ve odhadu fáze, který přebírá úhel a Oracle, předá úhel, který se `Rz` změnil řadou různých faktorů škálování, a pak řídí aplikace Oracle.</span><span class="sxs-lookup"><span data-stu-id="26b1d-328">Consider an operation `ApplyPhaseEstimationIteration` for use in phase estimation that takes an angle and an oracle, passes the angle to `Rz` modified by an array of different scaling factors, and then controls applications of the oracle.</span></span>
<span data-ttu-id="26b1d-329">Vstupy jsme poznamenali `ApplyPhaseEstimationIteration` následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="26b1d-329">We would order the inputs to `ApplyPhaseEstimationIteration` in the following fashion:</span></span>

```qsharp
operation ApplyPhaseEstimationIteration(
    angle : Double,
    callable : (Qubit => () is Ctl),
    scaleFactors : Double[],
    controlQubit : Qubit,
    targetQubits : Qubit[]
)
: Unit
...
```
<span data-ttu-id="26b1d-330">U některých funkcí a operací, které jsou ve zvláštních případech minimalizovány, napodobuje chování integrovaných funktory `Adjoint` a `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="26b1d-330">As a special case of minimizing surprise, some functions and operations mimic the behavior of the built-in functors `Adjoint` and `Controlled`.</span></span>
<span data-ttu-id="26b1d-331">Například `ControlledOnInt<'T>` je typu `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, například, aby `ControlledOnInt<Qubit[]>(5, _)` fungovat jako `Controlled` funktor, ale na podmínku, kterou registr ovládacího prvku představuje stav $ \ket{5} = \ket{101}$.</span><span class="sxs-lookup"><span data-stu-id="26b1d-331">For instance, `ControlledOnInt<'T>` has type `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, such that `ControlledOnInt<Qubit[]>(5, _)` acts like the `Controlled` functor, but on the condition that the control register represents the state $\ket{5} = \ket{101}$.</span></span>
<span data-ttu-id="26b1d-332">Proto vývojář očekává, že vstupy `ControlledOnInt` umístit vracené operace jako poslední a že výsledná operace přebírá jako svůj vstupní `(Qubit[], 'T)`---stejné pořadí, jako následuje výstup `Controlled` funktor.</span><span class="sxs-lookup"><span data-stu-id="26b1d-332">Thus, a developer expects that the inputs to `ControlledOnInt` place the callable being transformed last, and that the resulting operation takes as its input `(Qubit[], 'T)` --- the same order as followed by the output of the `Controlled` functor.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="26b1d-333">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="26b1d-333">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="26b1d-334">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="26b1d-334">We suggest:</span></span>

- <span data-ttu-id="26b1d-335">Používejte vstupní pořadí konzistentní s použitím částečné aplikace.</span><span class="sxs-lookup"><span data-stu-id="26b1d-335">Use input orderings consistent with the use of partial application.</span></span>
- <span data-ttu-id="26b1d-336">Používejte vstupní pořadí konzistentní s integrovanými funktory.</span><span class="sxs-lookup"><span data-stu-id="26b1d-336">Use input orderings consistent with built-in functors.</span></span>
- <span data-ttu-id="26b1d-337">Všechny klasické vstupy umístěte před všechny vstupy za sebou.</span><span class="sxs-lookup"><span data-stu-id="26b1d-337">Place all classical inputs before any quantum inputs.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="26b1d-338">Příklady</span><span class="sxs-lookup"><span data-stu-id="26b1d-338">Examples</span></span>](#tab/examples)

***

## <a name="documentation-conventions"></a><span data-ttu-id="26b1d-339">Konvence dokumentace</span><span class="sxs-lookup"><span data-stu-id="26b1d-339">Documentation Conventions</span></span> ##

<span data-ttu-id="26b1d-340">Jazyk Q # umožňuje připojit dokumentaci k operacím, funkcím a uživatelsky definovaným typům pomocí speciálně formátovaných dokumentačních komentářů.</span><span class="sxs-lookup"><span data-stu-id="26b1d-340">The Q# language allows for attaching documentation to operations, functions, and user-defined types through the use of specially formatted documentation comments.</span></span>
<span data-ttu-id="26b1d-341">Tyto komentáře k této dokumentaci jsou označeny trojitými lomítky (`///`), [](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) které se dají použít k popisu účelu jednotlivých operací, funkcí a uživatelsky definovaných typů, které vstupy očekává a tak dále.</span><span class="sxs-lookup"><span data-stu-id="26b1d-341">Denoted by triple-slashes (`///`), these documentation comments are small [DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) documents that can be used to describing the purpose of each operation, function, and user-defined type, what inputs each expects, and so forth.</span></span>
<span data-ttu-id="26b1d-342">Kompilátor, který je součástí vývojové sady pro všechna ta, extrahuje tyto komentáře a použije je k tomu https://docs.microsoft.com/quantum, aby vám pomohly sázení dokumentaci podobnou dokumentaci.</span><span class="sxs-lookup"><span data-stu-id="26b1d-342">The compiler provided with the Quantum Development Kit extracts these comments and uses them to help typeset documentation similar to that at https://docs.microsoft.com/quantum.</span></span>
<span data-ttu-id="26b1d-343">Podobně jazykový Server, který je součástí vývojové sady pro plnění, používá tyto komentáře k poskytnutí pomocníka uživatelům při přechodu myší na symboly v kódu Q #.</span><span class="sxs-lookup"><span data-stu-id="26b1d-343">Similarly, the language server provided with the Quantum Development Kit uses these comments to provide help to users when they hover over symbols in their Q# code.</span></span>
<span data-ttu-id="26b1d-344">Používání dokumentačních komentářů tak může pomoci uživatelům vydávat smysl kódu tím, že poskytuje užitečnou referenci pro podrobnosti, které nejsou snadno vyjádřeny pomocí dalších úmluv v tomto dokumentu.</span><span class="sxs-lookup"><span data-stu-id="26b1d-344">Making use of documentation comments can thus help users to make sense of code by providing a useful reference for details that are not easily expressed using the other conventions in this document.</span></span>

<div class="nextstepaction"><span data-ttu-id="26b1d-345">
    [Referenční dokumentace k syntaxi komentářů k dokumentaci](xref:microsoft.quantum.language.statements#documentation-comments)
</span><span class="sxs-lookup"><span data-stu-id="26b1d-345">
    [Documentation comment syntax reference](xref:microsoft.quantum.language.statements#documentation-comments)
</span></span></div>

<span data-ttu-id="26b1d-346">Aby bylo možné efektivně využít tuto funkci, doporučujeme, abyste při psaní dokumentačních komentářů měli na paměti pár věcí.</span><span class="sxs-lookup"><span data-stu-id="26b1d-346">In order to effectively use this functionality to help users, we recommend keeping a few things in mind as you write documentation comments.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="26b1d-347">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="26b1d-347">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="26b1d-348">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="26b1d-348">We suggest:</span></span>

- <span data-ttu-id="26b1d-349">Každá veřejná funkce, operace a uživatelsky definované typy by měly hned předcházet dokumentační komentář.</span><span class="sxs-lookup"><span data-stu-id="26b1d-349">Each public function, operation, and user-defined type should be immediately preceded by a documentation comment.</span></span>
- <span data-ttu-id="26b1d-350">Každý dokumentační komentář by měl mít minimálně následující oddíly:</span><span class="sxs-lookup"><span data-stu-id="26b1d-350">At a minimum, each documentation comment should include the following sections:</span></span>
    - <span data-ttu-id="26b1d-351">Souhrn</span><span class="sxs-lookup"><span data-stu-id="26b1d-351">Summary</span></span>
    - <span data-ttu-id="26b1d-352">Vstup</span><span class="sxs-lookup"><span data-stu-id="26b1d-352">Input</span></span>
    - <span data-ttu-id="26b1d-353">Výstup (Pokud je k dispozici)</span><span class="sxs-lookup"><span data-stu-id="26b1d-353">Output (if applicable)</span></span>
- <span data-ttu-id="26b1d-354">Ujistěte se, že všechny souhrny jsou dvě nebo méně vět.</span><span class="sxs-lookup"><span data-stu-id="26b1d-354">Ensure that all summaries are two sentences or less.</span></span> <span data-ttu-id="26b1d-355">Pokud je potřeba více místa, poskytněte `# Description` oddíl hned za `# Summary` s úplnými podrobnostmi.</span><span class="sxs-lookup"><span data-stu-id="26b1d-355">If more room is needed, provide a `# Description` section immediately following `# Summary` with complete details.</span></span>
- <span data-ttu-id="26b1d-356">Tam, kde je to rozumné, nezahrnuje matematiku v souhrnech, protože ne všichni klienti podporují TeX Notation v souhrnech.</span><span class="sxs-lookup"><span data-stu-id="26b1d-356">Where reasonable, do not include math in summaries, as not all clients support TeX notation in summaries.</span></span> <span data-ttu-id="26b1d-357">Pamatujte na to, že při psaní dokumentů prose (např. TeX nebo Markdownu) může být vhodnější použít delší délky řádků.</span><span class="sxs-lookup"><span data-stu-id="26b1d-357">Note that when writing prose documents (e.g. TeX or Markdown), it may be preferable to use longer line lengths.</span></span>
- <span data-ttu-id="26b1d-358">Poskytněte všechny relevantní matematické výrazy v části `# Description`.</span><span class="sxs-lookup"><span data-stu-id="26b1d-358">Provide all relevant mathematical expressions in the `# Description` section.</span></span>
- <span data-ttu-id="26b1d-359">Při popisu vstupů neopakuje typ každého vstupu, protože je možné ho odvodit kompilátorem a riziko zavedení nekonzistence.</span><span class="sxs-lookup"><span data-stu-id="26b1d-359">When describing inputs, do not repeat the types of each input as these can be inferred by the compiler and risk introducing inconsistency.</span></span>
- <span data-ttu-id="26b1d-360">Poskytněte příklady podle potřeby, každý v jejich `# Example` oddíl.</span><span class="sxs-lookup"><span data-stu-id="26b1d-360">Provide examples as appropriate, each in their own `# Example` section.</span></span>
- <span data-ttu-id="26b1d-361">Stručně popište každý příklad před výpisem kódu.</span><span class="sxs-lookup"><span data-stu-id="26b1d-361">Briefly describe each example before listing code.</span></span>
- <span data-ttu-id="26b1d-362">Seznamte se se všemi relevantními školními publikacemi (například dokumenty, postupy, příspěvky na blogu a alternativní implementace) v části `# References` jako seznam odkazů s odrážkami.</span><span class="sxs-lookup"><span data-stu-id="26b1d-362">Cite all relevant academic publications (e.g.: papers, proceedings, blog posts, and alternative implementations) in a `# References` section as a bulleted list of links.</span></span>
- <span data-ttu-id="26b1d-363">Ujistěte se, že pokud je to možné, všechny odkazy na citace jsou trvalé a neměnné identifikátory (DOIs nebo arXiv čísla se správou verzí).</span><span class="sxs-lookup"><span data-stu-id="26b1d-363">Ensure that, where possible, all citation links are to permanent and immutable identifiers (DOIs or versioned arXiv numbers).</span></span>
- <span data-ttu-id="26b1d-364">Pokud je operace nebo funkce v souvislosti s jinými operacemi nebo funkcemi podle funktor variant, vypíše další varianty jako odrážky v části `# See Also`.</span><span class="sxs-lookup"><span data-stu-id="26b1d-364">When an operation or function is related to other operations or functions by functor variants, list other variants as bullets in the `# See Also` section.</span></span>
- <span data-ttu-id="26b1d-365">Ponechte prázdný řádek komentáře mezi oddíly úrovně 1 (`/// #`), ale nenechávejte prázdné řádky mezi oddíly úrovně 2 (`/// ##`).</span><span class="sxs-lookup"><span data-stu-id="26b1d-365">Leave a blank comment line between level-1 (`/// #`) sections, but do not leave a blank line between level-2 (`/// ##`) sections.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="26b1d-366">Příklady</span><span class="sxs-lookup"><span data-stu-id="26b1d-366">Examples</span></span>](#tab/examples)

#### <a name=""></a><span data-ttu-id="26b1d-367">☑</span><span class="sxs-lookup"><span data-stu-id="26b1d-367">☑</span></span> ####

```
/// # Summary
/// Applies a rotation about the X-axis by a given angle.
///
///
/// # Description
/// This operation rotates a single qubit by the unitary operation
/// \begin{align}
///     R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2}.
/// \end{align}
///
/// # Input
/// ## theta
/// Angle about which the qubit is to be rotated.
/// ## qubit
/// Qubit to which the gate should be applied.
///
/// # Remarks
/// Equivalent to:
/// ```qsharp
/// R(PauliX, theta, qubit);
/// ```
///
/// # See Also
/// - Ry
/// - Rz
operation Rx(theta : Double, qubit : Qubit) : Unit
is Adj + Ctl {
    body (...) { R(PauliX, theta, qubit); }
    adjoint (...) { R(PauliX, -theta, qubit); }
}
```

***

## <a name="formatting-conventions"></a><span data-ttu-id="26b1d-368">Konvence formátování</span><span class="sxs-lookup"><span data-stu-id="26b1d-368">Formatting Conventions</span></span> ##

<span data-ttu-id="26b1d-369">Kromě výše uvedených návrhů je užitečné pomoct, aby byl kód co čitelný, aby bylo možné použít konzistentní pravidla formátování.</span><span class="sxs-lookup"><span data-stu-id="26b1d-369">In addition to the preceding suggestions, it is helpful to help make code as legible as possible to use consistent formatting rules.</span></span>
<span data-ttu-id="26b1d-370">Taková pravidla formátování podle povahy mají za následek trochu libovolné a silně silné až do osobních estetických.</span><span class="sxs-lookup"><span data-stu-id="26b1d-370">Such formatting rules by nature tend to be somewhat arbitrary and strongly up to personal aesthetics.</span></span>
<span data-ttu-id="26b1d-371">Nicméně doporučujeme, abyste zachovali konzistentní sadu formátovacích konvencí v rámci skupiny spolupracovníky a zejména u rozsáhlých projektů Q #, jako je například vývojová sada.</span><span class="sxs-lookup"><span data-stu-id="26b1d-371">Nonetheless, we recommend maintaining a consistent set of formatting conventions within a group of collaborators, and especially for large Q# projects such as the Quantum Development Kit itself.</span></span>
<span data-ttu-id="26b1d-372">Tato pravidla lze automaticky použít pomocí nástroje formátování integrovaného s kompilátorem Q #.</span><span class="sxs-lookup"><span data-stu-id="26b1d-372">These rules can be automatically applied by using the formatting tool integrated with the Q# compiler.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="26b1d-373">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="26b1d-373">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="26b1d-374">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="26b1d-374">We suggest:</span></span>

- <span data-ttu-id="26b1d-375">Místo karet pro přenositelnost použijte čtyři mezery.</span><span class="sxs-lookup"><span data-stu-id="26b1d-375">Use four spaces instead of tabs for portability.</span></span>
  <span data-ttu-id="26b1d-376">V VS Code například:</span><span class="sxs-lookup"><span data-stu-id="26b1d-376">For instance, in VS Code:</span></span>
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- <span data-ttu-id="26b1d-377">Zalomení řádku na 79 znaků, kde je to přijatelné.</span><span class="sxs-lookup"><span data-stu-id="26b1d-377">Line wrap at 79 characters where reasonable.</span></span>
- <span data-ttu-id="26b1d-378">Používejte mezery kolem binárních operátorů.</span><span class="sxs-lookup"><span data-stu-id="26b1d-378">Use spaces around binary operators.</span></span>
- <span data-ttu-id="26b1d-379">Používejte mezery na kterékoli straně dvojtečky používané pro anotace typu.</span><span class="sxs-lookup"><span data-stu-id="26b1d-379">Use spaces on either side of colons used for type annotations.</span></span>
- <span data-ttu-id="26b1d-380">Použijte jednu mezeru za čárkami použitou v poli a literálech řazené kolekce členů (např.: ve vstupech až po funkce a operace).</span><span class="sxs-lookup"><span data-stu-id="26b1d-380">Use a single space after commas used in array and tuple literals (e.g.: in inputs to functions and operations).</span></span>
- <span data-ttu-id="26b1d-381">Nepoužívejte mezery za název funkce, operace nebo UDT ani po `@` v deklaracích atributů.</span><span class="sxs-lookup"><span data-stu-id="26b1d-381">Do not use spaces after function, operation, or UDT names, or after the `@` in attribute declarations.</span></span>
- <span data-ttu-id="26b1d-382">Každá deklarace atributu by měla být na samostatném řádku.</span><span class="sxs-lookup"><span data-stu-id="26b1d-382">Each attribute declaration should be on its own line.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="26b1d-383">Příklady</span><span class="sxs-lookup"><span data-stu-id="26b1d-383">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="26b1d-384">Zlomk</span><span class="sxs-lookup"><span data-stu-id="26b1d-384">Snippet</span></span> | <span data-ttu-id="26b1d-385">Popis</span><span class="sxs-lookup"><span data-stu-id="26b1d-385">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="26b1d-386">☒</span><span class="sxs-lookup"><span data-stu-id="26b1d-386">☒</span></span> | <s>`2+3`</s> | <span data-ttu-id="26b1d-387">Používejte mezery kolem binárních operátorů.</span><span class="sxs-lookup"><span data-stu-id="26b1d-387">Use spaces around binary operators.</span></span> |
| <span data-ttu-id="26b1d-388">☒</span><span class="sxs-lookup"><span data-stu-id="26b1d-388">☒</span></span> | <s>`target:Qubit`</s> | <span data-ttu-id="26b1d-389">Používejte mezery kolem dvojtečky typu anotace.</span><span class="sxs-lookup"><span data-stu-id="26b1d-389">Use spaces around type annotation colons.</span></span> |
| <span data-ttu-id="26b1d-390">☑</span><span class="sxs-lookup"><span data-stu-id="26b1d-390">☑</span></span> | `Example(a, b, c)` | <span data-ttu-id="26b1d-391">Položky ve vstupní řazené kolekci členů jsou pro čitelnosti správně rozmístěny.</span><span class="sxs-lookup"><span data-stu-id="26b1d-391">Items in input tuple are correctly spaced for readability.</span></span> |
| <span data-ttu-id="26b1d-392">☒</span><span class="sxs-lookup"><span data-stu-id="26b1d-392">☒</span></span> | <s>`Example (a, b, c)`</s> | <span data-ttu-id="26b1d-393">Mezery by měly být potlačeny za názvy funkcí, operací nebo UDT.</span><span class="sxs-lookup"><span data-stu-id="26b1d-393">Spaces should be suppressed after function, operation, or UDT names.</span></span> |

***

