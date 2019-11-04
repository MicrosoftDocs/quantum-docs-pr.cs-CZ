---
title: 'Průvodce stylem Q # | Microsoft Docs'
description: 'Průvodce stylem Q #'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: 4050e2ee9e516aed7a8ba1398792562926808ee0
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463322"
---
# <a name="q-style-guide"></a><span data-ttu-id="5572e-103">Průvodce stylem Q #</span><span class="sxs-lookup"><span data-stu-id="5572e-103">Q# Style Guide</span></span> #
## <a name="general-conventions"></a><span data-ttu-id="5572e-104">Obecné konvence</span><span class="sxs-lookup"><span data-stu-id="5572e-104">General Conventions</span></span> ##

<span data-ttu-id="5572e-105">Konvence navržené v této příručce jsou určené k tomu, aby usnadnily čtení a pochopení programů a knihoven ve službě Q #.</span><span class="sxs-lookup"><span data-stu-id="5572e-105">The conventions suggested in this guide are intended to help make programs and libraries written in Q# easier to read and understand.</span></span>

## <a name="guidance"></a><span data-ttu-id="5572e-106">Pokyny</span><span class="sxs-lookup"><span data-stu-id="5572e-106">Guidance</span></span>

<span data-ttu-id="5572e-107">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="5572e-107">We suggest:</span></span>

- <span data-ttu-id="5572e-108">Nikdy nepoužívejte konvenci, pokud to neprovedete záměrně za účelem poskytnutí čitelnějšího a srozumitelného kódu pro uživatele.</span><span class="sxs-lookup"><span data-stu-id="5572e-108">Never disregard a convention unless you’re doing so intentionally in order to provide more readable and understandable code for your users.</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="5572e-109">Zásady vytváření názvů</span><span class="sxs-lookup"><span data-stu-id="5572e-109">Naming Conventions</span></span> ##

<span data-ttu-id="5572e-110">V rámci nabídky vývojové sady pro práci s více operačními společnostmi usilujeme o názvy funkcí a operací, které vývojářům usnadňují psaní programů, které se snadno čtou a které minimalizují neočekávaně.</span><span class="sxs-lookup"><span data-stu-id="5572e-110">In offering the Quantum Development Kit, we strive for function and operation names that help quantum developers write programs that are easy to read and that minimize surprise.</span></span>
<span data-ttu-id="5572e-111">Důležitou součástí toho je, že když vybíráme názvy pro funkce, operace a typy, vytvoříme *slovník* , který programátoři používají pro vyjádření základních konceptů. Díky našim možnostem vám pomůžeme nebo je bráníme v jejich úsilí, aby mohli jasně komunikovat.</span><span class="sxs-lookup"><span data-stu-id="5572e-111">An important part of that is that when we choose names for functions, operations, and types, we are establishing the *vocabulary* that programmers use to express quantum concepts; with our choices, we either help or hinder them in their effort to clearly communicate.</span></span>
<span data-ttu-id="5572e-112">Tím se na nás zaručí zodpovědnost, aby se zajistilo, že názvy, které zavádíme, představují srozumitelnější místo neprůhlednosti.</span><span class="sxs-lookup"><span data-stu-id="5572e-112">This places a responsibility on us to make sure that the names we introduce offer clarity rather than obscurity.</span></span>
<span data-ttu-id="5572e-113">V této části podrobně uvádíme, jak splňujeme tuto povinnost z hlediska explicitních pokynů, abychom nám mohli co nejlépe udělat komunitou pro vývoj Q.</span><span class="sxs-lookup"><span data-stu-id="5572e-113">In this section, we detail how we meet this obligation in terms of explicit guidance that helps us do the best by the Q# development community.</span></span>

### <a name="operations-and-functions"></a><span data-ttu-id="5572e-114">Operace a funkce</span><span class="sxs-lookup"><span data-stu-id="5572e-114">Operations and Functions</span></span> ###

<span data-ttu-id="5572e-115">Jedna z prvních věcí, které by měl název vytvořit, je, zda daný symbol představuje funkci nebo operaci.</span><span class="sxs-lookup"><span data-stu-id="5572e-115">One of the first things that a name should establish is whether a given symbol represents a function or an operation.</span></span>
<span data-ttu-id="5572e-116">Rozdíl mezi funkcemi a operacemi je zásadní pro porozumění způsobu, jakým se chová blok kódu.</span><span class="sxs-lookup"><span data-stu-id="5572e-116">The difference between functions and operations is critical to understanding how a block of code behaves.</span></span>
<span data-ttu-id="5572e-117">Pro sdělování rozdílů mezi funkcemi a operacemi pro uživatele spoléháme na to, že modely Q # využívají vedlejší účinky na tyto operace.</span><span class="sxs-lookup"><span data-stu-id="5572e-117">To communicate the distinction between functions and operations to users, we rely on that Q# models quantum operations through the use of side effects.</span></span>
<span data-ttu-id="5572e-118">To znamená, že operace *dělá* něco.</span><span class="sxs-lookup"><span data-stu-id="5572e-118">That is, an operation *does* something.</span></span>

<span data-ttu-id="5572e-119">Naopak funkce popisují matematické vztahy mezi daty.</span><span class="sxs-lookup"><span data-stu-id="5572e-119">By contrast, functions describe the mathematical relationships between data.</span></span>
<span data-ttu-id="5572e-120">Výraz `Sin(PI() / 2.0)` *je* `1.0`a nevyjadřuje žádné informace o stavu programu nebo jeho qubits.</span><span class="sxs-lookup"><span data-stu-id="5572e-120">The expression `Sin(PI() / 2.0)` *is* `1.0`, and implies nothing about the state of a program or its qubits.</span></span>

<span data-ttu-id="5572e-121">Sumarizace, operace se provádí v době, kdy jsou funkce věcí.</span><span class="sxs-lookup"><span data-stu-id="5572e-121">Summarizing, operations do things while functions are things.</span></span>
<span data-ttu-id="5572e-122">Tento rozdíl naznačuje, že pojmenování operací jako operací a funkcí jako podstatných jmen.</span><span class="sxs-lookup"><span data-stu-id="5572e-122">This distinction suggests that we name operations as verbs and functions as nouns.</span></span>

> [!NOTE]
> <span data-ttu-id="5572e-123">Když je deklarován uživatelsky definovaný typ, je nová funkce, která vytváří instance daného typu, implicitně definována současně.</span><span class="sxs-lookup"><span data-stu-id="5572e-123">When a user-defined type is declared, a new function that constructs instances of that type is implicitly defined at the same time.</span></span>
> <span data-ttu-id="5572e-124">Z této perspektivy by měly být uživatelsky definované typy pojmenovány jako podstatná jména, aby samotný typ i funkce konstruktoru měly konzistentní názvy.</span><span class="sxs-lookup"><span data-stu-id="5572e-124">From that perspective, user-defined types should be named as nouns so that both the type itself and the constructor function have consistent names.</span></span>

<span data-ttu-id="5572e-125">Tam, kde je to rozumné, zajistěte, aby názvy operací začaly slovesy, které jasně indikují účinek prováděný operací.</span><span class="sxs-lookup"><span data-stu-id="5572e-125">Where reasonable, ensure that operation names begin with verbs that clearly indicate the effect taken by the operation.</span></span>
<span data-ttu-id="5572e-126">Například:</span><span class="sxs-lookup"><span data-stu-id="5572e-126">For example:</span></span>

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

<span data-ttu-id="5572e-127">Jeden případ, který zachovává zvláštní zmínku, je v případě, že operace přebírá jinou operaci jako vstup a volá ji.</span><span class="sxs-lookup"><span data-stu-id="5572e-127">One case that deserves special mention is when an operation takes another operation as input and calls it.</span></span>
<span data-ttu-id="5572e-128">V takových případech není akce prováděná vstupní operací jasná, když je definovaná vnější operace, takže není správná operace okamžitě jasná.</span><span class="sxs-lookup"><span data-stu-id="5572e-128">In such cases, the action taken by the input operation is not clear when the outer operation is defined, such that the right verb is not immediately clear.</span></span>
<span data-ttu-id="5572e-129">Jako v `ApplyIf`, `ApplyToEach`a `ApplyToFirst`doporučujeme použít příkaz `Apply`.</span><span class="sxs-lookup"><span data-stu-id="5572e-129">We recommend the verb `Apply`, as in `ApplyIf`, `ApplyToEach`, and `ApplyToFirst`.</span></span>
<span data-ttu-id="5572e-130">V tomto případě mohou být užitečné i jiné akce, jako v `IterateThroughCartesianPower`.</span><span class="sxs-lookup"><span data-stu-id="5572e-130">Other verbs may be useful in this case as well, as in `IterateThroughCartesianPower`.</span></span>

