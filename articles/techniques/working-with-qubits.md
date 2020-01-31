---
title: Práce s Qubits
description: 'Práce s technikami Qubits-Q #'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: dc6db93dadc37534aece9624fe516125d919f8cd
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819990"
---
# <a name="working-with-qubits"></a>Práce s Qubits

Teď se zobrazila celá řada různých částí jazyka Q #. můžeme se dostat do široké nabídky a podívat se, jak qubits sami.

## <a name="allocating-qubits"></a>Přidělování Qubits

Nejprve pro získání qubit, které můžeme použít ve Q #, *přidělíme* qubits v rámci `using`ho bloku:

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

Libovolný qubits přidělený tímto způsobem začal ve stavu $ \ket{0}$; ve výše uvedeném příkladu je `register` tak ve stavu $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.
Na konci `using` bloku jsou všechny qubits přidělené tímto blokem okamžitě uvolněny a nelze je použít dále.

> [!WARNING]
> Cílové počítače očekávají, že qubits jsou ve stavu $ \ket{0}$ bezprostředně před zrušením přidělení, aby je bylo možné znovu použít a nabízet k ostatním `using`m blokům pro přidělení.
> Kdykoli je to možné, použijte k vrácení všech přidělených qubits do $ \ket{0}$ jednotnou operaci.
> V případě potřeby je možné místo toho použít operaci @"microsoft.quantum.intrinsic.reset" k měření qubit a k použití tohoto výsledku měření, abyste zajistili, že se měřený qubit vrátí do $ \ket{0}$. Taková míra odstraní všechny entanglement se zbývajícími qubits a může tedy ovlivnit výpočet.

## <a name="intrinsic-operations"></a>Vnitřní operace

Po přidělení může být qubit předán do funkcí a operací.
V některých případech to znamená, že program Q # může s qubit provádět, protože akce, které lze provést, jsou definovány jako operace.
Tyto operace podrobněji uvidíme v [vnitřních operacích a funkcích](xref:microsoft.quantum.libraries.standard.prelude), ale v současné době uvádíme několik užitečných operací, které se dají použít k interakci s qubits.

Za prvé, qubit Pauli Operators $X $, $Y $ a $Z $ jsou v Q # reprezentovány vnitřními operacemi `X`, `Y`a `Z`, z nichž každý má typ `(Qubit => Unit is Adj + Ctl)`.
Jak je popsáno v tématu [vnitřní operace a funkce](xref:microsoft.quantum.libraries.standard.prelude), můžeme si představit $X $ a proto se `X` jako operace překlápění nebo ne jako hradlo.
Operace `X` umožňuje připravit stavy formuláře $ \ket{s_0 s_1 \dots s_n} $ pro některý z klasických bitových řetězců $s $:

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
> Později se zobrazí více kompaktních způsobů psaní této operace, která nevyžaduje ruční řízení toku.

Také je možné připravit stavy, jako je $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ a $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ pomocí Hadamard Transform $H $, který je reprezentován v Q # vnitřní operací `H : (Qubit => Unit is Adj + Ctl)`:

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

## <a name="measurements"></a>Měření

Pomocí operace `Measure`, která je integrovanou vnitřní nejednotkovou operací, můžeme extrahovat klasické informace z objektu typu `Qubit` a přiřadit klasický údaj jako výsledek, který má rezervovaný typ `Result`, což značí, že výsledek již není ve stavu bez hodnoty.
Vstup pro `Measure` je Pauli osa v koule Bloch, reprezentovaná hodnotou typu `Pauli` (pro instanci `PauliX`) a hodnotou typu `Qubit`.

Jednoduchým příkladem je následující operace, která přiděluje jednu qubit ve stavu $ \ket{0}$, pak na ni aplikuje operaci Hadamard `H` a měří výsledek v `PauliZ`.

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

Mírně složitější příklad je dán následující operací, která vrací logickou hodnotu `true`, pokud všechny qubits v registru typu `Qubit[]` jsou v hodnotě nula při měření v zadaném Pauli a které vrací `false` jinak.

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

Jazyk Q # umožňuje, aby byl tok klasického řízení závislý na výsledcích měření qubits.
Tato funkce zase umožňuje implementovat výkonné pravděpodobnostní miniaplikace, které mohou snížit výpočetní náklady na implementaci unitaries.
Jako příklad můžete snadno implementovat vzory, které se označují jako *opakované a neúspěšné* (ru) v Q #.
Tyto ru vzory jsou pravděpodobnostní programy, které mají *očekávané* nízké náklady v rámci základních bran, ale u kterých se skutečné náklady závisí na skutečném běhu a skutečném proplutí různých možných větví.

Aby bylo možné zjednodušit vzorce opakování až do úspěchu (ru), Q # podporuje konstrukt.

```qsharp
repeat {
    statementBlock1
}
until (expression)
fixup {
    statementBlock2
}
```

kde `statementBlock1` a `statementBlock2` jsou nula nebo více příkazů Q # a `expression` libovolný platný výraz, který je vyhodnocen na hodnotu typu `Bool`.
V typickém případu použití následující operace Q # implementuje otočení kolem osy Irrational $ (I + 2i Z)/\sqrt{5}$ v koule Bloch. Toho je možné dosáhnout pomocí známého vzoru ru:

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

Tento příklad ukazuje použití proměnlivé proměnné `finished`, která je v rozsahu celého cyklu opakování až do opravy a která je inicializována před smyčkou a aktualizována v kroku opravy.

Nakonec ukážeme příklad ru vzoru pro přípravu stavového pole $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $, počínaje ze stavu $ \ket{+} $.
Viz také [ukázkový test jednotek, který je součástí standardní knihovny](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+⟩ state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+⟩ state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+⟩ state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+⟩ in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+⟩ state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

Významné programové funkce zobrazené v této operaci jsou složitější `fixup` součástí smyčky, která zahrnuje operace s nenáročnými na sebe, a použití příkazů `AssertProb` k zjištění pravděpodobnosti měření stavu u určitých bodů v programu.
Další informace o [`Assert`](xref:microsoft.quantum.intrinsic.assert) a [`AssertProb`ch](xref:microsoft.quantum.intrinsic.assertprob) operacích najdete v tématu [testování a ladění](xref:microsoft.quantum.techniques.testing-and-debugging) .
