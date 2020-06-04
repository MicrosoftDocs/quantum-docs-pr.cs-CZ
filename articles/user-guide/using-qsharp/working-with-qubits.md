---
title: Práce s qubity
description: Popis výplně
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: 0deb0729a88c49798f32a22a943b935d383c570b
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327539"
---
# <a name="working-with-qubits"></a>Práce s qubity

Teď se zobrazila celá řada různých částí jazyka Q #. můžeme se dostat do široké nabídky a podívat se, jak qubits sami.

Všimněte si, že žádný z těchto příkazů není povolen v rámci těla funkce.
Jsou platné pouze v rámci operací.

## <a name="allocating-qubits"></a>Přidělování Qubits

### <a name="clean-qubits"></a>Vyčistit qubits

`using`Příkaz slouží k *přidělení* nového qubits pro použití během bloku příkazu.

Příkaz se skládá z klíčového slova `using` následovaných levou závorkou `(` , vazbou, uzavírací závorkou `)` a blokem příkazu, ve kterém bude qubits k dispozici.
Vazba se řídí stejným vzorem jako `let` příkazy: buď jeden symbol, nebo záznamovou sadu symbolů následovaný symbolem rovná `=` se, a buď jedinou hodnotou, nebo porovnáním řazené kolekce členů *inicializátorů*.

Inicializátory jsou k dispozici buď pro jeden qubit, který `Qubit()` je označen jako nebo jako pole qubits, `Qubit[n]` , kde `n` je `Int` výraz.
Třeba

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

Všechny qubits přidělené tímto způsobem začínají ve stavu $ \ket {0} $; v příkladu výše `register` je tak ve stavu $ \ket {00000} = \ket {0} \otimes \ket {0} \otimes \cdots \otimes \ket {0} $.
Na konci `using` bloku jsou všechny qubits přidělené tímto blokem okamžitě uvolněny a nelze je použít dále.

> [!WARNING]
> Cílové počítače očekávají, že qubits jsou ve stavu $ \ket {0} $ bezprostředně před zrušením přidělení, aby je bylo možné znovu použít a nabízet jiným `using` blokům pro přidělení.
> Kdykoli je to možné, použijte k vrácení libovolných přidělených qubits do $ \ket $ jednotnou operaci {0} .
> V případě potřeby je @"microsoft.quantum.intrinsic.reset" možné operaci použít k měření qubit a k použití tohoto výsledku měření, abyste zajistili, že se měřený qubit vrátí do $ \ket {0} $. Taková míra odstraní všechny entanglement se zbývajícími qubits a může tedy ovlivnit výpočet.


### <a name="borrowed-qubits"></a>Vypůjčený Qubits

`borrowing`Příkaz slouží k tomu, aby qubits k dispozici pro dočasné použití, které nemusejí být v určitém stavu.

Výpůjční mechanizmus umožňuje přidělení qubits, které lze použít jako pomocné místo během výpočtu.
Tyto qubits nejsou obvykle v čistém stavu, tj., nejsou nutně inicializovány ve známém stavu, například $ \ket {0} $.
Ty se často označují jako "nequbitsé", protože jejich stav je neznámý a může být dokonce entangled s ostatními částmi paměti počítače.

Vazba následuje stejný vzor a pravidla jako v `using` příkazu.
Třeba
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
Vypůjčený qubits je v neznámém stavu a na konci bloku příkazu se překročí rozsah.
Dlužník se zavazuje, že opustí qubits ve stejném stavu, ve kterém byly ve chvíli, kdy byly vypůjčené, tj. jejich stav na začátku a na konci bloku příkazu by měl být stejný.
Konkrétně se nejedná o klasický stav, což znamená, že ve většině případů by výpůjční rozsahy neměly obsahovat měření. 

Při výpůjčkě qubits se systém nejprve pokusí vyplňovat požadavek z qubits, které se používají, ale nejsou k dispozici během těla `borrowing` příkazu.
Pokud není dostatečná taková qubits, přidělí se nové qubits, aby se žádost dokončila.


