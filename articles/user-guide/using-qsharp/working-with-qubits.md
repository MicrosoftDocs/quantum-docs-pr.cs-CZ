---
title: Práce s qubity
description: Popis výplně
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6808a852ee0de7d3a38ea44e9637eeaa6bea382a
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867858"
---
# <a name="working-with-qubits"></a>Práce s qubity

Qubits jsou zásadním objektem informací ve výpočetním prostředí. Obecné seznámení s qubits najdete v tématu [porozumění výpočetnímu](xref:microsoft.quantum.overview.understanding)prostředí a podrobně hlouběji do jejich matematické reprezentace, viz [qubit](xref:microsoft.quantum.concepts.qubit). 

Tento článek popisuje, jak používat qubits v programu a pracovat s nimi Q# . 

> [!IMPORTANT]
>Žádný z příkazů popsaných v tomto článku není platný v těle funkce. Jsou platné pouze v rámci operací.

## <a name="allocating-qubits"></a>Přidělování Qubits

Vzhledem k tomu, že fyzický qubits jsou cenným prostředkem v počítači, který je součástí úlohy, je nutné se ujistit, že jsou používány co nejúčinnějším způsobem.
V takovém případě je třeba říct, že Q# chcete *přidělit* qubits pro použití v rámci konkrétního bloku příkazu.
Můžete přidělit qubits jako jeden qubit nebo jako pole qubits, které se označuje jako *registr*. 

### <a name="clean-qubits"></a>Vyčistit qubits

Použijte `using` příkaz k přidělení nového qubits pro použití během bloku příkazu.

Příkaz se skládá z klíčového slova `using` , za nímž následuje vazba uzavřená v závorkách `( )` a blok příkazů, ve kterém je qubits k dispozici.
Vazba se řídí stejným vzorem jako `let` příkazy: buď jeden symbol, nebo záznamovou sadu symbolů následovaný symbolem rovná `=` se, a buď jedinou hodnotou, nebo porovnáním řazené kolekce členů *inicializátorů*.

Inicializátory jsou k dispozici buď pro jeden qubit, který `Qubit()` je označen jako nebo jako pole qubits, `Qubit[n]` , kde `n` je `Int` výraz.
Příklad:

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

Libovolný qubits přidělený tímto způsobem se spustí ve stavu $ \ket {0} $. V předchozím příkladu `auxiliary` je tedy jedna qubit ve stavu $ \ket {0} $ a `register` je ve stavu pět-qubit $ \ket {00000} = \ket {0} {0} {0} \otimes \ket \otimes \cdots \otimes \ket.
Na konci `using` bloku jsou všechny qubits přidělené tímto blokem okamžitě uvolněny a nelze je použít dále.

> [!WARNING]
> Cílové počítače můžou znovu použít zrušení přidělení qubits a nabízet je ostatním `using` blokům pro přidělení. V takovém případě cílový počítač očekává, že qubits jsou ve stavu $ \ket {0} $ bezprostředně před zrušením přidělení.
> Kdykoli je to možné, použijte k vrácení libovolných přidělených qubits do $ \ket $ jednotnou operaci {0} .
> V případě potřeby můžete použít @"microsoft.quantum.intrinsic.reset" operaci, která vrátí qubit do $ \ket $ tím, že {0} ji odměří a podmíněně provede operaci založenou na výsledku. Taková míra ničí všechny entanglement se zbývajícími qubits a může tedy ovlivnit výpočet.


### <a name="borrowed-qubits"></a>Vypůjčený Qubits

Použijte `borrowing` příkaz k přidělení qubits pro dočasné použití, které nemusí být v určitém stavu.

V průběhu výpočtu můžete použít vypůjčené qubits jako pomocné místo.
Tyto qubits nejsou obecně v čistém stavu, to znamená, že nejsou nutně inicializovány ve známém stavu, například $ \ket {0} $.
Ty se často označují jako "nequbitsé", protože jejich stav je neznámý a může být dokonce entangled s ostatními částmi paměti počítače.

Vazba následuje stejný vzor a pravidla jako `using` příkaz.
Příklad:
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
Vypůjčený qubits je v neznámém stavu a na konci bloku příkazu se překročí rozsah.
Dlužník se zavazuje, že opustí qubits ve stejném stavu, ve kterém byly při jejich vypůjčení. To znamená, že jejich stav na začátku a na konci bloku příkazu by měl být stejný.
Vzhledem k tomu, že tento stav není nutně klasický, ve většině případů se zapůjčení oborů nesmí obsahovat měření. 

Při výpůjčkě qubits se systém nejprve pokusí vyplnit požadavek z qubits, které se používají, ale během těla příkazu se k němu nepoužívá `borrowing` .
Pokud není dostatek takových qubits, přidělí nové qubits k dokončení žádosti.

Mezi známé případy použití undirty qubits jsou implementace více řízených CNOTch bran, které vyžadují jenom velmi málo qubits a implementaci přírůstku.
Příklad použití v Q# najdete v tématu [výpůjčka Qubits příklad](#borrowing-qubits-example) v tomto článku nebo vytváření papírů [*pomocí 2n + 2 Qubits s modulárním násobení*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler a Svore 2017) pro algoritmus, který využívá vypůjčený Qubits.

