---
title: Práce s qubity
description: Popis výplně
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: e89b9ccfe2a0796e01eedfc99f7ce71038d85f38
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430930"
---
# <a name="working-with-qubits"></a><span data-ttu-id="c66f1-103">Práce s qubity</span><span class="sxs-lookup"><span data-stu-id="c66f1-103">Working with qubits</span></span>

<span data-ttu-id="c66f1-104">Teď se zobrazila celá řada různých částí jazyka Q #. můžeme se dostat do široké nabídky a podívat se, jak qubits sami.</span><span class="sxs-lookup"><span data-stu-id="c66f1-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

<span data-ttu-id="c66f1-105">Všimněte si, že žádný z těchto příkazů není povolen v rámci těla funkce.</span><span class="sxs-lookup"><span data-stu-id="c66f1-105">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="c66f1-106">Jsou platné pouze v rámci operací.</span><span class="sxs-lookup"><span data-stu-id="c66f1-106">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="c66f1-107">Přidělování Qubits</span><span class="sxs-lookup"><span data-stu-id="c66f1-107">Allocating Qubits</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="c66f1-108">Vyčistit qubits</span><span class="sxs-lookup"><span data-stu-id="c66f1-108">Clean qubits</span></span>

<span data-ttu-id="c66f1-109">`using`Příkaz slouží k *přidělení* nového qubits pro použití během bloku příkazu.</span><span class="sxs-lookup"><span data-stu-id="c66f1-109">The `using` statement is used to *allocate* new qubits for use during a statement block.</span></span>

<span data-ttu-id="c66f1-110">Příkaz se skládá z klíčového slova `using` následovaných levou závorkou `(` , vazbou, uzavírací závorkou `)` a blokem příkazu, ve kterém bude qubits k dispozici.</span><span class="sxs-lookup"><span data-stu-id="c66f1-110">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="c66f1-111">Vazba se řídí stejným vzorem jako `let` příkazy: buď jeden symbol, nebo záznamovou sadu symbolů následovaný symbolem rovná `=` se, a buď jedinou hodnotou, nebo porovnáním řazené kolekce členů *inicializátorů*.</span><span class="sxs-lookup"><span data-stu-id="c66f1-111">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers*.</span></span>

<span data-ttu-id="c66f1-112">Inicializátory jsou k dispozici buď pro jeden qubit, který `Qubit()` je označen jako nebo jako pole qubits, `Qubit[n]` , kde `n` je `Int` výraz.</span><span class="sxs-lookup"><span data-stu-id="c66f1-112">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="c66f1-113">Například:</span><span class="sxs-lookup"><span data-stu-id="c66f1-113">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="c66f1-114">Všechny qubits přidělené tímto způsobem začínají ve stavu $ \ket {0} $; v příkladu výše `register` je tak ve stavu $ \ket {00000} = \ket {0} \otimes \ket {0} \otimes \cdots \otimes \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="c66f1-114">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="c66f1-115">Na konci `using` bloku jsou všechny qubits přidělené tímto blokem okamžitě uvolněny a nelze je použít dále.</span><span class="sxs-lookup"><span data-stu-id="c66f1-115">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="c66f1-116">Cílové počítače očekávají, že qubits jsou ve stavu $ \ket {0} $ bezprostředně před zrušením přidělení, aby je bylo možné znovu použít a nabízet jiným `using` blokům pro přidělení.</span><span class="sxs-lookup"><span data-stu-id="c66f1-116">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="c66f1-117">Kdykoli je to možné, použijte k vrácení libovolných přidělených qubits do $ \ket $ jednotnou operaci {0} .</span><span class="sxs-lookup"><span data-stu-id="c66f1-117">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="c66f1-118">V případě potřeby je @"microsoft.quantum.intrinsic.reset" možné operaci použít k měření qubit a k použití tohoto výsledku měření, abyste zajistili, že se měřený qubit vrátí do $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="c66f1-118">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="c66f1-119">Taková míra odstraní všechny entanglement se zbývajícími qubits a může tedy ovlivnit výpočet.</span><span class="sxs-lookup"><span data-stu-id="c66f1-119">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="c66f1-120">Vypůjčený Qubits</span><span class="sxs-lookup"><span data-stu-id="c66f1-120">Borrowed Qubits</span></span>

<span data-ttu-id="c66f1-121">`borrowing`Příkaz slouží k tomu, aby qubits k dispozici pro dočasné použití, které nemusejí být v určitém stavu.</span><span class="sxs-lookup"><span data-stu-id="c66f1-121">The `borrowing` statement is used to make qubits available for temporary use, which do not need be in a specific state.</span></span>

