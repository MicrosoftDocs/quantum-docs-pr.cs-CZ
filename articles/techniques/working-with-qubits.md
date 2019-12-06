---
title: Práce s Qubits | Microsoft Docs
description: Práce s Qubits
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: 477b358c3eba58b62926b4e9094770c9741cac92
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864249"
---
# <a name="working-with-qubits"></a><span data-ttu-id="97985-103">Práce s Qubits</span><span class="sxs-lookup"><span data-stu-id="97985-103">Working with Qubits</span></span> #

<span data-ttu-id="97985-104">Teď se zobrazila celá řada různých částí jazyka Q #. můžeme se dostat do široké nabídky a podívat se, jak qubits sami.</span><span class="sxs-lookup"><span data-stu-id="97985-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="97985-105">Přidělování Qubits</span><span class="sxs-lookup"><span data-stu-id="97985-105">Allocating Qubits</span></span> ##

<span data-ttu-id="97985-106">Nejprve pro získání qubit, které můžeme použít ve Q #, *přidělíme* qubits v rámci `using`ho bloku:</span><span class="sxs-lookup"><span data-stu-id="97985-106">First, to obtain a qubit that we can use in Q#, we *allocate* qubits within a `using` block:</span></span>

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

<span data-ttu-id="97985-107">Libovolný qubits přidělený tímto způsobem začal ve stavu $ \ket{0}$; ve výše uvedeném příkladu je `register` tak ve stavu $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="97985-107">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="97985-108">Na konci `using` bloku jsou všechny qubits přidělené tímto blokem okamžitě uvolněny a nelze je použít dále.</span><span class="sxs-lookup"><span data-stu-id="97985-108">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="97985-109">Cílové počítače očekávají, že qubits jsou ve stavu $ \ket{0}$ bezprostředně před zrušením přidělení, aby je bylo možné znovu použít a nabízet k ostatním `using`m blokům pro přidělení.</span><span class="sxs-lookup"><span data-stu-id="97985-109">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="97985-110">Kdykoli je to možné, použijte k vrácení všech přidělených qubits do $ \ket{0}$ jednotnou operaci.</span><span class="sxs-lookup"><span data-stu-id="97985-110">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="97985-111">V případě potřeby je možné místo toho použít operaci @"microsoft.quantum.intrinsic.reset" k měření qubit a k použití tohoto výsledku měření, abyste zajistili, že se měřený qubit vrátí do $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="97985-111">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="97985-112">Taková míra odstraní všechny entanglement se zbývajícími qubits a může tedy ovlivnit výpočet.</span><span class="sxs-lookup"><span data-stu-id="97985-112">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span> 

## <a name="intrinsic-operations"></a><span data-ttu-id="97985-113">Vnitřní operace</span><span class="sxs-lookup"><span data-stu-id="97985-113">Intrinsic Operations</span></span> ##

<span data-ttu-id="97985-114">Po přidělení může být qubit předán do funkcí a operací.</span><span class="sxs-lookup"><span data-stu-id="97985-114">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="97985-115">V některých případech to znamená, že program Q # může s qubit provádět, protože akce, které lze provést, jsou definovány jako operace.</span><span class="sxs-lookup"><span data-stu-id="97985-115">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="97985-116">Tyto operace podrobněji uvidíme v [vnitřních operacích a funkcích](xref:microsoft.quantum.libraries.standard.prelude), ale v současné době uvádíme několik užitečných operací, které se dají použít k interakci s qubits.</span><span class="sxs-lookup"><span data-stu-id="97985-116">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="97985-117">Za prvé, qubit Pauli Operators $X $, $Y $ a $Z $ jsou v Q # reprezentovány vnitřními operacemi `X`, `Y`a `Z`, z nichž každý má typ `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="97985-117">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="97985-118">Jak je popsáno v tématu [vnitřní operace a funkce](xref:microsoft.quantum.libraries.standard.prelude), můžeme si představit $X $ a proto se `X` jako operace překlápění nebo ne jako hradlo.</span><span class="sxs-lookup"><span data-stu-id="97985-118">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="97985-119">To umožňuje připravit stavy formuláře $ \ket{s_0 s_1 \dots s_n} $ pro některý z klasických bitových řetězců $s $:</span><span class="sxs-lookup"><span data-stu-id="97985-119">This lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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

