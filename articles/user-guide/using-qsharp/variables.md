---
title: 'Proměnné v Q #'
description: Popis výplně
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 456c05d4ca66a747e0cc514a30c6bbb33610f481
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327777"
---
# <a name="variables-in-q"></a><span data-ttu-id="90db0-103">Proměnné v Q #</span><span class="sxs-lookup"><span data-stu-id="90db0-103">Variables in Q#</span></span>

<span data-ttu-id="90db0-104">Q # rozlišuje proměnlivé a neproměnlivé symboly nebo "proměnné", které jsou vázány nebo přiřazeny výrazům.</span><span class="sxs-lookup"><span data-stu-id="90db0-104">Q# distinguishes between mutable and immutable symbols, or "variables", which are bound/assigned to expressions.</span></span>
<span data-ttu-id="90db0-105">Obecně platí, že použití neměnných symbolů je doporučováno, protože umožňuje kompilátoru provádět větší optimalizace.</span><span class="sxs-lookup"><span data-stu-id="90db0-105">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="90db0-106">Levá strana vazby se skládá ze symbolů řazené kolekce členů a pravé strany výrazu.</span><span class="sxs-lookup"><span data-stu-id="90db0-106">The left-hand-side of a binding consists of a symbol tuple, and the right hand side of an expression.</span></span>

## <a name="immutable-variables"></a><span data-ttu-id="90db0-107">Neměnné proměnné</span><span class="sxs-lookup"><span data-stu-id="90db0-107">Immutable Variables</span></span>

<span data-ttu-id="90db0-108">Hodnotu jakéhokoli typu v Q # lze přiřadit proměnné pro opětovné použití v rámci operace nebo funkce pomocí `let` klíčového slova.</span><span class="sxs-lookup"><span data-stu-id="90db0-108">A value of any type in Q# can be assigned to a variable for reuse within an operation or function by using the `let` keyword.</span></span>

<span data-ttu-id="90db0-109">Neproměnlivá vazba se skládá z klíčového slova `let` následovaný symbolem nebo řazenou kolekcí členů symbolu, znaménko rovná `=` se, výraz pro vazbu symbolů na a ukončující středník.</span><span class="sxs-lookup"><span data-stu-id="90db0-109">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="90db0-110">Například:</span><span class="sxs-lookup"><span data-stu-id="90db0-110">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="90db0-111">To přiřadí konkrétní pole operátorů Pauli k názvu proměnné (neboli symbol), `measurementOperator` .</span><span class="sxs-lookup"><span data-stu-id="90db0-111">This assigns a particular array of Pauli operators to the variable name (or "symbol"), `measurementOperator`.</span></span>

> [!NOTE]
> <span data-ttu-id="90db0-112">Nemuseli explicitně zadat typ naší nové proměnné, protože výraz na pravé straně `let` příkazu je nejednoznačný a daný typ je odvozený kompilátorem.</span><span class="sxs-lookup"><span data-stu-id="90db0-112">We did not need to explicitly specify the type of our new variable, as the expression on the right-hand side of the `let` statement is unambiguous and the type is inferred by the compiler.</span></span> 

<span data-ttu-id="90db0-113">Proměnné definované pomocí `let` jsou *neměnné*, což znamená, že po jejím definování již není možné je nijak měnit.</span><span class="sxs-lookup"><span data-stu-id="90db0-113">Variables defined using `let` are *immutable*, meaning that once it has been defined, it can no longer be changed in any way.</span></span>
<span data-ttu-id="90db0-114">To umožňuje několik užitečných optimalizací, včetně optimalizace klasické logiky, která působí na proměnné, aby se mohla použít `Adjoint` varianta operace.</span><span class="sxs-lookup"><span data-stu-id="90db0-114">This allows for several beneficial optimizations, including optimization of the classical logic acting on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

## <a name="mutable-variables"></a><span data-ttu-id="90db0-115">Proměnlivé proměnné</span><span class="sxs-lookup"><span data-stu-id="90db0-115">Mutable Variables</span></span>