<span data-ttu-id="c66f1-122">Výpůjční mechanizmus umožňuje přidělení qubits, které lze použít jako pomocné místo během výpočtu.</span><span class="sxs-lookup"><span data-stu-id="c66f1-122">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span>
<span data-ttu-id="c66f1-123">Tyto qubits nejsou obvykle v čistém stavu, tj., nejsou nutně inicializovány ve známém stavu, například $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="c66f1-123">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="c66f1-124">Ty se často označují jako "nequbitsé", protože jejich stav je neznámý a může být dokonce entangled s ostatními částmi paměti počítače.</span><span class="sxs-lookup"><span data-stu-id="c66f1-124">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="c66f1-125">Vazba následuje stejný vzor a pravidla jako v `using` příkazu.</span><span class="sxs-lookup"><span data-stu-id="c66f1-125">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>
<span data-ttu-id="c66f1-126">Například:</span><span class="sxs-lookup"><span data-stu-id="c66f1-126">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="c66f1-127">Vypůjčený qubits je v neznámém stavu a na konci bloku příkazu se překročí rozsah.</span><span class="sxs-lookup"><span data-stu-id="c66f1-127">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="c66f1-128">Dlužník se zavazuje, že opustí qubits ve stejném stavu, ve kterém byly ve chvíli, kdy byly vypůjčené, tj. jejich stav na začátku a na konci bloku příkazu by měl být stejný.</span><span class="sxs-lookup"><span data-stu-id="c66f1-128">The borrower commits to leaving the qubits in the same state they were in when they were borrowed,  i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="c66f1-129">Konkrétně se nejedná o klasický stav, což znamená, že ve většině případů by výpůjční rozsahy neměly obsahovat měření.</span><span class="sxs-lookup"><span data-stu-id="c66f1-129">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="c66f1-130">Při výpůjčkě qubits se systém nejprve pokusí vyplňovat požadavek z qubits, které se používají, ale nejsou k dispozici během těla `borrowing` příkazu.</span><span class="sxs-lookup"><span data-stu-id="c66f1-130">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="c66f1-131">Pokud není dostatečná taková qubits, přidělí se nové qubits, aby se žádost dokončila.</span><span class="sxs-lookup"><span data-stu-id="c66f1-131">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>


<span data-ttu-id="c66f1-132">Mezi známé případy použití undirty qubits jsou implementace více řízených CNOTch bran, které vyžadují jenom velmi málo qubits a implementaci přírůstku.</span><span class="sxs-lookup"><span data-stu-id="c66f1-132">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="c66f1-133">Podívejte se na [příklad výpůjčky Qubits](#borrowing-qubits-example) , kde vidíte příklad jejich použití v Q # nebo vytváření papírů [*pomocí 2n + 2 Qubits s modulárním násobení*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler a Svore 2017) pro algoritmus, který využívá vypůjčený Qubits.</span><span class="sxs-lookup"><span data-stu-id="c66f1-133">See the [Borrowing Qubits Example](#borrowing-qubits-example) below to see an example of their use in Q#, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>


## <a name="intrinsic-operations"></a><span data-ttu-id="c66f1-134">Vnitřní operace</span><span class="sxs-lookup"><span data-stu-id="c66f1-134">Intrinsic Operations</span></span>

<span data-ttu-id="c66f1-135">Po přidělení může být qubit předán do funkcí a operací.</span><span class="sxs-lookup"><span data-stu-id="c66f1-135">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="c66f1-136">V některých případech to znamená, že program Q # může s qubit provádět, protože akce, které lze provést, jsou definovány jako operace.</span><span class="sxs-lookup"><span data-stu-id="c66f1-136">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="c66f1-137">Tyto operace podrobněji uvidíme v [vnitřních operacích a funkcích](xref:microsoft.quantum.libraries.standard.prelude), ale v současné době uvádíme několik užitečných operací, které se dají použít k interakci s qubits.</span><span class="sxs-lookup"><span data-stu-id="c66f1-137">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="c66f1-138">Za prvé, qubit Pauli Operators $X $, $Y $ a $Z $ jsou v Q # reprezentovány vnitřními operacemi `X` , `Y` a `Z` , z nichž každý má typ `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="c66f1-138">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="c66f1-139">Jak je popsáno v tématu [vnitřní operace a funkce](xref:microsoft.quantum.libraries.standard.prelude), můžeme si představit $X $ a tedy `X` také jako operaci překlápění.</span><span class="sxs-lookup"><span data-stu-id="c66f1-139">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="c66f1-140">Tato `X` operace umožňuje připravit stavy formuláře $ \ket{s_0 S_1 \dots S_N} $ pro některý z klasických bitových řetězců $s $:</span><span class="sxs-lookup"><span data-stu-id="c66f1-140">The `X` operation lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
        // Resetting the qubits will allow us to deallocate them properly.
        ResetAll(register);
    }
}
```

> [!TIP]
> <span data-ttu-id="c66f1-141">Později se zobrazí více kompaktních způsobů psaní této operace, která nevyžaduje ruční řízení toku.</span><span class="sxs-lookup"><span data-stu-id="c66f1-141">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="c66f1-142">Můžete také připravit stavy, jako je $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ a $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\sqrt {2} $, pomocí Hadamard Transforming $H $, který je reprezentován v Q # vnitřní operací `H : (Qubit => Unit is Adj + Ctl)` :</span><span class="sxs-lookup"><span data-stu-id="c66f1-142">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString, above.
    PrepareBitString(bitstring, register);
    // Next, we use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the state we want.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a><span data-ttu-id="c66f1-143">Měření</span><span class="sxs-lookup"><span data-stu-id="c66f1-143">Measurements</span></span>

<span data-ttu-id="c66f1-144">Pomocí `Measure` operace, která je vestavěnou vnitřní nejednotkovou operací, můžeme extrahovat klasické informace z objektu typu `Qubit` a přiřadit klasický údaj jako výsledek, který má rezervovaný typ `Result` , což značí, že výsledek již není ve stavu bez hodnoty.</span><span class="sxs-lookup"><span data-stu-id="c66f1-144">Using the `Measure` operation, which is a built-in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span>
<span data-ttu-id="c66f1-145">Vstup do `Measure` je Pauli osa v koule Bloch, reprezentovaná hodnotou typu `Pauli` (pro instanci `PauliX` ) a hodnotou typu `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="c66f1-145">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by a value of type `Pauli` (for instance `PauliX`) and an value of type `Qubit`.</span></span>