operation Example() : Unit {

    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
    }
}
```

> [!TIP]
> <span data-ttu-id="97985-120">Později se zobrazí více kompaktních způsobů psaní této operace, která nevyžaduje ruční řízení toku.</span><span class="sxs-lookup"><span data-stu-id="97985-120">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="97985-121">Také je možné připravit stavy, jako je $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ a $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ pomocí Hadamard Transform $H $, který je reprezentován v Q # vnitřní operací `H : (Qubit => Unit is Adj + Ctl)`:</span><span class="sxs-lookup"><span data-stu-id="97985-121">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

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

## <a name="measurements"></a><span data-ttu-id="97985-122">Měření</span><span class="sxs-lookup"><span data-stu-id="97985-122">Measurements</span></span> ##

<span data-ttu-id="97985-123">Pomocí operace `Measure`, která je vestavěnou vnitřní nejednotkovou operací, můžeme extrahovat klasické informace z objektu typu `Qubit` a přiřadit klasický údaj jako výsledek, který má rezervovaný typ `Result`, což značí, že výsledek již není v nestránkovaném stavu.</span><span class="sxs-lookup"><span data-stu-id="97985-123">Using the `Measure` operation, which is a built in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span> <span data-ttu-id="97985-124">Vstup pro `Measure` je Pauli osa v koule Bloch, reprezentovaná objektem typu `Pauli` (tj. pro instanci `PauliX`) a objektem typu `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="97985-124">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by an object of type `Pauli` (i.e., for instance `PauliX`) and an object of type `Qubit`.</span></span> 

<span data-ttu-id="97985-125">Jednoduchým příkladem je následující operace, která vytvoří jeden qubit ve stavu $ \ket{0}$, pak na něj použije ``H`` bránu Hadamard a pak výsledek měří na základě `PauliZ`.</span><span class="sxs-lookup"><span data-stu-id="97985-125">A simple example is the following operation which creates one qubit in the $\ket{0}$ state, then applies a Hadamard gate ``H`` to it and then measures the result in the `PauliZ` basis.</span></span> 

