---
title: Práce s qubity
description: Popis výplně
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: 1655d18ab9d8638ad356e6fb90994b5c1fd76a25
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885307"
---
# <a name="working-with-qubits"></a><span data-ttu-id="3bce5-103">Práce s qubity</span><span class="sxs-lookup"><span data-stu-id="3bce5-103">Working with qubits</span></span>

<span data-ttu-id="3bce5-104">Qubits jsou zásadním objektem informací ve výpočetním prostředí.</span><span class="sxs-lookup"><span data-stu-id="3bce5-104">Qubits are the fundamental object of information in quantum computing.</span></span> <span data-ttu-id="3bce5-105">Obecné seznámení s qubits najdete v tématu [porozumění výpočetnímu](xref:microsoft.quantum.overview.understanding)prostředí a podrobně hlouběji do jejich matematické reprezentace, viz [qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="3bce5-105">For a general introduction to qubits, see [Understanding quantum computing](xref:microsoft.quantum.overview.understanding), and to dive deeper into their mathematical representation, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span> 

<span data-ttu-id="3bce5-106">Tento článek popisuje, jak používat qubits a pracovat s nimi v programu Q #.</span><span class="sxs-lookup"><span data-stu-id="3bce5-106">This article explores how to use and work with qubits in a Q# program.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="3bce5-107">Žádný z příkazů popsaných v tomto článku není platný v těle funkce.</span><span class="sxs-lookup"><span data-stu-id="3bce5-107">None of the statements discussed in this article are valid within the body of a function.</span></span> <span data-ttu-id="3bce5-108">Jsou platné pouze v rámci operací.</span><span class="sxs-lookup"><span data-stu-id="3bce5-108">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="3bce5-109">Přidělování Qubits</span><span class="sxs-lookup"><span data-stu-id="3bce5-109">Allocating Qubits</span></span>

<span data-ttu-id="3bce5-110">Vzhledem k tomu, že fyzický qubits jsou cenným prostředkem v počítači, který je součástí úlohy, je nutné se ujistit, že jsou používány co nejúčinnějším způsobem.</span><span class="sxs-lookup"><span data-stu-id="3bce5-110">Because physical qubits are a precious resource in a quantum computer, part of the compiler's job is to make sure they are being used as efficiently as possible.</span></span>
<span data-ttu-id="3bce5-111">V takovém případě je nutné sdělit Q # a *přidělit* qubits pro použití v rámci konkrétního bloku příkazu.</span><span class="sxs-lookup"><span data-stu-id="3bce5-111">As such, you need to tell Q# to *allocate* qubits for use within a particular statement block.</span></span>
<span data-ttu-id="3bce5-112">Můžete přidělit qubits jako jeden qubit nebo jako pole qubits, které se označuje jako *registr*.</span><span class="sxs-lookup"><span data-stu-id="3bce5-112">You can allocate qubits as a single qubit, or as an array of qubits, known as a *register*.</span></span> 

### <a name="clean-qubits"></a><span data-ttu-id="3bce5-113">Vyčistit qubits</span><span class="sxs-lookup"><span data-stu-id="3bce5-113">Clean qubits</span></span>

<span data-ttu-id="3bce5-114">Použijte `using` příkaz k přidělení nového qubits pro použití během bloku příkazu.</span><span class="sxs-lookup"><span data-stu-id="3bce5-114">Use the `using` statement to allocate new qubits for use during a statement block.</span></span>

<span data-ttu-id="3bce5-115">Příkaz se skládá z klíčového slova `using` , za nímž následuje vazba uzavřená v závorkách `( )` a blok příkazů, ve kterém je qubits k dispozici.</span><span class="sxs-lookup"><span data-stu-id="3bce5-115">The statement consists of the keyword `using`, followed by a binding enclosed in parentheses `( )` and the statement block within which the qubits are available.</span></span>
<span data-ttu-id="3bce5-116">Vazba se řídí stejným vzorem jako `let` příkazy: buď jeden symbol, nebo záznamovou sadu symbolů následovaný symbolem rovná `=` se, a buď jedinou hodnotou, nebo porovnáním řazené kolekce členů *inicializátorů*.</span><span class="sxs-lookup"><span data-stu-id="3bce5-116">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers*.</span></span>

<span data-ttu-id="3bce5-117">Inicializátory jsou k dispozici buď pro jeden qubit, který `Qubit()` je označen jako nebo jako pole qubits, `Qubit[n]` , kde `n` je `Int` výraz.</span><span class="sxs-lookup"><span data-stu-id="3bce5-117">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="3bce5-118">Třeba</span><span class="sxs-lookup"><span data-stu-id="3bce5-118">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="3bce5-119">Libovolný qubits přidělený tímto způsobem se spustí ve stavu $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="3bce5-119">Any qubits allocated in this way start off in the $\ket{0}$ state.</span></span> <span data-ttu-id="3bce5-120">V předchozím příkladu `auxiliary` je tedy jedna qubit ve stavu $ \ket {0} $ a `register` je ve stavu pět-qubit $ \ket {00000} = \ket {0} {0} {0} \otimes \ket \otimes \cdots \otimes \ket.</span><span class="sxs-lookup"><span data-stu-id="3bce5-120">Thus in the previous example, `auxiliary` is a single qubit in the state $\ket{0}$, and `register` is in the five-qubit state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="3bce5-121">Na konci `using` bloku jsou všechny qubits přidělené tímto blokem okamžitě uvolněny a nelze je použít dále.</span><span class="sxs-lookup"><span data-stu-id="3bce5-121">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="3bce5-122">Cílové počítače můžou znovu použít zrušení přidělení qubits a nabízet je ostatním `using` blokům pro přidělení.</span><span class="sxs-lookup"><span data-stu-id="3bce5-122">Target machines can reuse deallocated qubits and offer them to other `using` blocks for allocation.</span></span> <span data-ttu-id="3bce5-123">V takovém případě cílový počítač očekává, že qubits jsou ve stavu $ \ket {0} $ bezprostředně před zrušením přidělení.</span><span class="sxs-lookup"><span data-stu-id="3bce5-123">As such, the target machine expects that qubits are in the $\ket{0}$ state immediately before deallocation.</span></span>
> <span data-ttu-id="3bce5-124">Kdykoli je to možné, použijte k vrácení libovolných přidělených qubits do $ \ket $ jednotnou operaci {0} .</span><span class="sxs-lookup"><span data-stu-id="3bce5-124">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="3bce5-125">V případě potřeby můžete použít @"microsoft.quantum.intrinsic.reset" operaci, která vrátí qubit do $ \ket $ tím, že {0} ji odměří a podmíněně provede operaci založenou na výsledku.</span><span class="sxs-lookup"><span data-stu-id="3bce5-125">If need be, you can use the @"microsoft.quantum.intrinsic.reset" operation, which returns the qubit to $\ket{0}$ by measuring it and conditionally performing an operation based on the result.</span></span> <span data-ttu-id="3bce5-126">Taková míra ničí všechny entanglement se zbývajícími qubits a může tedy ovlivnit výpočet.</span><span class="sxs-lookup"><span data-stu-id="3bce5-126">Such a measurement destroys any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="3bce5-127">Vypůjčený Qubits</span><span class="sxs-lookup"><span data-stu-id="3bce5-127">Borrowed Qubits</span></span>

<span data-ttu-id="3bce5-128">Použijte `borrowing` příkaz k přidělení qubits pro dočasné použití, které nemusí být v určitém stavu.</span><span class="sxs-lookup"><span data-stu-id="3bce5-128">Use the `borrowing` statement to allocate qubits for temporary use, which do not need to be in a specific state.</span></span>

<span data-ttu-id="3bce5-129">V průběhu výpočtu můžete použít vypůjčené qubits jako pomocné místo.</span><span class="sxs-lookup"><span data-stu-id="3bce5-129">You can use borrowed qubits as scratch space during a computation.</span></span>
<span data-ttu-id="3bce5-130">Tyto qubits nejsou obecně v čistém stavu, to znamená, že nejsou nutně inicializovány ve známém stavu, například $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="3bce5-130">These qubits are generally not in a clean state, that is, they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="3bce5-131">Ty se často označují jako "nequbitsé", protože jejich stav je neznámý a může být dokonce entangled s ostatními částmi paměti počítače.</span><span class="sxs-lookup"><span data-stu-id="3bce5-131">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="3bce5-132">Vazba následuje stejný vzor a pravidla jako `using` příkaz.</span><span class="sxs-lookup"><span data-stu-id="3bce5-132">The binding follows the same pattern and rules as the `using` statement.</span></span>
<span data-ttu-id="3bce5-133">Třeba</span><span class="sxs-lookup"><span data-stu-id="3bce5-133">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="3bce5-134">Vypůjčený qubits je v neznámém stavu a na konci bloku příkazu se překročí rozsah.</span><span class="sxs-lookup"><span data-stu-id="3bce5-134">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="3bce5-135">Dlužník se zavazuje, že opustí qubits ve stejném stavu, ve kterém byly při jejich vypůjčení. To znamená, že jejich stav na začátku a na konci bloku příkazu by měl být stejný.</span><span class="sxs-lookup"><span data-stu-id="3bce5-135">The borrower commits to leaving the qubits in the same state they were in when they borrowed them; that is, their state at the beginning and the end of the statement block should be the same.</span></span>
<span data-ttu-id="3bce5-136">Vzhledem k tomu, že tento stav není nutně klasický, ve většině případů se zapůjčení oborů nesmí obsahovat měření.</span><span class="sxs-lookup"><span data-stu-id="3bce5-136">Because this state is not necessarily a classical state, in most cases borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="3bce5-137">Při výpůjčkě qubits se systém nejprve pokusí vyplnit požadavek z qubits, které se používají, ale během těla příkazu se k němu nepoužívá `borrowing` .</span><span class="sxs-lookup"><span data-stu-id="3bce5-137">When borrowing qubits, the system first tries to fill the request from qubits that are in use but not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="3bce5-138">Pokud není dostatek takových qubits, přidělí nové qubits k dokončení žádosti.</span><span class="sxs-lookup"><span data-stu-id="3bce5-138">If there aren't enough such qubits, then it allocates new qubits to complete the request.</span></span>

<span data-ttu-id="3bce5-139">Mezi známé případy použití undirty qubits jsou implementace více řízených CNOTch bran, které vyžadují jenom velmi málo qubits a implementaci přírůstku.</span><span class="sxs-lookup"><span data-stu-id="3bce5-139">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="3bce5-140">Příklad jejich použití v Q # najdete v tématu [výpůjčka Qubits příklad](#borrowing-qubits-example) v tomto článku nebo vytváření papírů [*pomocí 2n + 2 Qubits s modulárním násobení*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler a Svore 2017) pro algoritmus, který využívá vypůjčený Qubits.</span><span class="sxs-lookup"><span data-stu-id="3bce5-140">For an example of their use in Q#, see [Borrowing Qubits Example](#borrowing-qubits-example) in this article, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>

## <a name="intrinsic-operations"></a><span data-ttu-id="3bce5-141">Vnitřní operace</span><span class="sxs-lookup"><span data-stu-id="3bce5-141">Intrinsic Operations</span></span>

<span data-ttu-id="3bce5-142">Po přidělení můžete předat qubit funkcím a operacím.</span><span class="sxs-lookup"><span data-stu-id="3bce5-142">Once allocated, you can pass a qubit to functions and operations.</span></span>
<span data-ttu-id="3bce5-143">V některých případech to znamená, že program Q # může s qubit provádět, protože akce, které lze provést, jsou definovány jako operace.</span><span class="sxs-lookup"><span data-stu-id="3bce5-143">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>

<span data-ttu-id="3bce5-144">Tento článek popisuje několik užitečných operací Q #, které můžete použít k interakci s qubits.</span><span class="sxs-lookup"><span data-stu-id="3bce5-144">This article discusses a few useful Q# operations that you can use to interact with qubits.</span></span>
<span data-ttu-id="3bce5-145">Další podrobnosti o těchto a dalších funkcích najdete v tématu [vnitřní operace a funkce](xref:microsoft.quantum.libraries.standard.prelude).</span><span class="sxs-lookup"><span data-stu-id="3bce5-145">For more detail about these and others, see [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span> 

<span data-ttu-id="3bce5-146">Za prvé, qubit Pauli Operators $X $, $Y $ a $Z $ jsou v Q # reprezentovány vnitřními operacemi [`X`](xref:microsoft.quantum.intrinsic.x) , [`Y`](xref:microsoft.quantum.intrinsic.y) a [`Z`](xref:microsoft.quantum.intrinsic.z) , z nichž každý má typ `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="3bce5-146">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations [`X`](xref:microsoft.quantum.intrinsic.x), [`Y`](xref:microsoft.quantum.intrinsic.y), and [`Z`](xref:microsoft.quantum.intrinsic.z), each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="3bce5-147">Jak je popsáno v tématu [vnitřní operace a funkce](xref:microsoft.quantum.libraries.standard.prelude), uvažujte o $X $, a to proto, že se jedná o `X` operaci PŘEklápění nebo ne o hradlo.</span><span class="sxs-lookup"><span data-stu-id="3bce5-147">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="3bce5-148">Operaci můžete použít `X` k přípravě stavů ve formátu $ \ket{s_0 S_1 \dots S_N} $ pro některý z klasických bitových řetězců $s $:</span><span class="sxs-lookup"><span data-stu-id="3bce5-148">You can use the `X` operation to prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

```qsharp
operation PrepareBitString(bitstring : Bool[], register : Qubit[]) : Unit
is Adj + Ctl {
    let nQubits = Length(register);
    for (idxQubit in 0..nQubits - 1) {
        if (bitstring[idxQubit]) {
            X(register[idxQubit]);
        }
    }
}

operation RunExample() : Unit {
    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
        // Remember to reset the qubits before deallocation:
        ResetAll(register);
    }
}
```

> [!TIP]
> <span data-ttu-id="3bce5-149">Později se zobrazí více kompaktních způsobů psaní této operace, která nevyžaduje ruční tok řízení.</span><span class="sxs-lookup"><span data-stu-id="3bce5-149">Later, you will see more compact ways of writing this operation that do not require manual control flow.</span></span>

<span data-ttu-id="3bce5-150">Můžete také připravit stavy, jako je $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ a $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\sqrt {2} $, pomocí Hadamard Transforming $H $, který je reprezentován v Q # vnitřní operací [`H`](xref:microsoft.quantum.intrinsic.h) (také typ (qubit => jednotka je ADJ + CTL)):</span><span class="sxs-lookup"><span data-stu-id="3bce5-150">You can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation [`H`](xref:microsoft.quantum.intrinsic.h) (also of type (Qubit => Unit is Adj + Ctl)\`):</span></span>

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString in the earlier example.
    PrepareBitString(bitstring, register);
    // Next, use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the desired state.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a><span data-ttu-id="3bce5-151">Měření</span><span class="sxs-lookup"><span data-stu-id="3bce5-151">Measurements</span></span>

<span data-ttu-id="3bce5-152">Měření jednotlivých qubits se dají provádět v různých základech, z nichž každý představuje Pauli osa v [oblasti Bloch](xref:microsoft.quantum.glossary#bloch-sphere).</span><span class="sxs-lookup"><span data-stu-id="3bce5-152">Measurements of individual qubits can be performed in different bases, each represented by a Pauli axis on the [Bloch sphere](xref:microsoft.quantum.glossary#bloch-sphere).</span></span>
<span data-ttu-id="3bce5-153">*Výpočetní základ* odkazuje na `PauliZ` základ a je nejběžnějším základem pro měření.</span><span class="sxs-lookup"><span data-stu-id="3bce5-153">The *computational basis* refers to the `PauliZ` basis, and is the most common basis used for measurement.</span></span>

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a><span data-ttu-id="3bce5-154">Měření jediného qubitu v `PauliZ` základu</span><span class="sxs-lookup"><span data-stu-id="3bce5-154">Measure a single qubit in the `PauliZ` basis</span></span>

<span data-ttu-id="3bce5-155">Použijte [`M`](xref:microsoft.quantum.intrinsic.m) operaci, která je vestavěnou vnitřní nejednotkovou operací, k měření jediného qubitu v `PauliZ` základu a k tomu ke výsledku přiřadíte klasický údaj.</span><span class="sxs-lookup"><span data-stu-id="3bce5-155">Use the [`M`](xref:microsoft.quantum.intrinsic.m) operation, which is a built-in intrinsic non-unitary operation, to measure a single qubit in the `PauliZ` basis and assign a classical value to the result.</span></span>
<span data-ttu-id="3bce5-156">`M`má rezervovaný návratový typ, `Result` který může převzít pouze hodnoty `Zero` nebo `One` odpovídající měřené stavy $ \ket {0} $ nebo $ \ket {1} $ – označuje, že výsledek již není ve stavu bez hodnoty.</span><span class="sxs-lookup"><span data-stu-id="3bce5-156">`M` has a reserved return type, `Result`, which can only take values `Zero` or `One` corresponding to the measured states $\ket{0}$ or $\ket{1}$ - indicating that the result is no longer a quantum state.</span></span>

<span data-ttu-id="3bce5-157">Jednoduchým příkladem je následující operace, která přiděluje jednu qubit ve stavu $ \ket {0} $, pak na ni aplikuje operaci Hadamard `H` a měří výsledek na `PauliZ` základě.</span><span class="sxs-lookup"><span data-stu-id="3bce5-157">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // Apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, return the result of the measurement.
        return result;
    }
}
```

### <a name="measure-one-or-more-qubits-in-specific-bases"></a><span data-ttu-id="3bce5-158">Měření jednoho nebo více qubits v konkrétních základech</span><span class="sxs-lookup"><span data-stu-id="3bce5-158">Measure one or more qubits in specific bases</span></span>

<span data-ttu-id="3bce5-159">Chcete-li změřit pole jednoho nebo více qubits v konkrétních základech, můžete použít [`Measure`](xref:microsoft.quantum.intrinsic.measure) operaci.</span><span class="sxs-lookup"><span data-stu-id="3bce5-159">To measure an array of one or more qubits in specific bases, you can use the [`Measure`](xref:microsoft.quantum.intrinsic.measure) operation.</span></span>

<span data-ttu-id="3bce5-160">Vstupy pro `Measure` jsou pole `Pauli` typů (například `[PauliX, PauliZ, PauliZ]` ) a pole qubits.</span><span class="sxs-lookup"><span data-stu-id="3bce5-160">The inputs to `Measure` are an array of `Pauli` types (for example, `[PauliX, PauliZ, PauliZ]`) and an array of qubits.</span></span>

<span data-ttu-id="3bce5-161">Mírně komplikovanější příklad je dán následující operací, která vrací logickou hodnotu, `true` Pokud jsou všechny qubits v registru typu `Qubit[]` v hodnotě nula, pokud se měří v zadaném Pauli a který vrací `false` jinak.</span><span class="sxs-lookup"><span data-stu-id="3bce5-161">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

```qsharp
operation MeasureIfAllQubitsAreZero(qubits : Qubit[], pauli : Pauli) : Bool {
    mutable value = true;
    for (qubit in qubits) {
        if (Measure([pauli], [qubit]) == One) {
            set value = false;
        }
    }
    return value;
}
```

<span data-ttu-id="3bce5-162">Všimněte si, že tento příklad se pořád provádí jenom `Measure` na jednotlivých qubits po jednom, ale operace se dá rozšířit na společné měření více qubits.</span><span class="sxs-lookup"><span data-stu-id="3bce5-162">Note that this example still only performs `Measure` on individual qubits one at a time, but the operation can be extended to joint measurements on multiple qubits.</span></span>

## <a name="borrowing-qubits-example"></a><span data-ttu-id="3bce5-163">Příklad výpůjčky Qubits</span><span class="sxs-lookup"><span data-stu-id="3bce5-163">Borrowing Qubits Example</span></span>

<span data-ttu-id="3bce5-164">Ve Canon jsou příklady, které používají `borrowing` klíčové slovo, jako je například následující funkce `MultiControlledXBorrow` .</span><span class="sxs-lookup"><span data-stu-id="3bce5-164">There are examples in the canon that use the `borrowing` keyword, such as the following function `MultiControlledXBorrow`.</span></span> <span data-ttu-id="3bce5-165">Pokud `controls` aplikace označuje qubits ovládacího prvku, že se má přidat k `X` operaci, pak počet nezměněných [ancillas](xref:microsoft.quantum.glossary#ancilla) přidaných touto implementací je `Length(controls)-2` .</span><span class="sxs-lookup"><span data-stu-id="3bce5-165">If `controls` denotes the control qubits to add to an `X` operation, then the number of dirty [ancillas](xref:microsoft.quantum.glossary#ancilla) added by this implementation is `Length(controls)-2`.</span></span>

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

<span data-ttu-id="3bce5-166">Všimněte si, že tento příklad používá rozsáhlé použití `With` kombinátorem ve formě, který platí pro operace, které podporují sousední, například `WithA` .</span><span class="sxs-lookup"><span data-stu-id="3bce5-166">Note that this example used extensive use of the `With` combinator, in its form that is applicable for operations that support adjoint, for example, `WithA`.</span></span>
<span data-ttu-id="3bce5-167">To je dobrý styl programování, protože přidání ovládacího prvku do struktur zahrnující `With` rozšíření šíří pouze vnitřní operaci.</span><span class="sxs-lookup"><span data-stu-id="3bce5-167">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="3bce5-168">Všimněte si také, že kromě `body` operace `controlled` byla explicitně poskytnuta implementace těla operace, nikoli `controlled auto` příkaz k příkazu.</span><span class="sxs-lookup"><span data-stu-id="3bce5-168">Also note that, in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="3bce5-169">Důvodem je to, že kvůli struktuře okruhu je snadné přidat další ovládací prvky, které jsou ve srovnání s přidáním řízení ke každé bráně v nástroji užitečné `body` .</span><span class="sxs-lookup"><span data-stu-id="3bce5-169">The reason for this is that, because of the structure of the circuit, it is easy to add further controls, which is beneficial compared to adding control to each gate in the `body`.</span></span> 

<span data-ttu-id="3bce5-170">Je povede k porovnání tohoto kódu s jinou funkcí Canon, `MultiControlledXClean` která dosahuje stejného cíle implementace operace řízené vynásobením `X` , která však používá několik čistých qubits pomocí `using` mechanismu.</span><span class="sxs-lookup"><span data-stu-id="3bce5-170">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="3bce5-171">Další kroky</span><span class="sxs-lookup"><span data-stu-id="3bce5-171">Next steps</span></span>

<span data-ttu-id="3bce5-172">Přečtěte si o [toku řízení](xref:microsoft.quantum.guide.controlflow) v Q #.</span><span class="sxs-lookup"><span data-stu-id="3bce5-172">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>