| <span data-ttu-id="5572e-131">Operace</span><span class="sxs-lookup"><span data-stu-id="5572e-131">Verb</span></span> | <span data-ttu-id="5572e-132">Očekávaný efekt</span><span class="sxs-lookup"><span data-stu-id="5572e-132">Expected Effect</span></span> |
| ---- | ------ |
| <span data-ttu-id="5572e-133">Použít</span><span class="sxs-lookup"><span data-stu-id="5572e-133">Apply</span></span> | <span data-ttu-id="5572e-134">Nazývá se operace zadaná jako vstup.</span><span class="sxs-lookup"><span data-stu-id="5572e-134">An operation provided as input is called</span></span> |
| <span data-ttu-id="5572e-135">Assert</span><span class="sxs-lookup"><span data-stu-id="5572e-135">Assert</span></span> | <span data-ttu-id="5572e-136">Hypotéza o výsledku možného měření doby využívání se kontroluje simulátorem.</span><span class="sxs-lookup"><span data-stu-id="5572e-136">A hypothesis about the outcome of a possible quantum measurement is checked by a simulator</span></span> |
| <span data-ttu-id="5572e-137">Ocenění</span><span class="sxs-lookup"><span data-stu-id="5572e-137">Estimate</span></span> | <span data-ttu-id="5572e-138">Vrátí se klasická hodnota, která představuje odhad vykreslený z jedné nebo více měření.</span><span class="sxs-lookup"><span data-stu-id="5572e-138">A classical value is returned, representing an estimate drawn from one or more measurements</span></span> |
| <span data-ttu-id="5572e-139">Measure</span><span class="sxs-lookup"><span data-stu-id="5572e-139">Measure</span></span> | <span data-ttu-id="5572e-140">Měří se měření po sobě a výsledek se vrátí uživateli.</span><span class="sxs-lookup"><span data-stu-id="5572e-140">A quantum measurement is performed, and its result is returned to the user</span></span> |
| <span data-ttu-id="5572e-141">Připravit</span><span class="sxs-lookup"><span data-stu-id="5572e-141">Prepare</span></span> | <span data-ttu-id="5572e-142">Daný registr qubits se inicializuje do určitého stavu.</span><span class="sxs-lookup"><span data-stu-id="5572e-142">A given register of qubits is initialized into a particular state</span></span> |
| <span data-ttu-id="5572e-143">Ukázka</span><span class="sxs-lookup"><span data-stu-id="5572e-143">Sample</span></span> | <span data-ttu-id="5572e-144">Z nějaké distribuce se náhodně vrátí klasická hodnota.</span><span class="sxs-lookup"><span data-stu-id="5572e-144">A classical value is returned at random from some distribution</span></span> |

<span data-ttu-id="5572e-145">V případě funkcí doporučujeme vyhnout se použití sloves ve prospěch běžných podstatných jmen (viz doprovodné materiály o řádných podstatných jmenách níže) nebo adjektiva:</span><span class="sxs-lookup"><span data-stu-id="5572e-145">For functions, we suggest avoiding the use of verbs in favor of common nouns (see guidance on proper nouns below) or adjectives:</span></span>

- `ConstantArray`
- `Head`
- `LookupFunction`

<span data-ttu-id="5572e-146">Konkrétně v téměř všech případech doporučujeme použít dřívější participles, kde je to vhodné k označení toho, že název funkce je důrazně připojen k akci nebo vedlejšímu účinku jinde v programu pro práci s více událostmi.</span><span class="sxs-lookup"><span data-stu-id="5572e-146">In particular, in almost all cases, we suggest using past participles where appropriate to indicate that a function name is strongly connected to an action or side effect elsewhere in a quantum program.</span></span>
<span data-ttu-id="5572e-147">Například `ControlledOnInt` používá participle formuláře příkazu "Control" k označení toho, že funkce funguje jako adjektivum pro úpravu svého argumentu.</span><span class="sxs-lookup"><span data-stu-id="5572e-147">For example,  `ControlledOnInt` uses the part participle form of the verb "control" to indicate that the function acts as an adjective to modify its argument.</span></span>
<span data-ttu-id="5572e-148">Tento název má další výhody, které odpovídají sémantikě předdefinovaných `Controlled` funktor, jak je popsáno dále níže.</span><span class="sxs-lookup"><span data-stu-id="5572e-148">This name has the additional benefit of matching the semantics of the built-in `Controlled` functor, as discussed further below.</span></span>
<span data-ttu-id="5572e-149">Obdobně lze použít _substantivum agenta_ k vytvoření funkce a názvů UDT z názvů operací, jako v případě názvu `Encoder` pro UDT, který je silně spojen s `Encode`.</span><span class="sxs-lookup"><span data-stu-id="5572e-149">Similarly, _agent nouns_ can be used to construct function and UDT names from operation names, as in the case of the name `Encoder` for a UDT that is strongly associated with `Encode`.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="5572e-150">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="5572e-150">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="5572e-151">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="5572e-151">We suggest:</span></span>