<span data-ttu-id="90db0-116">Jako alternativu k vytvoření proměnné pomocí `let` `mutable` klíčového slova vytvoří proměnlivou proměnnou, která *může* být po počátečním vytvoření pomocí `set` klíčového slova znovu svázána.</span><span class="sxs-lookup"><span data-stu-id="90db0-116">As an alternative to creating a variable with `let`, the `mutable` keyword will create a mutable variable that *can* be re-bound after it is initially created by using the `set` keyword.</span></span>

<span data-ttu-id="90db0-117">Symboly deklarované a svázané jako součást `mutable` příkazu mohou být později v kódu převázány na jinou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="90db0-117">Symbols declared and bound as part of a `mutable` statement may be rebound to a different value later in the code.</span></span> <span data-ttu-id="90db0-118">Pokud je symbol převázán později v kódu, jeho typ se nezmění a nově vázané hodnoty musí být kompatibilní s tímto typem.</span><span class="sxs-lookup"><span data-stu-id="90db0-118">If a symbol is rebound later in the code, its type does not change, and the newly bound value needs to be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="90db0-119">Obnovení vazby proměnlivých symbolů</span><span class="sxs-lookup"><span data-stu-id="90db0-119">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="90db0-120">Proměnlivou proměnnou lze znovu svázat pomocí `set` příkazu.</span><span class="sxs-lookup"><span data-stu-id="90db0-120">A mutable variable may be rebound using a `set` statement.</span></span>
<span data-ttu-id="90db0-121">Taková revazba se skládá z klíčového slova `set` následovaný symbolem nebo řazenou kolekcí členů symbolů, znaménkem rovnosti `=` , výrazu pro opětovné svázání symbolů a zakončeným středníkem.</span><span class="sxs-lookup"><span data-stu-id="90db0-121">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="90db0-122">Tady poskytujeme některé možné příklady technik revázání příkazů.</span><span class="sxs-lookup"><span data-stu-id="90db0-122">Here, we provide some possible examples of rebinding statement techniques</span></span>

### <a name="apply-and-reassign-statements"></a><span data-ttu-id="90db0-123">Příkazy Apply a Reassign</span><span class="sxs-lookup"><span data-stu-id="90db0-123">Apply-and-Reassign Statements</span></span>

<span data-ttu-id="90db0-124">Konkrétní druh `set` příkazu, který označujeme jako příkaz *Apply a Reassign* , poskytuje pohodlný způsob zřetězení, pokud se pravá strana skládá z aplikace binárního operátoru a výsledek je převázán na levý argument operátoru.</span><span class="sxs-lookup"><span data-stu-id="90db0-124">A particular kind of `set`-statement we refer to as an *apply-and-reassign* statement provides a convenient way of concatenation if the right hand side consists of the application of a binary operator and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="90db0-125">Třeba</span><span class="sxs-lookup"><span data-stu-id="90db0-125">For example,</span></span>
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="90db0-126">zvýší hodnotu čítače `counter` v každé iteraci `for` smyčky.</span><span class="sxs-lookup"><span data-stu-id="90db0-126">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="90db0-127">Výše uvedený kód je stejný jako</span><span class="sxs-lookup"><span data-stu-id="90db0-127">The code above is equivalent to</span></span> 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

<span data-ttu-id="90db0-128">Podobné příkazy jsou k dispozici pro všechny binární operátory, ve kterých typ levé strany odpovídá typu výrazu.</span><span class="sxs-lookup"><span data-stu-id="90db0-128">Similar statements are available for all binary operators in which the type of the left-hand-side matches the expression type.</span></span> <span data-ttu-id="90db0-129">To poskytuje například pohodlný způsob, jak nashromáždit hodnoty.</span><span class="sxs-lookup"><span data-stu-id="90db0-129">This provides for example a convenient way to accumulate values.</span></span>

<span data-ttu-id="90db0-130">Například Supposing `qubits` je regsiter of qubits:</span><span class="sxs-lookup"><span data-stu-id="90db0-130">For example, supposing `qubits` is a regsiter of qubits:</span></span>
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

### <a name="update-and-reassign-statements"></a><span data-ttu-id="90db0-131">Příkazy Update a Reassign</span><span class="sxs-lookup"><span data-stu-id="90db0-131">Update-and-Reassign Statements</span></span>