```qsharp
operation MeasurementOneQubit () : Result {

    // The following using block creates a fresh qubit and initializes it 
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby creating the 
        // state 1/sqrt(2)(|0〉+|1〉). 
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

<span data-ttu-id="97985-126">Mírně složitější příklad je dán následující operací, která vrací logickou hodnotu `true`, pokud všechny qubits v registru typu `Qubit[]` jsou v hodnotě nula, pokud se měří v zadaném Pauli a `false` jinak.</span><span class="sxs-lookup"><span data-stu-id="97985-126">A slightly more complicated example is given by the following operation which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero, when measured in a specified Pauli basis and `false` otherwise.</span></span> 

```qsharp
operation AllMeasurementsZero (qs : Qubit[], pauli : Pauli) : Bool {

    mutable value = true;
    for (q in qs) {
        if ( Measure([pauli], [q]) == One ) {
            set value = false;
        }
    }
    return value;
}
```

<span data-ttu-id="97985-127">Jazyk Q # umožňuje závislosti toku klasického řízení při měření výsledků qubits.</span><span class="sxs-lookup"><span data-stu-id="97985-127">The Q# language allows dependencies of classical control flow on measurement results of qubits.</span></span> <span data-ttu-id="97985-128">To zase umožňuje implementovat výkonné pravděpodobnostní miniaplikace, které mohou snížit výpočetní náklady na implementaci unitaries.</span><span class="sxs-lookup"><span data-stu-id="97985-128">This in turn enables to implement powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span> <span data-ttu-id="97985-129">Jako příklad se dá snadno implementovat volání *Repeat-to-do-* v Q #, které představují pravděpodobnostní okruhy s *očekávanými* nízkými náklady z hlediska základních bran, ale u kterých skutečné náklady závisí na skutečném běhu a skutečném prochodu různých možných rozvětvení.</span><span class="sxs-lookup"><span data-stu-id="97985-129">As an example, it is easy to implement so-called *Repeat-Until-Success* in Q# which are probabilistic circuits that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span> 

<span data-ttu-id="97985-130">Aby bylo možné zjednodušit vzorce opakování až do úspěchu (ru), Q # podporuje konstrukt.</span><span class="sxs-lookup"><span data-stu-id="97985-130">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the construct</span></span>
```qsharp
repeat {
    statementBlock1 
}
until (expression)
fixup {
    statementBlock2
}
```
<span data-ttu-id="97985-131">kde `statementBlock1` a `statementBlock2` jsou nula nebo více příkazů Q # a `expression` libovolný platný výraz, který je vyhodnocen na hodnotu typu `Bool`.</span><span class="sxs-lookup"><span data-stu-id="97985-131">where `statementBlock1` and `statementBlock2` are zero or more Q# statements, and `expression` any valid expression that evaluates to a value of type `Bool`.</span></span> <span data-ttu-id="97985-132">V typickém případu použití následující okruh implementuje otočení kolem osy Irrational $ (I + 2i Z)/\sqrt{5}$ v koule Bloch.</span><span class="sxs-lookup"><span data-stu-id="97985-132">In a typical use case, the following circuit implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="97985-133">Toho je možné dosáhnout pomocí známého vzoru ru:</span><span class="sxs-lookup"><span data-stu-id="97985-133">This is accomplished by using a known RUS pattern:</span></span> 

```qsharp
operation RUScircuit (qubit : Qubit) : Unit {

    using(ancillas = Qubit[2]) {
        ApplyToEachA(H, ancillas);
        mutable finished = false;
        repeat {
            Controlled X(ancillas, qubit);
            S(qubit);
            Controlled X(ancillas, qubit);
            Z(qubit);
        }
        until(finished)
        fixup {
            if AllMeasurementsZero(ancillas, Xpauli) {
                set finished = true;
            }
        }
    }
}
```

<span data-ttu-id="97985-134">Tento příklad ukazuje použití proměnlivé proměnné `finished`, která je v rozsahu celého cyklu opakování až do opravy a která je inicializována před smyčkou a aktualizována v kroku opravy.</span><span class="sxs-lookup"><span data-stu-id="97985-134">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

<span data-ttu-id="97985-135">Nakonec ukážeme příklad ru vzoru pro přípravu stavového pole $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $, počínaje ze stavu $ \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="97985-135">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span> <span data-ttu-id="97985-136">Viz také [ukázkový test jednotek, který je součástí standardní knihovny](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="97985-136">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span> 

```qsharp
operation RepeatUntilSuccessStatePreparation( target : Qubit ) : Unit {

    using( ancilla = Qubit() ) {
        H(ancilla);
        repeat {
            // We expect target and ancilla qubit to be in |+⟩ state.
            AssertProb( 
                [PauliX], [target], Zero, 1.0, 
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb( 
                [PauliX], [ancilla], Zero, 1.0,
                "ancilla qubit should be in the |+⟩ state", 1e-10 );
                
            Adjoint T(ancilla);
            CNOT(target, ancilla);
            T(ancilla);

            // The probability of measuring |+⟩ state on ancilla is 3/4.
            AssertProb( 
                [PauliX], [ancilla], Zero, 3. / 4., 
                "Error: the probability to measure |+⟩ in the first 
                ancilla must be 3/4",
                1e-10);

            // If we get measurement outcome Zero, we prepare the required state 
            let outcome = Measure([PauliX], [ancilla]);
        }
        until( outcome == Zero )
        fixup {
            // Bring ancilla and target back to |+⟩ state
            if( outcome == One ) {
                Z(ancilla);
                X(target);
                H(target);
            }
        }
        // Return ancilla back to Zero state
        H(ancilla);
    }
}
```
 
<span data-ttu-id="97985-137">Významné programové funkce uvedené v této operaci jsou složitější `fixup` součástí smyčky, která zahrnuje operace s nenáročnými na sebe, a použití příkazů `AssertProb` k zjištění pravděpodobnosti měření stavu nečinnosti v určitých bodech v programu.</span><span class="sxs-lookup"><span data-stu-id="97985-137">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span> <span data-ttu-id="97985-138">Další informace o `Assert` a `AssertProb`ch příkazech naleznete v tématu [testování a ladění](xref:microsoft.quantum.techniques.testing-and-debugging) .</span><span class="sxs-lookup"><span data-stu-id="97985-138">See also [Testing and debugging](xref:microsoft.quantum.techniques.testing-and-debugging) for more information about `Assert` and `AssertProb` statements.</span></span> 