- <span data-ttu-id="5572e-152">Pro názvy operací použijte slovesa.</span><span class="sxs-lookup"><span data-stu-id="5572e-152">Use verbs for operation names.</span></span>
- <span data-ttu-id="5572e-153">Pro názvy funkcí použijte podstatná jména nebo jména.</span><span class="sxs-lookup"><span data-stu-id="5572e-153">Use nouns or adjectives for function names.</span></span>
- <span data-ttu-id="5572e-154">Používejte podstatná jména pro uživatelsky definované typy a atributy.</span><span class="sxs-lookup"><span data-stu-id="5572e-154">Use nouns for user-defined types and attributes.</span></span>
- <span data-ttu-id="5572e-155">Pro všechny názvy, které lze volat, použijte `CamelCase` ve silném předvolbách na `pascalCase`, `snake_case`nebo `ANGRY_CASE`.</span><span class="sxs-lookup"><span data-stu-id="5572e-155">For all callable names, use `CamelCase` in strong preference to `pascalCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="5572e-156">Konkrétně se ujistěte, že názvy, které se budou volat, začínají velkým písmenem.</span><span class="sxs-lookup"><span data-stu-id="5572e-156">In particular, ensure that callable names start with uppercase letters.</span></span>
- <span data-ttu-id="5572e-157">U všech místních proměnných použijte `pascalCase` v případě silné Předvolby na `CamelCase`, `snake_case`nebo `ANGRY_CASE`.</span><span class="sxs-lookup"><span data-stu-id="5572e-157">For all local variables, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="5572e-158">Konkrétně zajistěte, aby místní proměnné byly začínat malými písmeny.</span><span class="sxs-lookup"><span data-stu-id="5572e-158">In particular, ensure that local variables start with lowercase letters.</span></span>
- <span data-ttu-id="5572e-159">Vyhněte se použití podtržítek `_` v názvech funkcí a operací; v případě potřeby dalších úrovní hierarchie použijte obory názvů a aliasy oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="5572e-159">Avoid the use of underscores `_` in function and operation names; where additional levels of hierarchy are needed, use namespaces and namespace aliases.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="5572e-160">Příklady</span><span class="sxs-lookup"><span data-stu-id="5572e-160">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="5572e-161">Name (Název)</span><span class="sxs-lookup"><span data-stu-id="5572e-161">Name</span></span> | <span data-ttu-id="5572e-162">Popis</span><span class="sxs-lookup"><span data-stu-id="5572e-162">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="5572e-163">☑</span><span class="sxs-lookup"><span data-stu-id="5572e-163">☑</span></span> | `operation ReflectAboutStart` | <span data-ttu-id="5572e-164">Zrušením použití příkazu ("reflektování") označíte účinek operace.</span><span class="sxs-lookup"><span data-stu-id="5572e-164">Clear use of a verb ("reflect") to indicate the effect of the operation.</span></span> |
| <span data-ttu-id="5572e-165">☒</span><span class="sxs-lookup"><span data-stu-id="5572e-165">☒</span></span> | <s>`operation XRotation`</s> | <span data-ttu-id="5572e-166">Místo operace použijte funkci navrhuje fráze substantivum.</span><span class="sxs-lookup"><span data-stu-id="5572e-166">Use of noun phrase suggests function, rather than operation.</span></span> |
| <span data-ttu-id="5572e-167">☒</span><span class="sxs-lookup"><span data-stu-id="5572e-167">☒</span></span> | <s>`operation search_oracle`</s> | <span data-ttu-id="5572e-168">Použití `snake_case` je v rozporu s zápisem Q #.</span><span class="sxs-lookup"><span data-stu-id="5572e-168">Use of `snake_case` contravenes Q# notation.</span></span> |
| <span data-ttu-id="5572e-169">☒</span><span class="sxs-lookup"><span data-stu-id="5572e-169">☒</span></span> | <s>`operation Search_Oracle`</s> | <span data-ttu-id="5572e-170">Použití podtržítek s podtržítkem pro název operace je v rozporu s zápisem Q #.</span><span class="sxs-lookup"><span data-stu-id="5572e-170">Use of underscores internal to operation name contravenes Q# notation.</span></span> |
| <span data-ttu-id="5572e-171">☑</span><span class="sxs-lookup"><span data-stu-id="5572e-171">☑</span></span> | `function StatePreparationOracle` | <span data-ttu-id="5572e-172">Použití fráze substantivum naznačuje, že funkce vrátí operaci.</span><span class="sxs-lookup"><span data-stu-id="5572e-172">Use of noun phrase suggests that the function returns an operation.</span></span> |
| <span data-ttu-id="5572e-173">☑</span><span class="sxs-lookup"><span data-stu-id="5572e-173">☑</span></span> | `function EqualityFact` | <span data-ttu-id="5572e-174">Zrušte použití podstatného jména ("fakt"), abyste označili, že se jedná o funkci, ale jeho jméno.</span><span class="sxs-lookup"><span data-stu-id="5572e-174">Clear use of noun ("fact") to indicate that this is a function, while the adjective.</span></span> |
| <span data-ttu-id="5572e-175">☒</span><span class="sxs-lookup"><span data-stu-id="5572e-175">☒</span></span> | <s>`function GetRotationAngles`</s> | <span data-ttu-id="5572e-176">Použití příkazu ("Get") naznačuje, že se jedná o operaci.</span><span class="sxs-lookup"><span data-stu-id="5572e-176">Use of verb ("get") suggests that this is an operation.</span></span> |
| <span data-ttu-id="5572e-177">☑</span><span class="sxs-lookup"><span data-stu-id="5572e-177">☑</span></span> | `newtype GeneratorTerm` | <span data-ttu-id="5572e-178">Použití fráze substantivum jasně odkazuje na výsledek volání konstruktoru UDT.</span><span class="sxs-lookup"><span data-stu-id="5572e-178">Use of noun phrase clearly refers to the result of calling the UDT constructor.</span></span> |
| <span data-ttu-id="5572e-179">☒</span><span class="sxs-lookup"><span data-stu-id="5572e-179">☒</span></span> | <s>`@Attribute() newtype RunOnce()`</s> | <span data-ttu-id="5572e-180">Použití příkazového fráze navrhuje, že konstruktor UDT je operace.</span><span class="sxs-lookup"><span data-stu-id="5572e-180">Use of verb phrase suggests that the UDT constructor is an operation.</span></span> |
| <span data-ttu-id="5572e-181">☑</span><span class="sxs-lookup"><span data-stu-id="5572e-181">☑</span></span> | `@Attribute() newtype Deprecated(Reason : String)` | <span data-ttu-id="5572e-182">Použití fráze substantivum komunikuje s použitím atributu.</span><span class="sxs-lookup"><span data-stu-id="5572e-182">Use of noun phrase communicates the use of the attribute.</span></span> |

***

### <a name="shorthand-and-abbreviations"></a><span data-ttu-id="5572e-183">Zkratky a zkratky</span><span class="sxs-lookup"><span data-stu-id="5572e-183">Shorthand and Abbreviations</span></span> ###

<span data-ttu-id="5572e-184">Výše uvedená doporučení se neshoduje, existuje mnoho forem zkrácených ve formě běžných a pervasivech použití ve výpočetním prostředí.</span><span class="sxs-lookup"><span data-stu-id="5572e-184">The above advice notwithstanding, there are many forms of shorthand that see common and pervasive use in quantum computing.</span></span>
<span data-ttu-id="5572e-185">Doporučujeme používat existující a běžnou zkrácený popis, kde existuje, zejména pro operace, které jsou vnitřní pro provoz cílového počítače.</span><span class="sxs-lookup"><span data-stu-id="5572e-185">We suggest using existing and common shorthand where it exists, especially for operations that are intrinsic to the operation of a target machine.</span></span>
<span data-ttu-id="5572e-186">Například zvolíme název `X` místo `ApplyX`a `Rz` místo `RotateAboutZ`.</span><span class="sxs-lookup"><span data-stu-id="5572e-186">For example, we choose the name `X` instead of `ApplyX`, and `Rz` instead of `RotateAboutZ`.</span></span>
<span data-ttu-id="5572e-187">Při použití takových zkratek by názvy operací měly být všechna velká (např.: `MAJ`).</span><span class="sxs-lookup"><span data-stu-id="5572e-187">When using such shorthand, operation names should be all uppercase (e.g.: `MAJ`).</span></span>

<span data-ttu-id="5572e-188">Při použití této konvence v případě běžně používaných akronymů a initialisms, jako je například "QFT", se vyžaduje určitá péče.</span><span class="sxs-lookup"><span data-stu-id="5572e-188">Some care is required when applying this convention in the case of commonly used acronyms and initialisms such as "QFT" for "quantum Fourier transform."</span></span>
<span data-ttu-id="5572e-189">Pro použití akronymů a initialisms v úplných názvech doporučujeme následující obecné konvence rozhraní .NET, které předepisuje, že:</span><span class="sxs-lookup"><span data-stu-id="5572e-189">We suggest following general .NET conventions for the use of acronyms and initialisms in full names, which prescribe that:</span></span>

- <span data-ttu-id="5572e-190">zkratky se dvěma písmeny a initialisms se nazývají v horním případě (např.: `BE` pro "big-endian").</span><span class="sxs-lookup"><span data-stu-id="5572e-190">two-letter acronyms and initialisms are named in upper case (e.g.: `BE` for "big-endian"),</span></span>
- <span data-ttu-id="5572e-191">všechny delší akronymy a initialisms se pojmenují v `CamelCase` (např.: `Qft` pro "dobu" s "Fourierova transformace").</span><span class="sxs-lookup"><span data-stu-id="5572e-191">all longer acronyms and initialisms are named in `CamelCase` (e.g.: `Qft` for "quantum Fourier transform")</span></span>

<span data-ttu-id="5572e-192">Proto operace implementující QFT může být buď volána `QFT` jako zkrácený, nebo jako `ApplyQft`zapsána jako.</span><span class="sxs-lookup"><span data-stu-id="5572e-192">Thus, an operation implementing the QFT could either be called `QFT` as shorthand, or written out as `ApplyQft`.</span></span>

<span data-ttu-id="5572e-193">Pro obzvlášť používané operace a funkce může být vhodné zadat zkrácený název jako _alias_ pro delší tvar:</span><span class="sxs-lookup"><span data-stu-id="5572e-193">For particularly commonly used operations and functions, it may be desirable to provide a shorthand name as an _alias_ for a longer form:</span></span>

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidancetabguidance"></a>[<span data-ttu-id="5572e-194">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="5572e-194">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="5572e-195">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="5572e-195">We suggest:</span></span>

- <span data-ttu-id="5572e-196">V případě potřeby zvažte běžně přijatelné a často používané zkrácený název.</span><span class="sxs-lookup"><span data-stu-id="5572e-196">Consider commonly accepted and widely used shorthand names when appropriate.</span></span>
- <span data-ttu-id="5572e-197">Pro zkrácený tvar použijte velká písmena.</span><span class="sxs-lookup"><span data-stu-id="5572e-197">Use uppercase for shorthand.</span></span>
- <span data-ttu-id="5572e-198">Používejte velká písmena pro krátká (dvě písmena) zkratky a initialisms.</span><span class="sxs-lookup"><span data-stu-id="5572e-198">Use uppercase for short (two-letter) acronyms and initialisms.</span></span>
- <span data-ttu-id="5572e-199">Použijte `CamelCase` pro delší (tři nebo více písmen) a initialisms.</span><span class="sxs-lookup"><span data-stu-id="5572e-199">Use `CamelCase` for longer (three or more letter) acronyms and initialisms.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="5572e-200">Příklady</span><span class="sxs-lookup"><span data-stu-id="5572e-200">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="5572e-201">Name (Název)</span><span class="sxs-lookup"><span data-stu-id="5572e-201">Name</span></span> | <span data-ttu-id="5572e-202">Popis</span><span class="sxs-lookup"><span data-stu-id="5572e-202">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="5572e-203">☑</span><span class="sxs-lookup"><span data-stu-id="5572e-203">☑</span></span> | `X` | <span data-ttu-id="5572e-204">Dobře srozumitelná zkrácený příkaz pro použití transformace $X $</span><span class="sxs-lookup"><span data-stu-id="5572e-204">Well-understood shorthand for "apply an $X$ transformation"</span></span> |
| <span data-ttu-id="5572e-205">☑</span><span class="sxs-lookup"><span data-stu-id="5572e-205">☑</span></span> | `CNOT` | <span data-ttu-id="5572e-206">Dobře srozumitelná zkrácená zkratka pro "řízená – ne"</span><span class="sxs-lookup"><span data-stu-id="5572e-206">Well-understood shorthand for "controlled-NOT"</span></span> |
| <span data-ttu-id="5572e-207">☒</span><span class="sxs-lookup"><span data-stu-id="5572e-207">☒</span></span> | <s>`Cnot`</s> | <span data-ttu-id="5572e-208">Zkrácený odkaz by neměl být v `CamelCase`.</span><span class="sxs-lookup"><span data-stu-id="5572e-208">Shorthand should not be in `CamelCase`.</span></span> |
| <span data-ttu-id="5572e-209">☑</span><span class="sxs-lookup"><span data-stu-id="5572e-209">☑</span></span> | `ApplyQft` | <span data-ttu-id="5572e-210">Běžným počátečním názvem "QFT" se jeví jako součást formátu dlouhého formátu.</span><span class="sxs-lookup"><span data-stu-id="5572e-210">Common initialism "QFT" appears as a part of a long-form name.</span></span> |
| <span data-ttu-id="5572e-211">☑</span><span class="sxs-lookup"><span data-stu-id="5572e-211">☑</span></span> | `QFT` | <span data-ttu-id="5572e-212">Common initialer "QFT" se zobrazuje jako součást zkrácený název.</span><span class="sxs-lookup"><span data-stu-id="5572e-212">Common initialism "QFT" appears as a part of a shorthand name.</span></span> |



***


### <a name="proper-nouns-in-names"></a><span data-ttu-id="5572e-213">Správná jména v názvech</span><span class="sxs-lookup"><span data-stu-id="5572e-213">Proper Nouns in Names</span></span> ###

<span data-ttu-id="5572e-214">V rámci fyziky je běžné pojmenování po první osobě, která o nich je publikovaná, většina nephysicistsch není obeznámená s názvy všech a všech historií.</span><span class="sxs-lookup"><span data-stu-id="5572e-214">While in physics it is common to name things after the first person to publish about them, most non-physicists aren’t familiar with everyone’s names and all of the history.</span></span>
<span data-ttu-id="5572e-215">Velmi silně spoléhá na konvence pojmenování z fyziky, takže by se měla zabývat značnou překážkou vstupu, protože uživatelé z jiných pozadí se musí seznámit s velkým počtem zdánlivě neprůhledných názvů, aby mohli používat běžné operace a koncepty.</span><span class="sxs-lookup"><span data-stu-id="5572e-215">Relying too heavily on naming conventions from physics can thus put up a substantial barrier to entry, as users from other backgrounds must learn a large number of seemingly opaque names in order to use common operations and concepts.</span></span>
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
<span data-ttu-id="5572e-216">Proto doporučujeme, abyste při každém rozumném a běžném výskytu, který popisuje pojem koncept, přijali v rámci silné Předvolby na řádné podstatné jméno, které popisují historii publikace konceptu.</span><span class="sxs-lookup"><span data-stu-id="5572e-216">Thus, we recommend that wherever reasonable, common nouns that describe a concept be adopted in strong preference to proper nouns that describe the publication history of a concept.</span></span>
<span data-ttu-id="5572e-217">Jako konkrétní příklad se v rámci akademické literatury často označují samostatně kontrolované SWAPy a dvakrát kontrolované operace, ale v rámci Fredkin se identifikují hlavně jako `CSWAP` a `CCNOT`.</span><span class="sxs-lookup"><span data-stu-id="5572e-217">As a particular example, the singly controlled SWAP and doubly controlled NOT operations are often called the "Fredkin" and "Toffoli" operations in academic literature, but are identified in Q# primarily as `CSWAP` and `CCNOT`.</span></span>
<span data-ttu-id="5572e-218">V obou případech komentáře k rozhraní API poskytují synonymum názvů na základě správných podstatných jmen a spolu se všemi příslušnými citacemi.</span><span class="sxs-lookup"><span data-stu-id="5572e-218">In both cases, the API documentation comments provide synonymous names based on proper nouns, along with all appropriate citations.</span></span>

<span data-ttu-id="5572e-219">Tato předvolba je obzvláště důležitá vzhledem k tomu, že některé použití řádných podstatných jmen bude vždy nutné – Q # následuje po sadě klasických jazyků, například a odkazuje na `Bool` typy v odkazu na logickou logiku, která je zase pojmenována za akceptovatelné. z logického typu Jiří.</span><span class="sxs-lookup"><span data-stu-id="5572e-219">This preference is especially important given that some usage of proper nouns will always be necessary — Q# follows the tradition set by many classical languages, for instance, and refers to `Bool` types in reference to Boolean logic, which is in turn named in honor of George Boole.</span></span>
<span data-ttu-id="5572e-220">Několik základních principů je obdobně pojmenováno podobným způsobem, včetně typu `Pauli` integrovaného do jazyka Q #.</span><span class="sxs-lookup"><span data-stu-id="5572e-220">A few quantum concepts similarly are named in a similar fashion, including the `Pauli` type built-in to the Q# language.</span></span>
<span data-ttu-id="5572e-221">Minimalizací použití řádných podstatných jmen, kde takové použití není nezbytné, snižujeme dopad na to, kde nelze rozumně obejít řádná podstatná jména.</span><span class="sxs-lookup"><span data-stu-id="5572e-221">By minimizing the usage of proper nouns where such usage is not essential, we reduce the impact where proper nouns cannot be reasonably avoided.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="5572e-222">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="5572e-222">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="5572e-223">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="5572e-223">We suggest:</span></span>

- <span data-ttu-id="5572e-224">Vyhněte se použití řádných podstatných jmen v názvech.</span><span class="sxs-lookup"><span data-stu-id="5572e-224">Avoid the use of proper nouns in names.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="5572e-225">Příklady</span><span class="sxs-lookup"><span data-stu-id="5572e-225">Examples</span></span>](#tab/examples)

***

### <a name="type-conversions"></a><span data-ttu-id="5572e-226">Převody typu</span><span class="sxs-lookup"><span data-stu-id="5572e-226">Type Conversions</span></span> ###

<span data-ttu-id="5572e-227">Vzhledem k tomu, že Q # je silně a staticky typovaného jazyka, hodnota jednoho typu může být použita pouze jako hodnota jiného typu pomocí explicitního volání funkce pro převod typu.</span><span class="sxs-lookup"><span data-stu-id="5572e-227">Since Q# is a strongly and staticly typed language, a value of one type can only be used as a value of another type by using an explicit call to a type conversion function.</span></span>
<span data-ttu-id="5572e-228">To je v kontrastu s jazyky, které umožňují hodnotám měnit typy implicitně (např.: povýšení typu) nebo prostřednictvím přetypování.</span><span class="sxs-lookup"><span data-stu-id="5572e-228">This is in contrast to languages which allow for values to change types implicitly (e.g.: type promotion), or through casting.</span></span>
<span data-ttu-id="5572e-229">Výsledkem je, že funkce pro převod typu hrají důležitou roli ve vývoji knihovny Q # a sestávají z nich jedno z častých rozhodnutí o pojmenování.</span><span class="sxs-lookup"><span data-stu-id="5572e-229">As a result, type conversion functions play an important role in Q# library development, and comprise one of the more commonly encountered decisions about naming.</span></span>
<span data-ttu-id="5572e-230">Upozorňujeme však, že protože převody typu jsou vždycky _deterministické_, můžou být zapsány jako funkce a tak do výše uvedených rad.</span><span class="sxs-lookup"><span data-stu-id="5572e-230">We note, however, that since type conversions are always _deterministic_, they can be written as functions and thus fall under the advice above.</span></span>
<span data-ttu-id="5572e-231">Konkrétně doporučujeme, aby funkce pro převod typu neměly být nikdy pojmenovány jako slovesa (např.: `ConvertToX`) nebo příznakem příznaku příznaku (`ToX`), ale měly by se pojmenovat jako předpozice "adjektivum", které označují zdrojové a cílové typy (`XAsY`).</span><span class="sxs-lookup"><span data-stu-id="5572e-231">In particular, we suggest that type conversion functions should never be named as verbs (e.g.: `ConvertToX`) or adverb prepositional phrases (`ToX`), but should be named as adjective prepositional phrases that indicate the source and destination types (`XAsY`).</span></span>
<span data-ttu-id="5572e-232">Při výpisu typů polí v názvech funkcí konverze typu doporučujeme zkrácený `Arr`.</span><span class="sxs-lookup"><span data-stu-id="5572e-232">When listing array types in type conversion function names, we recommend the shorthand `Arr`.</span></span>
<span data-ttu-id="5572e-233">Blokování výjimečných okolností, doporučujeme, aby všechny funkce pro převod typů byly pojmenovány pomocí `As`, aby je bylo možné rychle identifikovat.</span><span class="sxs-lookup"><span data-stu-id="5572e-233">Barring exceptional circumstances, we recommend that all type conversion functions be named using `As` so that they can be quickly identified.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="5572e-234">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="5572e-234">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="5572e-235">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="5572e-235">We suggest:</span></span>

- <span data-ttu-id="5572e-236">Pokud funkce převede hodnotu typu `X` na hodnotu typu `Y`, použijte buď název `AsY` nebo `XAsY`.</span><span class="sxs-lookup"><span data-stu-id="5572e-236">If a function converts a value of type `X` to a value of type `Y`, use either the name `AsY` or `XAsY`.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="5572e-237">Příklady</span><span class="sxs-lookup"><span data-stu-id="5572e-237">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="5572e-238">Name (Název)</span><span class="sxs-lookup"><span data-stu-id="5572e-238">Name</span></span> | <span data-ttu-id="5572e-239">Popis</span><span class="sxs-lookup"><span data-stu-id="5572e-239">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="5572e-240">☒</span><span class="sxs-lookup"><span data-stu-id="5572e-240">☒</span></span> | <s>`ToDouble`</s> | <span data-ttu-id="5572e-241">Výsledkem předpozice "do" je příkazová fráze, která značí operaci a nikoli funkci.</span><span class="sxs-lookup"><span data-stu-id="5572e-241">The preposition "to" results in a verb phrase, indicating an operation and not a function.</span></span> |
| <span data-ttu-id="5572e-242">☒</span><span class="sxs-lookup"><span data-stu-id="5572e-242">☒</span></span> | <s>`AsDouble`</s> | <span data-ttu-id="5572e-243">Typ vstupu není jasný od názvu funkce.</span><span class="sxs-lookup"><span data-stu-id="5572e-243">The input type is not clear from the function name.</span></span> |
| <span data-ttu-id="5572e-244">☒</span><span class="sxs-lookup"><span data-stu-id="5572e-244">☒</span></span> | <s>`PauliArrFromBoolArr`</s> | <span data-ttu-id="5572e-245">Vstupní a výstupní typy se zobrazí v nesprávném pořadí.</span><span class="sxs-lookup"><span data-stu-id="5572e-245">The input and output types appear in the wrong order.</span></span> |
| <span data-ttu-id="5572e-246">☑</span><span class="sxs-lookup"><span data-stu-id="5572e-246">☑</span></span> | `ResultArrAsBoolArr` | <span data-ttu-id="5572e-247">Vstupní typy i výstupní typy jsou jasné.</span><span class="sxs-lookup"><span data-stu-id="5572e-247">Both the input types and output types are clear.</span></span> |

***

### <a name="private-or-internal-names"></a><span data-ttu-id="5572e-248">Privátní nebo interní názvy</span><span class="sxs-lookup"><span data-stu-id="5572e-248">Private or Internal Names</span></span> ###

<span data-ttu-id="5572e-249">V mnoha případech je název určený výhradně pro použití interního pro knihovnu nebo projekt a není zaručenou součástí rozhraní API nabízeného knihovnou.</span><span class="sxs-lookup"><span data-stu-id="5572e-249">In many cases, a name is intended strictly for use internal to a library or project, and is not a guaranteed part of the API offered by a library.</span></span>
<span data-ttu-id="5572e-250">Je vhodné jasně označit, že se jedná o případ, kdy se pojmenují funkce a operace, aby byly náhodné závislosti na kódu pouze v interním kódu.</span><span class="sxs-lookup"><span data-stu-id="5572e-250">It is helpful to clearly indicate that this is the case when naming functions and operations so that accidental dependencies on internal-only code are made obvious.</span></span>
<span data-ttu-id="5572e-251">Pokud operace nebo funkce není určena pro přímé použití, ale místo toho by měla být použita odpovídajícím voláním, které funguje na základě částečné aplikace, zvažte použití názvu začínajícího `_` pro volání, které je částečně použito.</span><span class="sxs-lookup"><span data-stu-id="5572e-251">If an operation or function is not intended for direct use, but rather should be used by a matching callable which acts by partial application, consider using a name starting with `_` for the callable that is partially applied.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="5572e-252">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="5572e-252">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="5572e-253">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="5572e-253">We suggest:</span></span>

- <span data-ttu-id="5572e-254">Není-li funkce, operace nebo uživatelsky definovaný typ součástí veřejného rozhraní API pro knihovnu nebo program Q #, ujistěte se, že název začíná počátečním podtržítkem (`_`).</span><span class="sxs-lookup"><span data-stu-id="5572e-254">When a function, operation, or user-defined type is not a part of the public API for a Q# library or program, ensure that its name begins with a leading underscore (`_`).</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="5572e-255">Příklady</span><span class="sxs-lookup"><span data-stu-id="5572e-255">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="5572e-256">Name (Název)</span><span class="sxs-lookup"><span data-stu-id="5572e-256">Name</span></span> | <span data-ttu-id="5572e-257">Popis</span><span class="sxs-lookup"><span data-stu-id="5572e-257">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="5572e-258">☒</span><span class="sxs-lookup"><span data-stu-id="5572e-258">☒</span></span> | <s>`ApplyDecomposedOperation_`</s> | <span data-ttu-id="5572e-259">Podtržítko `_` nesmí být na konci názvu.</span><span class="sxs-lookup"><span data-stu-id="5572e-259">The underscore `_` should not appear at the end of the name.</span></span> |
| <span data-ttu-id="5572e-260">☑</span><span class="sxs-lookup"><span data-stu-id="5572e-260">☑</span></span> | `_ApplyDecomposedOperation` | <span data-ttu-id="5572e-261">Podtržítko `_` na začátku jasně označuje, že tato operace je určena pouze pro interní použití.</span><span class="sxs-lookup"><span data-stu-id="5572e-261">The underscore `_` at the beginning clearly indicates that this operation is for internal use only.</span></span> |

***

### <a name="variants"></a><span data-ttu-id="5572e-262">Typy</span><span class="sxs-lookup"><span data-stu-id="5572e-262">Variants</span></span> ###

<span data-ttu-id="5572e-263">I když toto omezení nemusí být v budoucích verzích Q # trvalé, je v současné době v případě, že budou často skupiny souvisejících operací nebo funkcí, které jsou odlišené funktory jejich vstupy, nebo konkrétními typy jejich argumentů.</span><span class="sxs-lookup"><span data-stu-id="5572e-263">Though this limitation may not persist in future versions of Q#, it is presently the case that there will often be groups of related operations or functions that are distinguished by which functors their inputs support, or by the concrete types of their arguments.</span></span>
<span data-ttu-id="5572e-264">Tyto skupiny lze odlišit pomocí stejného kořenového názvu, následovaný jedním nebo dvěma písmeny, která označují jeho variantu.</span><span class="sxs-lookup"><span data-stu-id="5572e-264">These groups can be distinguished by using the same root name, followed by one or two letters that indicate its variant.</span></span>

| <span data-ttu-id="5572e-265">Auditování</span><span class="sxs-lookup"><span data-stu-id="5572e-265">Suffix</span></span> | <span data-ttu-id="5572e-266">Význam</span><span class="sxs-lookup"><span data-stu-id="5572e-266">Meaning</span></span> |
|--------|---------|
| `A` | <span data-ttu-id="5572e-267">Byl očekáván vstup, který podporuje `Adjoint`</span><span class="sxs-lookup"><span data-stu-id="5572e-267">Input expected to support `Adjoint`</span></span> |
| `C` | <span data-ttu-id="5572e-268">Byl očekáván vstup, který podporuje `Controlled`</span><span class="sxs-lookup"><span data-stu-id="5572e-268">Input expected to support `Controlled`</span></span> |
| `CA` | <span data-ttu-id="5572e-269">Byl očekáván vstup, který podporuje `Controlled` a `Adjoint`</span><span class="sxs-lookup"><span data-stu-id="5572e-269">Input expected to support `Controlled` and `Adjoint`</span></span> |
| `I` | <span data-ttu-id="5572e-270">Vstup nebo vstupy jsou typu `Int`</span><span class="sxs-lookup"><span data-stu-id="5572e-270">Input or inputs are of type `Int`</span></span> |
| `D` | <span data-ttu-id="5572e-271">Vstup nebo vstupy jsou typu `Double`</span><span class="sxs-lookup"><span data-stu-id="5572e-271">Input or inputs are of type `Double`</span></span> |
| `L` | <span data-ttu-id="5572e-272">Vstup nebo vstupy jsou typu `BigInt`</span><span class="sxs-lookup"><span data-stu-id="5572e-272">Input or inputs are of type `BigInt`</span></span> |

# <a name="guidancetabguidance"></a>[<span data-ttu-id="5572e-273">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="5572e-273">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="5572e-274">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="5572e-274">We suggest:</span></span>

- <span data-ttu-id="5572e-275">Pokud funkce nebo operace nesouvisí s podobnými funkcemi nebo operacemi, které typy a funktor podporují jejich vstupy, nepoužívejte příponu.</span><span class="sxs-lookup"><span data-stu-id="5572e-275">If a function or operation is not related to any similar functions or operations by the types and functor support of their inputs, do not use a suffix.</span></span>
- <span data-ttu-id="5572e-276">Pokud funkce nebo operace souvisí s podobnými funkcemi nebo operacemi podle typů a funktor podpory jejich vstupů, použijte přípony jako v tabulce výše, abyste rozlišili varianty.</span><span class="sxs-lookup"><span data-stu-id="5572e-276">If a function or operation is related to any similar functions or operations by the types and functor support of their inputs, use suffixes as in the table above to distinguish variants.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="5572e-277">Příklady</span><span class="sxs-lookup"><span data-stu-id="5572e-277">Examples</span></span>](#tab/examples)

***

### <a name="arguments-and-variables"></a><span data-ttu-id="5572e-278">Argumenty a proměnné</span><span class="sxs-lookup"><span data-stu-id="5572e-278">Arguments and Variables</span></span> ###

<span data-ttu-id="5572e-279">Klíčový cíl kódu Q # pro funkci nebo operaci je, aby jej bylo možné snadno přečíst a pochopit.</span><span class="sxs-lookup"><span data-stu-id="5572e-279">A key goal of the Q# code for a function or operation is for it to be easily read and understood.</span></span>
<span data-ttu-id="5572e-280">Podobně názvy vstupů a argumentů typu by měly sdělit, jak se bude funkce nebo argument používat, jakmile bude k dispozici.</span><span class="sxs-lookup"><span data-stu-id="5572e-280">Similarly, the names of inputs and type arguments should communicate how a function or argument will be used once provided.</span></span>


# <a name="guidancetabguidance"></a>[<span data-ttu-id="5572e-281">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="5572e-281">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="5572e-282">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="5572e-282">We suggest:</span></span>

- <span data-ttu-id="5572e-283">Pro všechny proměnné a vstupní názvy použijte `pascalCase` v případě silné Předvolby na `CamelCase`, `snake_case`nebo `ANGRY_CASE`.</span><span class="sxs-lookup"><span data-stu-id="5572e-283">For all variable and input names, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span>
- <span data-ttu-id="5572e-284">Vstupní názvy by měly být popisné; Vyhněte se jednomu nebo dvěma názvům písmen, pokud je to možné.</span><span class="sxs-lookup"><span data-stu-id="5572e-284">Input names should be descriptive; avoid one or two letter names where possible.</span></span>
- <span data-ttu-id="5572e-285">Operace a funkce, které přijímají přesně jeden argument typu, by měly poznamenat, že argument typu je `T`, když je jeho role zřejmá.</span><span class="sxs-lookup"><span data-stu-id="5572e-285">Operations and functions accepting exactly one type argument should denote that type argument by `T` when its role is obvious.</span></span>
- <span data-ttu-id="5572e-286">Pokud funkce nebo operace přebírá více argumentů typu nebo pokud role jednoho argumentu typu není zřejmá, zvažte použití krátkého slova, které je `T` (např.: `TOutput`) pro každý typ.</span><span class="sxs-lookup"><span data-stu-id="5572e-286">If a function or operation takes multiple type arguments, or if the role of a single type argument is not obvious, consider using a short capitalized word prefaced by `T` (e.g.: `TOutput`) for each type.</span></span>
- <span data-ttu-id="5572e-287">Do názvů argumentů a proměnných nezahrnujte názvy typů; Tyto informace můžou a by měly být poskytované vaším vývojovým prostředím.</span><span class="sxs-lookup"><span data-stu-id="5572e-287">Do not include type names in argument and variable names; this information can and should be provided by your development environment.</span></span>
- <span data-ttu-id="5572e-288">Zaznamenejte skalární typy podle jejich názvů literálů (`flagQubit`) a typy polí pomocí plural (`measResults`).</span><span class="sxs-lookup"><span data-stu-id="5572e-288">Denote scalar types by their literal names (`flagQubit`), and array types by a plural (`measResults`).</span></span>
  <span data-ttu-id="5572e-289">V případě polí qubits je vhodné zvážit označení těchto typů pomocí `Register`, kde název odkazuje na sekvenci qubits, které úzce souvisejí s nějakým způsobem.</span><span class="sxs-lookup"><span data-stu-id="5572e-289">For arrays of qubits in particular, consider denoting such types by `Register` where the name refers to a sequence of qubits that are closely related in some way.</span></span>
- <span data-ttu-id="5572e-290">Proměnné použité jako indexy do polí by měly začínat `idx` a měly by být jednotné (např.: `things[idxThing]`).</span><span class="sxs-lookup"><span data-stu-id="5572e-290">Variables used as indices into arrays should begin with `idx` and should be singular (e.g.: `things[idxThing]`).</span></span>
  <span data-ttu-id="5572e-291">Zejména se silně Vyhněte použití názvů proměnných s jedním písmenem jako indexů; Zvažte použití `idx` minimálně.</span><span class="sxs-lookup"><span data-stu-id="5572e-291">In particular, strongly avoid using single-letter variable names as indices; consider using `idx` at a minimum.</span></span>
- <span data-ttu-id="5572e-292">Proměnné používané pro uchovávání délek polí by měly začínat `n` a měly by být v množném čísle (např.: `nThings`).</span><span class="sxs-lookup"><span data-stu-id="5572e-292">Variables used to hold lengths of arrays should begin with `n` and should be pluralized (e.g.: `nThings`).</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="5572e-293">Příklady</span><span class="sxs-lookup"><span data-stu-id="5572e-293">Examples</span></span>](#tab/examples)

***

### <a name="user-defined-type-named-items"></a><span data-ttu-id="5572e-294">Uživatelem definovaný typ s názvem Items</span><span class="sxs-lookup"><span data-stu-id="5572e-294">User Defined Type Named Items</span></span> ###

<span data-ttu-id="5572e-295">Pojmenované položky v uživatelsky definovaných typech by měly být pojmenovány jako `CamelCase`, a to i ve vstupu na konstruktory UDT.</span><span class="sxs-lookup"><span data-stu-id="5572e-295">Named items in user-defined types should be named as `CamelCase`, even in input to UDT constructors.</span></span>
<span data-ttu-id="5572e-296">To pomáhá při použití notace přistupujícího objektu (např.: `callable::Apply`) nebo zápisu typu Copy-and-Update (`set arr w/= Data <- newData`) jasně oddělit pojmenované položky od odkazů na místně vymezené proměnné.</span><span class="sxs-lookup"><span data-stu-id="5572e-296">This helps in order to clearly separate named items from references to locally scoped variables when using accessor notation (e.g.: `callable::Apply`) or copy-and-update notation (`set arr w/= Data <- newData`).</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="5572e-297">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="5572e-297">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="5572e-298">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="5572e-298">We suggest:</span></span>

- <span data-ttu-id="5572e-299">Pojmenované položky v konstruktorech UDT by měly být pojmenovány jako `CamelCase`; To znamená, že by měly začínat počátečními velkými písmeny.</span><span class="sxs-lookup"><span data-stu-id="5572e-299">Named items in UDT constructors should be named as `CamelCase`; that is, they should begin with an initial uppercase.</span></span>
- <span data-ttu-id="5572e-300">Pojmenované položky, které se překládají na operace, by měly být pojmenovány jako fáze operací.</span><span class="sxs-lookup"><span data-stu-id="5572e-300">Named items that resolve to operations should be named as verb phases.</span></span>
- <span data-ttu-id="5572e-301">Pojmenované položky, které nelze přeložit na operace, by měly být pojmenovány jako podstatné fráze.</span><span class="sxs-lookup"><span data-stu-id="5572e-301">Named items that do not resolve to operations should be named as noun phrases.</span></span>
- <span data-ttu-id="5572e-302">Pro UDT, které zabalí operace, by měla být definována jedna pojmenovaná položka s názvem `Apply`.</span><span class="sxs-lookup"><span data-stu-id="5572e-302">For UDTs that wrap operations, a single named item called `Apply` should be defined.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="5572e-303">Příklady</span><span class="sxs-lookup"><span data-stu-id="5572e-303">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="5572e-304">Zlomk</span><span class="sxs-lookup"><span data-stu-id="5572e-304">Snippet</span></span> | <span data-ttu-id="5572e-305">Popis</span><span class="sxs-lookup"><span data-stu-id="5572e-305">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="5572e-306">☑</span><span class="sxs-lookup"><span data-stu-id="5572e-306">☑</span></span> | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | <span data-ttu-id="5572e-307">Název `Apply` je příkazová fráze ve formátu `CamelCase`, což naznačuje, že pojmenovaná položka je operace.</span><span class="sxs-lookup"><span data-stu-id="5572e-307">The name `Apply` is a `CamelCase`-formatted verb phrase, suggesting that the named item is an operation.</span></span> |
| <span data-ttu-id="5572e-308">☒</span><span class="sxs-lookup"><span data-stu-id="5572e-308">☒</span></span> | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | <span data-ttu-id="5572e-309">Pojmenované položky by měly začínat počátečním velkým písmenem.</span><span class="sxs-lookup"><span data-stu-id="5572e-309">Named items should begin with an initial uppercase letter.</span></span> |
| <span data-ttu-id="5572e-310">☒</span><span class="sxs-lookup"><span data-stu-id="5572e-310">☒</span></span> | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | <span data-ttu-id="5572e-311">Pojmenované položky, které se mají vyhodnotit na Functions, by měly být pojmenovány jako podstatné fráze, nikoli jako slovesová</span><span class="sxs-lookup"><span data-stu-id="5572e-311">Named items which resolve to functions should be named as noun phrases, not as verb phrases.</span></span> |

***

## <a name="input-conventions"></a><span data-ttu-id="5572e-312">Vstupní konvence</span><span class="sxs-lookup"><span data-stu-id="5572e-312">Input Conventions</span></span> ##

<span data-ttu-id="5572e-313">Pokud vývojář volá operaci nebo funkci, je nutné určit různé vstupy pro tuto operaci nebo funkci v určitém pořadí, čímž se zvýší zátěžové zatížení, které vývojář vytvoří, aby mohli použít knihovnu.</span><span class="sxs-lookup"><span data-stu-id="5572e-313">When a developer calls into an operation or function, the various inputs to that operation or function must be specified in a particular order, increasing the cognitive load that a developer faces in order to make use of a library.</span></span>
<span data-ttu-id="5572e-314">Konkrétně úkol přeřazení vstupních objednávek je často z úlohy rušivý: programování implementace algoritmu pro plnění.</span><span class="sxs-lookup"><span data-stu-id="5572e-314">In particular, the task of remembering input orderings is often a distraction from the task at hand: programming an implementation of a quantum algorithm.</span></span>
<span data-ttu-id="5572e-315">I když Rozsáhlá podpora integrovaného vývojového prostředí (IDE) může toto omezení zmírnit na velký rozsah, dobrý návrh a uplatnění běžných konvencí, může také pomoci minimalizovat zátěž vypracovanou rozhraním API.</span><span class="sxs-lookup"><span data-stu-id="5572e-315">Though rich IDE support can mitigate this to a large extent, good design and adherence to common conventions can also help to minimize the cognitive load imposed by an API.</span></span>

<span data-ttu-id="5572e-316">Pokud je to možné, může být užitečné snížit počet vstupů očekávaných operací nebo funkcí, aby se role každého vstupu načetla okamžitě pro vývojáře, kteří volají tuto operaci nebo funkci, a vývojářům tento kód přečte později.</span><span class="sxs-lookup"><span data-stu-id="5572e-316">Where possible, it can be helpful to reduce the number of inputs expected by an operation or function, so that the role of each input is more immediately obvious both to developers calling into that operation or function, and to developers reading that code later.</span></span>
<span data-ttu-id="5572e-317">Zejména v případě, že není možné nebo rozumné snížit počet argumentů operace nebo funkce, je důležité mít konzistentní řazení, které minimalizuje neohlášení chyb uživatelů při předvídání pořadí vstupů.</span><span class="sxs-lookup"><span data-stu-id="5572e-317">Especially when it is not possible or reasonable to reduce the number of arguments to an operation or function, it is important to have a consistent ordering that minimizes the surprise that a user faces when predicting the order of inputs.</span></span>

<span data-ttu-id="5572e-318">Doporučujeme konvence pro řazení vstupu, které jsou převážně odvozené z úvahy částečné aplikace jako generalizace procesu curryfikace f (x, y) ≡ f (x) (y).</span><span class="sxs-lookup"><span data-stu-id="5572e-318">We recommend an input ordering conventions that largely derives from thinking of partial application as a generalization of currying 𝑓(𝑥, 𝑦) ≡ 𝑓(𝑥)(𝑦).</span></span>
<span data-ttu-id="5572e-319">Proto by částečně použití prvních argumentů mělo být volat, které je užitečné, pokud je to vhodné.</span><span class="sxs-lookup"><span data-stu-id="5572e-319">Thus, partially applying the first arguments should result in a callable that is useful in its own right whenever that is reasonable.</span></span>
<span data-ttu-id="5572e-320">Podle tohoto principu zvažte použití následujícího pořadí argumentů:</span><span class="sxs-lookup"><span data-stu-id="5572e-320">Following this principle, consider using the following order of arguments:</span></span>

- <span data-ttu-id="5572e-321">Klasické nediskriminační argumenty, jako jsou úhly, vektory a atd.</span><span class="sxs-lookup"><span data-stu-id="5572e-321">Classical non-callable arguments such as angles, vectors of powers, etc.</span></span>
- <span data-ttu-id="5572e-322">Argumenty pro možnost volat (funkce a argumenty).</span><span class="sxs-lookup"><span data-stu-id="5572e-322">Callable arguments (functions and arguments).</span></span>
  <span data-ttu-id="5572e-323">Pokud jsou funkce a operace provedeny jako argumenty, zvažte umístění operací po funkcích.</span><span class="sxs-lookup"><span data-stu-id="5572e-323">If both functions and operations are taken as arguments, consider placing operations after functions.</span></span>
- <span data-ttu-id="5572e-324">Kolekce, na kterých se pracuje, pomocí volání argumentů podobným způsobem, jak `Map`, `Iter`, `Enumerate`a `Fold`.</span><span class="sxs-lookup"><span data-stu-id="5572e-324">Collections acted upon by callable arguments in a similar way to `Map`, `Iter`, `Enumerate`, and `Fold`.</span></span>
- <span data-ttu-id="5572e-325">Argumenty qubit slouží jako ovládací prvky.</span><span class="sxs-lookup"><span data-stu-id="5572e-325">Qubit arguments used as controls.</span></span>
- <span data-ttu-id="5572e-326">Argumenty qubit slouží jako cíle.</span><span class="sxs-lookup"><span data-stu-id="5572e-326">Qubit arguments used as targets.</span></span>

<span data-ttu-id="5572e-327">Vezměte v úvahu operaci `ApplyPhaseEstimationIteration` pro použití ve odhadu fáze, který přebírá úhel a Oracle, předá úhel, který se `Rz` změnil řadou různých faktorů škálování, a pak řídí aplikace Oracle.</span><span class="sxs-lookup"><span data-stu-id="5572e-327">Consider an operation `ApplyPhaseEstimationIteration` for use in phase estimation that takes an angle and an oracle, passes the angle to `Rz` modified by an array of different scaling factors, and then controls applications of the oracle.</span></span>
<span data-ttu-id="5572e-328">Vstupy jsme poznamenali `ApplyPhaseEstimationIteration` následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="5572e-328">We would order the inputs to `ApplyPhaseEstimationIteration` in the following fashion:</span></span>

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
<span data-ttu-id="5572e-329">U některých funkcí a operací, které jsou ve zvláštních případech minimalizovány, napodobuje chování integrovaných funktory `Adjoint` a `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="5572e-329">As a special case of minimizing surprise, some functions and operations mimic the behavior of the built-in functors `Adjoint` and `Controlled`.</span></span>
<span data-ttu-id="5572e-330">Například `ControlledOnInt<'T>` je typu `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, například, aby `ControlledOnInt<Qubit[]>(5, _)` fungovat jako `Controlled` funktor, ale na podmínku, kterou registr ovládacího prvku představuje stav $ \ket{5} = \ket{101}$.</span><span class="sxs-lookup"><span data-stu-id="5572e-330">For instance, `ControlledOnInt<'T>` has type `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, such that `ControlledOnInt<Qubit[]>(5, _)` acts like the `Controlled` functor, but on the condition that the control register represents the state $\ket{5} = \ket{101}$.</span></span>
<span data-ttu-id="5572e-331">Proto vývojář očekává, že vstupy `ControlledOnInt` umístit vracené operace jako poslední a že výsledná operace přebírá jako svůj vstupní `(Qubit[], 'T)`---stejné pořadí, jako následuje výstup `Controlled` funktor.</span><span class="sxs-lookup"><span data-stu-id="5572e-331">Thus, a developer expects that the inputs to `ControlledOnInt` place the callable being transformed last, and that the resulting operation takes as its input `(Qubit[], 'T)` --- the same order as followed by the output of the `Controlled` functor.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="5572e-332">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="5572e-332">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="5572e-333">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="5572e-333">We suggest:</span></span>

