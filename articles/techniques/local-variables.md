---
title: 'Místní proměnné-Q # – techniky | Microsoft Docs'
description: 'Lokální proměnné – techniky Q #'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.local-variables
ms.openlocfilehash: 8b1de5c096210fb36a81c127a8bbbe1b39522741
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820177"
---
# <a name="local-variables"></a><span data-ttu-id="3324b-103">Místní proměnné</span><span class="sxs-lookup"><span data-stu-id="3324b-103">Local Variables</span></span> #

<span data-ttu-id="3324b-104">Hodnotu libovolného typu v Q # lze přiřadit proměnné pro opětovné použití v rámci operace nebo funkce pomocí klíčového slova `let`.</span><span class="sxs-lookup"><span data-stu-id="3324b-104">A value of any type in Q# can be assigned to a variable for reuse within an operation or function by using the `let` keyword.</span></span>
<span data-ttu-id="3324b-105">Příklad:</span><span class="sxs-lookup"><span data-stu-id="3324b-105">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="3324b-106">To přiřadí konkrétní pole operátorů Pauli proměnné s názvem `measurementOperator`.</span><span class="sxs-lookup"><span data-stu-id="3324b-106">This assigns a particular array of Pauli operators to a variable called `measurementOperator`.</span></span>

> [!TIP]
> <span data-ttu-id="3324b-107">Všimněte si, že nepotřebujeme explicitně zadat typ naší nové proměnné, protože výraz na pravé straně příkazu `let` je nejednoznačný a tento typ je odvozený kompilátorem.</span><span class="sxs-lookup"><span data-stu-id="3324b-107">Note that we did not need to explicitly specify the type of our new variable, as the expression on the right-hand side of the `let` statement is unambiguous and the type is inferred by the compiler.</span></span> 

<span data-ttu-id="3324b-108">Proměnné v Q # jsou *neměnné*, což znamená, že jakmile je proměnná definována tímto způsobem, nelze ji již žádným způsobem změnit.</span><span class="sxs-lookup"><span data-stu-id="3324b-108">Variables in Q# are *immutable*, meaning that once a variable has been defined in this way, it can no longer be changed in any way.</span></span>
<span data-ttu-id="3324b-109">To umožňuje několik užitečných optimalizací, včetně optimalizace klasické logiky, která působí na proměnné, aby bylo možné použít `Adjoint` variantu operace.</span><span class="sxs-lookup"><span data-stu-id="3324b-109">This allows for several beneficial optimizations, including optimization of the classical logic acting on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

<span data-ttu-id="3324b-110">Proměnné definované pomocí vazby `let`, jak je uvedeno výše, jsou místní pro určitý rozsah, jako je například tělo operace nebo obsah `for` smyčky.</span><span class="sxs-lookup"><span data-stu-id="3324b-110">Variables defined using the `let` binding as above are local to a particular scope, such as the body of an operation or the contents of a `for` loop.</span></span>


## <a name="mutability"></a><span data-ttu-id="3324b-111">Proměnlivost</span><span class="sxs-lookup"><span data-stu-id="3324b-111">Mutability</span></span> ##

<span data-ttu-id="3324b-112">Jako alternativu k vytvoření proměnné pomocí `let`klíčové slovo `mutable` vytvoří speciální proměnlivou proměnnou, která může být po prvním vytvoření pomocí klíčového slova `set` znovu svázána.</span><span class="sxs-lookup"><span data-stu-id="3324b-112">As an alternative to creating a variable with `let`, the `mutable` keyword will create a special mutable variable that can be re-bound after it is initially created by using the `set` keyword.</span></span>

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

<span data-ttu-id="3324b-113">Všechny typy v Q #, včetně polí, dodržují sémantiku hodnot.</span><span class="sxs-lookup"><span data-stu-id="3324b-113">All types in Q#, including arrays, follow value semantics.</span></span> <span data-ttu-id="3324b-114">Konkrétně není možné aktualizovat položky pole.</span><span class="sxs-lookup"><span data-stu-id="3324b-114">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="3324b-115">Chcete-li upravit existující pole, je nutné využívat mechanismus kopírování a aktualizace podobně jako u záznamů v F#nástroji.</span><span class="sxs-lookup"><span data-stu-id="3324b-115">To modify an existing array requires leveraging a copy-and-update mechanism much like the one for records in F#.</span></span> <span data-ttu-id="3324b-116">Pomocí nástrojů knihovny pro pole, která jsou k dispozici v [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), můžeme například snadno definovat funkci, která vrací pole Paul, kde Pauli na indexu `i` přebírá danou hodnotu a všechny ostatní položky jsou identity:</span><span class="sxs-lookup"><span data-stu-id="3324b-116">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), we can e.g. easily define a function that returns an array of Paulis where the Pauli at index `i` takes the given value and all other entries are the identity:</span></span> 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