<span data-ttu-id="90db0-132">Pro [výrazy kopírování a aktualizace](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) na pravé straně existuje podobný zřetězení.</span><span class="sxs-lookup"><span data-stu-id="90db0-132">A similar concatenation exists for [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) on the right-hand-side.</span></span>
<span data-ttu-id="90db0-133">Odpovídající příkazy *Update-a-Reassign* existují pro *pojmenované položky* v uživatelsky definovaných typech a také pro *položky pole*.</span><span class="sxs-lookup"><span data-stu-id="90db0-133">Correspondingly, *update-and-reassign* statements exist for *named items* in user-defined types as well as for *array items*.</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

<span data-ttu-id="90db0-134">V případě polí jsou [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) v naší standardní knihovně k dispozici potřebné nástroje pro řadu běžných požadavků na inicializaci a manipulaci s poli, takže se tak můžou vyhnout nutnosti aktualizovat položky pole na prvním místě.</span><span class="sxs-lookup"><span data-stu-id="90db0-134">In the case of arrays, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) in our standard libraries provides the necessary tools for many common array initialization and manipulation needs, and thus help avoid having to update array items in the first place.</span></span> 

<span data-ttu-id="90db0-135">Příkazy Update a Reassign poskytují v případě potřeby alternativu:</span><span class="sxs-lookup"><span data-stu-id="90db0-135">Update-and-reassign statements provide an alternative if needed:</span></span>

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

<span data-ttu-id="90db0-136">Pomocí nástrojů knihovny pro pole, která jsou k dispozici v systému [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) , můžeme například snadno definovat funkci, která vrací pole Paul, kde Pauli on index `i` přebírá danou hodnotu a všechny ostatní položky jsou identity.</span><span class="sxs-lookup"><span data-stu-id="90db0-136">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), we can, for example, easily define a function that returns an array of Paulis where the Pauli at index `i` takes the given value and all other entries are the identity.</span></span>

<span data-ttu-id="90db0-137">Tady jsou dvě definice této funkce s druhým využitím výhod těchto nástrojů.</span><span class="sxs-lookup"><span data-stu-id="90db0-137">Here are two definitions of such a function, with the second taking advantage of the tools at our disposal.</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli or PauliI dep. on whether index==location
    }    
    return pauliArray;
}
```

<span data-ttu-id="90db0-138">Místo procházení každého indexu v poli a podmíněně jeho nastavování na `PauliI` nebo `Pauli` můžete místo toho použít `ConstantArray` z [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) k vytvoření pole `PauliI` a pak jednoduše vracet výraz kopie a aktualizace, ve kterém jsme změnili hodnotu specifc na indexu `location` :</span><span class="sxs-lookup"><span data-stu-id="90db0-138">Instead of iterating over each index in the array, and conditionally setting it to `PauliI` or `Pauli`, we can instead use `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) to create an array of `PauliI`'s, and then simply returning a copy-and-update expression in which we've changed the specifc value at index `location`:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a><span data-ttu-id="90db0-139">Dekonstrukce řazené kolekce členů</span><span class="sxs-lookup"><span data-stu-id="90db0-139">Tuple Deconstruction</span></span>