Mezi známé případy použití undirty qubits jsou implementace více řízených CNOTch bran, které vyžadují jenom velmi málo qubits a implementaci přírůstku.
Podívejte se na [příklad výpůjčky Qubits](#borrowing-qubits-example) , kde vidíte příklad jejich použití v Q # nebo vytváření papírů [*pomocí 2n + 2 Qubits s modulárním násobení*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler a Svore 2017) pro algoritmus, který využívá vypůjčený Qubits.


## <a name="intrinsic-operations"></a>Vnitřní operace

Po přidělení může být qubit předán do funkcí a operací.
V některých případech to znamená, že program Q # může s qubit provádět, protože akce, které lze provést, jsou definovány jako operace.
Tyto operace podrobněji uvidíme v [vnitřních operacích a funkcích](xref:microsoft.quantum.libraries.standard.prelude), ale v současné době uvádíme několik užitečných operací, které se dají použít k interakci s qubits.

Za prvé, qubit Pauli Operators $X $, $Y $ a $Z $ jsou v Q # reprezentovány vnitřními operacemi `X` , `Y` a `Z` , z nichž každý má typ `(Qubit => Unit is Adj + Ctl)` .
Jak je popsáno v tématu [vnitřní operace a funkce](xref:microsoft.quantum.libraries.standard.prelude), můžeme si představit $X $ a tedy `X` také jako operaci překlápění.
Tato `X` operace umožňuje připravit stavy formuláře $ \ket{s_0 S_1 \dots S_N} $ pro některý z klasických bitových řetězců $s $:

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

Můžete také připravit stavy, jako je $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ a $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\sqrt {2} $, pomocí Hadamard Transforming $H $, který je reprezentován v Q # vnitřní operací `H : (Qubit => Unit is Adj + Ctl)` :

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

Pomocí `Measure` operace, která je vestavěnou vnitřní nejednotkovou operací, můžeme extrahovat klasické informace z objektu typu `Qubit` a přiřadit klasický údaj jako výsledek, který má rezervovaný typ `Result` , což značí, že výsledek již není ve stavu bez hodnoty.
Vstup do `Measure` je Pauli osa v koule Bloch, reprezentovaná hodnotou typu `Pauli` (pro instanci `PauliX` ) a hodnotou typu `Qubit` .

Jednoduchým příkladem je následující operace, která přiděluje jednu qubit ve stavu $ \ket {0} $, pak na ni aplikuje operaci Hadamard `H` a měří výsledek na `PauliZ` základě.

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

Mírně komplikovanější příklad je dán následující operací, která vrací logickou hodnotu, `true` Pokud jsou všechny qubits v registru typu `Qubit[]` v hodnotě nula, pokud se měří v zadaném Pauli a který vrací `false` jinak.

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

## <a name="borrowing-qubits-example"></a>Příklad výpůjčky Qubits

V Canon existují příklady, které používají `borrowing` klíčové slovo, například funkci `MultiControlledXBorrow` definovanou níže.
Pokud `controls` aplikace označuje qubits ovládacího prvku, který se má přidat k `X` operaci, pak se `Length(controls)-2` Tato implementace přidá do celkového počtu nezměněných ancillas.

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

Mějte na paměti, že `With` kombinátorem---ve své podobě, která se vztahuje na operace, které podporují sousední, tj. `WithA` ---byl v tomto příkladu proveden.
To je dobrý styl programování, protože přidání ovládacího prvku do struktur zahrnující `With` rozšíření šíří pouze vnitřní operaci.
Dále si všimněte, že zde jsou kromě `body` operace k `controlled` dispozici implementace těla operace, nikoli použití `controlled auto` příkazu.
Důvodem je to, že ví od struktury okruhu, jak snadno přidat další ovládací prvky, které jsou ve srovnání s přidáním řízení ke každé a každé samostatné bráně v nástroji užitečné `body` . 

Je povede k porovnání tohoto kódu s jinou funkcí Canon, `MultiControlledXClean` která dosahuje stejného cíle implementace operace řízené vynásobením `X` , která však používá několik čistých qubits pomocí `using` mechanismu. 

## <a name="next-steps"></a>Další kroky

Přečtěte si o [toku řízení](xref:microsoft.quantum.guide.controlflow) v Q #.