<span data-ttu-id="c66f1-146">Jednoduchým příkladem je následující operace, která přiděluje jednu qubit ve stavu $ \ket {0} $, pak na ni aplikuje operaci Hadamard `H` a měří výsledek na `PauliZ` základě.</span><span class="sxs-lookup"><span data-stu-id="c66f1-146">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

<span data-ttu-id="c66f1-147">Mírně komplikovanější příklad je dán následující operací, která vrací logickou hodnotu, `true` Pokud jsou všechny qubits v registru typu `Qubit[]` v hodnotě nula, pokud se měří v zadaném Pauli a který vrací `false` jinak.</span><span class="sxs-lookup"><span data-stu-id="c66f1-147">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

## <a name="borrowing-qubits-example"></a><span data-ttu-id="c66f1-148">Příklad výpůjčky Qubits</span><span class="sxs-lookup"><span data-stu-id="c66f1-148">Borrowing Qubits Example</span></span>

<span data-ttu-id="c66f1-149">V Canon existují příklady, které používají `borrowing` klíčové slovo, například funkci `MultiControlledXBorrow` definovanou níže.</span><span class="sxs-lookup"><span data-stu-id="c66f1-149">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="c66f1-150">Pokud `controls` aplikace označuje qubits ovládacího prvku, který se má přidat k `X` operaci, pak se `Length(controls)-2` Tato implementace přidá do celkového počtu nezměněných ancillas.</span><span class="sxs-lookup"><span data-stu-id="c66f1-150">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

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

<span data-ttu-id="c66f1-151">Mějte na paměti, že `With` kombinátorem---ve své podobě, která se vztahuje na operace, které podporují sousední, tj. `WithA` ---byl v tomto příkladu proveden.</span><span class="sxs-lookup"><span data-stu-id="c66f1-151">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example.</span></span>
<span data-ttu-id="c66f1-152">To je dobrý styl programování, protože přidání ovládacího prvku do struktur zahrnující `With` rozšíření šíří pouze vnitřní operaci.</span><span class="sxs-lookup"><span data-stu-id="c66f1-152">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="c66f1-153">Dále si všimněte, že zde jsou kromě `body` operace k `controlled` dispozici implementace těla operace, nikoli použití `controlled auto` příkazu.</span><span class="sxs-lookup"><span data-stu-id="c66f1-153">Further, note that here in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="c66f1-154">Důvodem je to, že ví od struktury okruhu, jak snadno přidat další ovládací prvky, které jsou ve srovnání s přidáním řízení ke každé a každé samostatné bráně v nástroji užitečné `body` .</span><span class="sxs-lookup"><span data-stu-id="c66f1-154">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="c66f1-155">Je povede k porovnání tohoto kódu s jinou funkcí Canon, `MultiControlledXClean` která dosahuje stejného cíle implementace operace řízené vynásobením `X` , která však používá několik čistých qubits pomocí `using` mechanismu.</span><span class="sxs-lookup"><span data-stu-id="c66f1-155">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="whats-next"></a><span data-ttu-id="c66f1-156">A co dál?</span><span class="sxs-lookup"><span data-stu-id="c66f1-156">What's Next?</span></span>
<span data-ttu-id="c66f1-157">Přečtěte si o [toku řízení](xref:microsoft.quantum.guide.controlflow) v Q #.</span><span class="sxs-lookup"><span data-stu-id="c66f1-157">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>