<span data-ttu-id="90db0-140">Kromě přiřazování jedné proměnné, `let` `mutable` klíčová slova a---nebo ve skutečnosti jakékoliv jiné konstrukce vazby, například `set` (popsané níže)---také umožňují rozbalení obsahu [typu řazené kolekce členů](xref:microsoft.quantum.guide.types#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="90db0-140">In addition to assigning a single variable, the `let` and `mutable` keywords---or in fact any other binding construct, such as `set` (described below)---also allow for unpacking the contents of a [tuple type](xref:microsoft.quantum.guide.types#tuple-types).</span></span>
<span data-ttu-id="90db0-141">Přiřazení tohoto formuláře se říká k *dekonstrukci* prvků této řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="90db0-141">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>

<span data-ttu-id="90db0-142">Pokud je pravá strana vazby řazená kolekce členů, pak je možné po přiřazení dekonstruovat tuto řazenou kolekci členů.</span><span class="sxs-lookup"><span data-stu-id="90db0-142">If the right-hand side of the binding is a tuple, then that tuple may be deconstructed upon assignment.</span></span>
<span data-ttu-id="90db0-143">Tato dekonstrukce může zahrnovat vnořené řazené kolekce členů a jakákoli úplná nebo částečná dekonstrukce je platná, pokud je tvar řazené kolekce členů na pravé straně kompatibilní s obrazcem řazené kolekce členů symbolů.</span><span class="sxs-lookup"><span data-stu-id="90db0-143">Such deconstructions may involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right hand side is compatible with the shape of the symbol tuple.</span></span>

<span data-ttu-id="90db0-144">Příklad:</span><span class="sxs-lookup"><span data-stu-id="90db0-144">For example:</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a><span data-ttu-id="90db0-145">Rozsahy vazeb</span><span class="sxs-lookup"><span data-stu-id="90db0-145">Binding Scopes</span></span>

<span data-ttu-id="90db0-146">Obecně se vazby symbolů přestanou přecházet z oboru a stanou se nefunkčními na konci příkazu, ke kterým dojde v.</span><span class="sxs-lookup"><span data-stu-id="90db0-146">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="90db0-147">Toto pravidlo obsahuje dvě výjimky:</span><span class="sxs-lookup"><span data-stu-id="90db0-147">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="90db0-148">Vazba proměnné smyčky `for` smyčky je v rozsahu pro tělo smyčky for, ale ne za koncem smyčky.</span><span class="sxs-lookup"><span data-stu-id="90db0-148">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="90db0-149">Všechny tři části `repeat` / `until` smyčky (tělo, test a oprava) se považují za jediný obor, takže symboly, které jsou svázané s textem, jsou k dispozici v testu a v opravě.</span><span class="sxs-lookup"><span data-stu-id="90db0-149">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) are treated as a single scope, so symbols that are bound in the body are available in the test and in the fixup.</span></span>

<span data-ttu-id="90db0-150">U obou typů smyček projde smyčka ve vlastním oboru, takže vazby z dřívějšího průchodu nejsou k dispozici v pozdější fázi.</span><span class="sxs-lookup"><span data-stu-id="90db0-150">For both types of loops, each pass through the loop executes in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>
<span data-ttu-id="90db0-151">Podrobnosti o těchto smyčkách najdete v [toku řízení](xref:microsoft.quantum.guide.controlflow).</span><span class="sxs-lookup"><span data-stu-id="90db0-151">Details on these loops can be found at [Control Flow](xref:microsoft.quantum.guide.controlflow).</span></span>

<span data-ttu-id="90db0-152">Vazby symbolů z vnějších bloků jsou děděny pomocí vnitřních bloků.</span><span class="sxs-lookup"><span data-stu-id="90db0-152">Symbol bindings from outer blocks are inherited by inner blocks.</span></span>
<span data-ttu-id="90db0-153">Symbol může být vázaný jenom jednou na blok; není povoleno definovat symbol se stejným názvem jako jiný symbol, který je v oboru (bez "stínování").</span><span class="sxs-lookup"><span data-stu-id="90db0-153">A symbol may only be bound once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="90db0-154">Následující sekvence by byly platné:</span><span class="sxs-lookup"><span data-stu-id="90db0-154">The following sequences would be legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="90db0-155">a</span><span class="sxs-lookup"><span data-stu-id="90db0-155">and</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
...                 // n is not bound to a value
```

<span data-ttu-id="90db0-156">Ale to by bylo neplatné:</span><span class="sxs-lookup"><span data-stu-id="90db0-156">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="90db0-157">Jak by to bylo:</span><span class="sxs-lookup"><span data-stu-id="90db0-157">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="next-steps"></a><span data-ttu-id="90db0-158">Další kroky</span><span class="sxs-lookup"><span data-stu-id="90db0-158">Next steps</span></span>

<span data-ttu-id="90db0-159">Přečtěte si o [práci s Qubits](xref:microsoft.quantum.guide.qubits) v Q #.</span><span class="sxs-lookup"><span data-stu-id="90db0-159">Learn about [Working With Qubits](xref:microsoft.quantum.guide.qubits) in Q#.</span></span>