- <span data-ttu-id="5572e-334">Používejte vstupní pořadí konzistentní s použitím částečné aplikace.</span><span class="sxs-lookup"><span data-stu-id="5572e-334">Use input orderings consistent with the use of partial application.</span></span>
- <span data-ttu-id="5572e-335">Používejte vstupní pořadí konzistentní s integrovanými funktory.</span><span class="sxs-lookup"><span data-stu-id="5572e-335">Use input orderings consistent with built-in functors.</span></span>
- <span data-ttu-id="5572e-336">Všechny klasické vstupy umístěte před všechny vstupy za sebou.</span><span class="sxs-lookup"><span data-stu-id="5572e-336">Place all classical inputs before any quantum inputs.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="5572e-337">Příklady</span><span class="sxs-lookup"><span data-stu-id="5572e-337">Examples</span></span>](#tab/examples)

***

## <a name="documentation-conventions"></a><span data-ttu-id="5572e-338">Konvence dokumentace</span><span class="sxs-lookup"><span data-stu-id="5572e-338">Documentation Conventions</span></span> ##

<span data-ttu-id="5572e-339">Jazyk Q # umožňuje připojit dokumentaci k operacím, funkcím a uživatelsky definovaným typům pomocí speciálně formátovaných dokumentačních komentářů.</span><span class="sxs-lookup"><span data-stu-id="5572e-339">The Q# language allows for attaching documentation to operations, functions, and user-defined types through the use of specially formatted documentation comments.</span></span>
<span data-ttu-id="5572e-340">Tyto komentáře k této dokumentaci jsou označeny trojitými lomítky (`///`), [](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) které se dají použít k popisu účelu jednotlivých operací, funkcí a uživatelsky definovaných typů, které vstupy očekává a tak dále.</span><span class="sxs-lookup"><span data-stu-id="5572e-340">Denoted by triple-slashes (`///`), these documentation comments are small [DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) documents that can be used to describing the purpose of each operation, function, and user-defined type, what inputs each expects, and so forth.</span></span>
<span data-ttu-id="5572e-341">Kompilátor, který je součástí vývojové sady pro všechna ta, extrahuje tyto komentáře a použije je k tomu https://docs.microsoft.com/quantum, aby vám pomohly sázení dokumentaci podobnou dokumentaci.</span><span class="sxs-lookup"><span data-stu-id="5572e-341">The compiler provided with the Quantum Development Kit extracts these comments and uses them to help typeset documentation similar to that at https://docs.microsoft.com/quantum.</span></span>
<span data-ttu-id="5572e-342">Podobně jazykový Server, který je součástí vývojové sady pro plnění, používá tyto komentáře k poskytnutí pomocníka uživatelům při přechodu myší na symboly v kódu Q #.</span><span class="sxs-lookup"><span data-stu-id="5572e-342">Similarly, the language server provided with the Quantum Development Kit uses these comments to provide help to users when they hover over symbols in their Q# code.</span></span>
<span data-ttu-id="5572e-343">Používání dokumentačních komentářů tak může pomoci uživatelům vydávat smysl kódu tím, že poskytuje užitečnou referenci pro podrobnosti, které nejsou snadno vyjádřeny pomocí dalších úmluv v tomto dokumentu.</span><span class="sxs-lookup"><span data-stu-id="5572e-343">Making use of documentation comments can thus help users to make sense of code by providing a useful reference for details that are not easily expressed using the other conventions in this document.</span></span>

<div class="nextstepaction"><span data-ttu-id="5572e-344">
    [Referenční dokumentace k syntaxi komentářů k dokumentaci](xref:microsoft.quantum.language.statements#documentation-comments)
</span><span class="sxs-lookup"><span data-stu-id="5572e-344">
    [Documentation comment syntax reference](xref:microsoft.quantum.language.statements#documentation-comments)
</span></span></div>

<span data-ttu-id="5572e-345">Aby bylo možné efektivně využít tuto funkci, doporučujeme, abyste při psaní dokumentačních komentářů měli na paměti pár věcí.</span><span class="sxs-lookup"><span data-stu-id="5572e-345">In order to effectively use this functionality to help users, we recommend keeping a few things in mind as you write documentation comments.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="5572e-346">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="5572e-346">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="5572e-347">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="5572e-347">We suggest:</span></span>

- <span data-ttu-id="5572e-348">Každá veřejná funkce, operace a uživatelsky definované typy by měly hned předcházet dokumentační komentář.</span><span class="sxs-lookup"><span data-stu-id="5572e-348">Each public function, operation, and user-defined type should be immediately preceded by a documentation comment.</span></span>
- <span data-ttu-id="5572e-349">Každý dokumentační komentář by měl mít minimálně následující oddíly:</span><span class="sxs-lookup"><span data-stu-id="5572e-349">At a minimum, each documentation comment should include the following sections:</span></span>
    - <span data-ttu-id="5572e-350">Souhrn</span><span class="sxs-lookup"><span data-stu-id="5572e-350">Summary</span></span>
    - <span data-ttu-id="5572e-351">Vstup</span><span class="sxs-lookup"><span data-stu-id="5572e-351">Input</span></span>
    - <span data-ttu-id="5572e-352">Výstup (Pokud je k dispozici)</span><span class="sxs-lookup"><span data-stu-id="5572e-352">Output (if applicable)</span></span>
- <span data-ttu-id="5572e-353">Ujistěte se, že všechny souhrny jsou dvě nebo méně vět.</span><span class="sxs-lookup"><span data-stu-id="5572e-353">Ensure that all summaries are two sentences or less.</span></span> <span data-ttu-id="5572e-354">Pokud je potřeba více místa, poskytněte `# Description` oddíl hned za `# Summary` s úplnými podrobnostmi.</span><span class="sxs-lookup"><span data-stu-id="5572e-354">If more room is needed, provide a `# Description` section immediately following `# Summary` with complete details.</span></span>
- <span data-ttu-id="5572e-355">Tam, kde je to rozumné, nezahrnuje matematiku v souhrnech, protože ne všichni klienti podporují TeX Notation v souhrnech.</span><span class="sxs-lookup"><span data-stu-id="5572e-355">Where reasonable, do not include math in summaries, as not all clients support TeX notation in summaries.</span></span> <span data-ttu-id="5572e-356">Pamatujte na to, že při psaní dokumentů prose (např. TeX nebo Markdownu) může být vhodnější použít delší délky řádků.</span><span class="sxs-lookup"><span data-stu-id="5572e-356">Note that when writing prose documents (e.g. TeX or Markdown), it may be preferable to use longer line lengths.</span></span>
- <span data-ttu-id="5572e-357">Poskytněte všechny relevantní matematické výrazy v části `# Description`.</span><span class="sxs-lookup"><span data-stu-id="5572e-357">Provide all relevant mathematical expressions in the `# Description` section.</span></span>
- <span data-ttu-id="5572e-358">Při popisu vstupů neopakuje typ každého vstupu, protože je možné ho odvodit kompilátorem a riziko zavedení nekonzistence.</span><span class="sxs-lookup"><span data-stu-id="5572e-358">When describing inputs, do not repeat the types of each input as these can be inferred by the compiler and risk introducing inconsistency.</span></span>
- <span data-ttu-id="5572e-359">Poskytněte příklady podle potřeby, každý v jejich `# Example` oddíl.</span><span class="sxs-lookup"><span data-stu-id="5572e-359">Provide examples as appropriate, each in their own `# Example` section.</span></span>
- <span data-ttu-id="5572e-360">Stručně popište každý příklad před výpisem kódu.</span><span class="sxs-lookup"><span data-stu-id="5572e-360">Briefly describe each example before listing code.</span></span>
- <span data-ttu-id="5572e-361">Seznamte se se všemi relevantními školními publikacemi (například dokumenty, postupy, příspěvky na blogu a alternativní implementace) v části `# References` jako seznam odkazů s odrážkami.</span><span class="sxs-lookup"><span data-stu-id="5572e-361">Cite all relevant academic publications (e.g.: papers, proceedings, blog posts, and alternative implementations) in a `# References` section as a bulleted list of links.</span></span>
- <span data-ttu-id="5572e-362">Ujistěte se, že pokud je to možné, všechny odkazy na citace jsou trvalé a neměnné identifikátory (DOIs nebo arXiv čísla se správou verzí).</span><span class="sxs-lookup"><span data-stu-id="5572e-362">Ensure that, where possible, all citation links are to permanent and immutable identifiers (DOIs or versioned arXiv numbers).</span></span>
- <span data-ttu-id="5572e-363">Pokud je operace nebo funkce v souvislosti s jinými operacemi nebo funkcemi podle funktor variant, vypíše další varianty jako odrážky v části `# See Also`.</span><span class="sxs-lookup"><span data-stu-id="5572e-363">When an operation or function is related to other operations or functions by functor variants, list other variants as bullets in the `# See Also` section.</span></span>
- <span data-ttu-id="5572e-364">Ponechte prázdný řádek komentáře mezi oddíly úrovně 1 (`/// #`), ale nenechávejte prázdné řádky mezi oddíly úrovně 2 (`/// ##`).</span><span class="sxs-lookup"><span data-stu-id="5572e-364">Leave a blank comment line between level-1 (`/// #`) sections, but do not leave a blank line between level-2 (`/// ##`) sections.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="5572e-365">Příklady</span><span class="sxs-lookup"><span data-stu-id="5572e-365">Examples</span></span>](#tab/examples)

#### <a name=""></a><span data-ttu-id="5572e-366">☑</span><span class="sxs-lookup"><span data-stu-id="5572e-366">☑</span></span> ####

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

## <a name="formatting-conventions"></a><span data-ttu-id="5572e-367">Konvence formátování</span><span class="sxs-lookup"><span data-stu-id="5572e-367">Formatting Conventions</span></span> ##

<span data-ttu-id="5572e-368">Kromě výše uvedených návrhů je užitečné pomoct, aby byl kód co čitelný, aby bylo možné použít konzistentní pravidla formátování.</span><span class="sxs-lookup"><span data-stu-id="5572e-368">In addition to the preceding suggestions, it is helpful to help make code as legible as possible to use consistent formatting rules.</span></span>
<span data-ttu-id="5572e-369">Taková pravidla formátování podle povahy mají za následek trochu libovolné a silně silné až do osobních estetických.</span><span class="sxs-lookup"><span data-stu-id="5572e-369">Such formatting rules by nature tend to be somewhat arbitrary and strongly up to personal aesthetics.</span></span>
<span data-ttu-id="5572e-370">Nicméně doporučujeme, abyste zachovali konzistentní sadu formátovacích konvencí v rámci skupiny spolupracovníky a zejména u rozsáhlých projektů Q #, jako je například vývojová sada.</span><span class="sxs-lookup"><span data-stu-id="5572e-370">Nonetheless, we recommend maintaining a consistent set of formatting conventions within a group of collaborators, and especially for large Q# projects such as the Quantum Development Kit itself.</span></span>
<span data-ttu-id="5572e-371">Tato pravidla lze automaticky použít pomocí nástroje formátování integrovaného s kompilátorem Q #.</span><span class="sxs-lookup"><span data-stu-id="5572e-371">These rules can be automatically applied by using the formatting tool integrated with the Q# compiler.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="5572e-372">Doprovodné materiály</span><span class="sxs-lookup"><span data-stu-id="5572e-372">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="5572e-373">Navrhujeme:</span><span class="sxs-lookup"><span data-stu-id="5572e-373">We suggest:</span></span>

- <span data-ttu-id="5572e-374">Místo karet pro přenositelnost použijte čtyři mezery.</span><span class="sxs-lookup"><span data-stu-id="5572e-374">Use four spaces instead of tabs for portability.</span></span>
  <span data-ttu-id="5572e-375">V VS Code například:</span><span class="sxs-lookup"><span data-stu-id="5572e-375">For instance, in VS Code:</span></span>
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- <span data-ttu-id="5572e-376">Zalomení řádku na 79 znaků, kde je to přijatelné.</span><span class="sxs-lookup"><span data-stu-id="5572e-376">Line wrap at 79 characters where reasonable.</span></span>
- <span data-ttu-id="5572e-377">Používejte mezery kolem binárních operátorů.</span><span class="sxs-lookup"><span data-stu-id="5572e-377">Use spaces around binary operators.</span></span>
- <span data-ttu-id="5572e-378">Používejte mezery na kterékoli straně dvojtečky používané pro anotace typu.</span><span class="sxs-lookup"><span data-stu-id="5572e-378">Use spaces on either side of colons used for type annotations.</span></span>
- <span data-ttu-id="5572e-379">Použijte jednu mezeru za čárkami použitou v poli a literálech řazené kolekce členů (např.: ve vstupech až po funkce a operace).</span><span class="sxs-lookup"><span data-stu-id="5572e-379">Use a single space after commas used in array and tuple literals (e.g.: in inputs to functions and operations).</span></span>
- <span data-ttu-id="5572e-380">Nepoužívejte mezery za název funkce, operace nebo UDT ani po `@` v deklaracích atributů.</span><span class="sxs-lookup"><span data-stu-id="5572e-380">Do not use spaces after function, operation, or UDT names, or after the `@` in attribute declarations.</span></span>
- <span data-ttu-id="5572e-381">Každá deklarace atributu by měla být na samostatném řádku.</span><span class="sxs-lookup"><span data-stu-id="5572e-381">Each attribute declaration should be on its own line.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="5572e-382">Příklady</span><span class="sxs-lookup"><span data-stu-id="5572e-382">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="5572e-383">Zlomk</span><span class="sxs-lookup"><span data-stu-id="5572e-383">Snippet</span></span> | <span data-ttu-id="5572e-384">Popis</span><span class="sxs-lookup"><span data-stu-id="5572e-384">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="5572e-385">☒</span><span class="sxs-lookup"><span data-stu-id="5572e-385">☒</span></span> | <s>`2+3`</s> | <span data-ttu-id="5572e-386">Používejte mezery kolem binárních operátorů.</span><span class="sxs-lookup"><span data-stu-id="5572e-386">Use spaces around binary operators.</span></span> |
| <span data-ttu-id="5572e-387">☒</span><span class="sxs-lookup"><span data-stu-id="5572e-387">☒</span></span> | <s>`target:Qubit`</s> | <span data-ttu-id="5572e-388">Používejte mezery kolem dvojtečky typu anotace.</span><span class="sxs-lookup"><span data-stu-id="5572e-388">Use spaces around type annotation colons.</span></span> |
| <span data-ttu-id="5572e-389">☑</span><span class="sxs-lookup"><span data-stu-id="5572e-389">☑</span></span> | `Example(a, b, c)` | <span data-ttu-id="5572e-390">Položky ve vstupní řazené kolekci členů jsou pro čitelnosti správně rozmístěny.</span><span class="sxs-lookup"><span data-stu-id="5572e-390">Items in input tuple are correctly spaced for readability.</span></span> |
| <span data-ttu-id="5572e-391">☒</span><span class="sxs-lookup"><span data-stu-id="5572e-391">☒</span></span> | <s>`Example (a, b, c)`</s> | <span data-ttu-id="5572e-392">Mezery by měly být potlačeny za názvy funkcí, operací nebo UDT.</span><span class="sxs-lookup"><span data-stu-id="5572e-392">Spaces should be suppressed after function, operation, or UDT names.</span></span> |

***

