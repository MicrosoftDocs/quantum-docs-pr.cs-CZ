---
title: Práce s Qubits | Microsoft Docs
description: Práce s Qubits
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: d1a8ccc9423a9a04e12bc98e3783790232b2f5d8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183467"
---
# <a name="working-with-qubits"></a>Práce s Qubits #

Teď se zobrazila celá řada různých částí jazyka Q #. můžeme se dostat do široké nabídky a podívat se, jak qubits sami.

## <a name="allocating-qubits"></a>Přidělování Qubits ##

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

## <a name="intrinsic-operations"></a>Vnitřní operace ##

Po přidělení může být qubit předán do funkcí a operací.
V některých případech to znamená, že program Q # může s qubit provádět, protože akce, které lze provést, jsou definovány jako operace.
Tyto operace podrobněji uvidíme v [vnitřních operacích a funkcích](xref:microsoft.quantum.libraries.standard.prelude), ale v současné době uvádíme několik užitečných operací, které se dají použít k interakci s qubits.

Za prvé, qubit Pauli Operators $X $, $Y $ a $Z $ jsou v Q # reprezentovány vnitřními operacemi `X`, `Y`a `Z`, z nichž každý má typ `(Qubit => Unit is Adj + Ctl)`.
Jak je popsáno v tématu [vnitřní operace a funkce](xref:microsoft.quantum.libraries.standard.prelude), můžeme si představit $X $ a proto se `X` jako operace překlápění nebo ne jako hradlo.
To nám umožní připravit stavy formuláře $ \ket{s_0 S_1 \dots S_N} $ pro některý z klasických bitových řetězců $s $:

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
> Později se zobrazí více kompaktních způsobů psaní této operace, která nevyžaduje ruční řízení toku.

Můžeme také připravit stavy, jako je $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ a $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ pomocí transformace Hadamard $H $ , který je reprezentován v Q # vnitřní operací `H : (Qubit => Unit is Adj + Ctl)`:

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

## <a name="measurements"></a>Měření ##

Pomocí operace `Measure`, která je vestavěnou vnitřní nejednotkovou operací, můžeme extrahovat klasické informace z objektu typu `Qubit` a přiřadit klasický údaj jako výsledek, který má rezervovaný typ `Result`, což značí, že výsledek není. delší stav Vstup pro `Measure` je Pauli osa v koule Bloch, reprezentovaná objektem typu `Pauli` (tj. pro instanci `PauliX`) a objektem typu `Qubit`. 

Jednoduchým příkladem je následující operace, která vytvoří jeden qubit ve stavu $ \ket{0}$, pak na něj použije ``H`` bránu Hadamard a pak výsledek měří na základě `PauliZ`. 

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

Mírně složitější příklad je dán následující operací, která vrací logickou hodnotu `true`, pokud všechny qubits v registru typu `Qubit[]` jsou v hodnotě nula, pokud se měří v zadaném Pauli a `false` jinak. 

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

Jazyk Q # umožňuje závislosti toku klasického řízení při měření výsledků qubits. To zase umožňuje implementovat výkonné pravděpodobnostní miniaplikace, které mohou snížit výpočetní náklady na implementaci unitaries. Jako příklad je možné ji snadno implementovat *tak, aby se v Q* # pravděpodobnostní okruhy, které mají *očekávané* nízké náklady, ale na základě základních bran, ale pravdivé náklady závisí na skutečném běhu a skutečném prokládání různých možných rozvětvení. 

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
kde `statementBlock1` a `statementBlock2` jsou nula nebo více příkazů Q # a `expression` libovolný platný výraz, který je vyhodnocen na hodnotu typu `Bool`. V typickém případu použití následující okruh implementuje otočení kolem osy Irrational $ (I + 2i Z)/\sqrt{5}$ v koule Bloch. Toho je možné dosáhnout pomocí známého vzoru ru: 

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

Tento příklad ukazuje použití proměnlivé proměnné `finished`, která je v rozsahu celého cyklu opakování až do opravy a která je inicializována před smyčkou a aktualizována v kroku opravy.

Nakonec ukážeme příklad ru vzoru pro přípravu stavového pole $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $, počínaje ze stavu $ \ket{+} $. Viz také [ukázkový test jednotek, který je součástí standardní knihovny](https://github.com/Microsoft/Quantum/blob/master/Samples/src/UnitTesting/RepeatUntilSuccessCircuits.qs): 

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
 
Důležité programové funkce uvedené v této operaci jsou složitější `fixup` součástí smyčky, která zahrnuje operace s nenáročnými na sebe, a použití příkazů `AssertProb` k zjištění pravděpodobnosti měření stavu nečinnosti v určitých bodech v editoru. Další informace o `Assert` a `AssertProb`ch příkazech naleznete v tématu [testování a ladění](xref:microsoft.quantum.techniques.testing-and-debugging) . 