## <a name="intrinsic-operations"></a>Vnitřní operace

Po přidělení můžete předat qubit funkcím a operacím.
V některých případech to znamená, že Q# program může s qubit provádět, protože akce, které lze provést, jsou definovány jako operace.

Tento článek popisuje několik užitečných Q# operací, které můžete použít k interakci s qubits.
Další podrobnosti o těchto a dalších funkcích najdete v tématu [vnitřní operace a funkce](xref:microsoft.quantum.libraries.standard.prelude). 

Za prvé, qubit Pauli Operators $X $, $Y $ a $Z $ jsou reprezentovány v rámci Q# vnitřních operací [`X`](xref:microsoft.quantum.intrinsic.x) , [`Y`](xref:microsoft.quantum.intrinsic.y) a [`Z`](xref:microsoft.quantum.intrinsic.z) , z nichž každý má typ `(Qubit => Unit is Adj + Ctl)` .

Jak je popsáno v tématu [vnitřní operace a funkce](xref:microsoft.quantum.libraries.standard.prelude), uvažujte o $X $, a to proto, že se jedná o `X` operaci PŘEklápění nebo ne o hradlo.
Operaci můžete použít `X` k přípravě stavů ve formátu $ \ket{s_0 S_1 \dots S_N} $ pro některý z klasických bitových řetězců $s $:

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
> Později se zobrazí více kompaktních způsobů psaní této operace, která nevyžaduje ruční tok řízení.

Můžete také připravit stavy, jako je $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ a $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\sqrt {2} $, pomocí Hadamard Transforming $H $, který je reprezentován Q# vnitřní operací [`H`](xref:microsoft.quantum.intrinsic.h) (také typ (qubit => jednotka je ADJ + CTL)):

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

## <a name="measurements"></a>Měření

Měření jednotlivých qubits se dají provádět v různých základech, z nichž každý představuje Pauli osa v [oblasti Bloch](xref:microsoft.quantum.glossary#bloch-sphere).
*Výpočetní základ* odkazuje na `PauliZ` základ a je nejběžnějším základem pro měření.

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a>Měření jediného qubitu v `PauliZ` základu

Použijte [`M`](xref:microsoft.quantum.intrinsic.m) operaci, která je vestavěnou vnitřní nejednotkovou operací, k měření jediného qubitu v `PauliZ` základu a k tomu ke výsledku přiřadíte klasický údaj.
`M`má rezervovaný návratový typ, `Result` který může převzít pouze hodnoty `Zero` nebo `One` odpovídající měřené stavy $ \ket {0} $ nebo $ \ket {1} $ – označuje, že výsledek již není ve stavu bez hodnoty.

Jednoduchým příkladem je následující operace, která přiděluje jednu qubit ve stavu $ \ket {0} $, pak na ni aplikuje operaci Hadamard `H` a měří výsledek na `PauliZ` základě.

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

### <a name="measure-one-or-more-qubits-in-specific-bases"></a>Měření jednoho nebo více qubits v konkrétních základech

Chcete-li změřit pole jednoho nebo více qubits v konkrétních základech, můžete použít [`Measure`](xref:microsoft.quantum.intrinsic.measure) operaci.

Vstupy pro `Measure` jsou pole `Pauli` typů (například `[PauliX, PauliZ, PauliZ]` ) a pole qubits.

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

Všimněte si, že tento příklad se pořád provádí jenom `Measure` na jednotlivých qubits po jednom, ale operace se dá rozšířit na společné měření více qubits.

## <a name="borrowing-qubits-example"></a>Příklad výpůjčky Qubits

Ve Canon jsou příklady, které používají `borrowing` klíčové slovo, jako je například následující funkce `MultiControlledXBorrow` . Pokud `controls` aplikace označuje qubits ovládacího prvku, že se má přidat k `X` operaci, pak počet nezměněných [ancillas](xref:microsoft.quantum.glossary#ancilla) přidaných touto implementací je `Length(controls)-2` .

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

Všimněte si, že tento příklad používá rozsáhlé použití `With` kombinátorem ve formě, který platí pro operace, které podporují sousední, například `WithA` .
To je dobrý styl programování, protože přidání ovládacího prvku do struktur zahrnující `With` rozšíření šíří pouze vnitřní operaci.
Všimněte si také, že kromě `body` operace `controlled` byla explicitně poskytnuta implementace těla operace, nikoli `controlled auto` příkaz k příkazu.
Důvodem je to, že kvůli struktuře okruhu je snadné přidat další ovládací prvky, které jsou ve srovnání s přidáním řízení ke každé bráně v nástroji užitečné `body` . 

Je povede k porovnání tohoto kódu s jinou funkcí Canon, `MultiControlledXClean` která dosahuje stejného cíle implementace operace řízené vynásobením `X` , která však používá několik čistých qubits pomocí `using` mechanismu. 

## <a name="next-steps"></a>Další kroky

Přečtěte si o [toku řízení](xref:microsoft.quantum.guide.controlflow) v nástroji Q# .