<span data-ttu-id="3324b-117">Podíváme se na to, jak pracovat s poli při diskuzi o příkazech a výrazech Q #.</span><span class="sxs-lookup"><span data-stu-id="3324b-117">We will elaborate more on how to work with arrays when discussing Q# statements and expressions.</span></span> 

<span data-ttu-id="3324b-118">Proměnlivost v rámci Q # je koncept, který se vztahuje na *symbol* , nikoli na typ nebo hodnotu.</span><span class="sxs-lookup"><span data-stu-id="3324b-118">Mutability within Q# is a concept that applies to a *symbol* rather than a type or value.</span></span> <span data-ttu-id="3324b-119">Konkrétně neobsahuje reprezentace v systému typů, implicitně nebo explicitně a zda je vazba proměnlivá (jak je uvedeno v klíčovém slovu `mutable`) nebo neměnných (jak je uvedeno v `let`) nemění typ vázaných proměnných.</span><span class="sxs-lookup"><span data-stu-id="3324b-119">Specifically, it does not have a representation in the type system, implicitly or explicitly, and whether or not a binding is mutable (as indicated by the `mutable` keyword) or immutable (as indicated by `let`) does not change the type of the bound variable(s).</span></span> <span data-ttu-id="3324b-120">To poskytuje důležitý způsob, jak izolovat proměnlivost uvnitř specializovaných funkcí a operací.</span><span class="sxs-lookup"><span data-stu-id="3324b-120">This provides an important way to isolate mutability inside specialized functions and operations.</span></span>
<span data-ttu-id="3324b-121">Zejména i v případě, že se v rámci operace, která používá proměnlivou proměnnou, nemůže automaticky generovat automaticky generovaná specializace typu, může automatická generace fungovat pro operaci, která volá funkci, která používá proměnlivost.</span><span class="sxs-lookup"><span data-stu-id="3324b-121">In particular, even though an adjoint specialization for an operation which uses a mutable variable cannot be auto-generated, auto-generation works fine for an operation calling a function which uses mutability.</span></span>
<span data-ttu-id="3324b-122">Z tohoto důvodu je vhodné provádět funkce a operace, které používají proměnlivost co nejkratší a kompaktní, aby zbytek programu pro práci s více operačními systémem mohl být napsán pomocí běžných neměnných proměnných.</span><span class="sxs-lookup"><span data-stu-id="3324b-122">For this reason, it is a good practice to make functions and operations which use mutability as short and compact as possible, so that the rest of the quantum program can be written using ordinary immutable variables.</span></span>


## <a name="deconstruction"></a><span data-ttu-id="3324b-123">Dekonstrukce</span><span class="sxs-lookup"><span data-stu-id="3324b-123">Deconstruction</span></span> ##

<span data-ttu-id="3324b-124">Kromě přiřazování jedné proměnné, klíčová slova `let` a `mutable` – nebo ve skutečnosti jakékoliv jiné konstrukce vazby – umožňují také rozbalení obsahu [typu řazené kolekce členů](xref:microsoft.quantum.language.type-model#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="3324b-124">In addition to assigning a single variable, the `let` and `mutable` keywords - or in fact any other binding construct - also allow for unpacking the contents of a [tuple type](xref:microsoft.quantum.language.type-model#tuple-types).</span></span>
<span data-ttu-id="3324b-125">Přiřazení tohoto formuláře se říká k *dekonstrukci* prvků této řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="3324b-125">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>
<span data-ttu-id="3324b-126">Například pokud budeme modelovat pojem v Hamiltonian podle řazené kolekce členů, můžeme použít dekonstrukci k přístupu k různým datům, ke kterým musíme simulovat za tento termín:</span><span class="sxs-lookup"><span data-stu-id="3324b-126">For instance, if we model a term in a Hamiltonian by a tuple, then we can use deconstruction to access the different data that we need to simulate under that term:</span></span>

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


