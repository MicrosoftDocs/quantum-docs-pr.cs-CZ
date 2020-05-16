---
title: 'Tok řízení v Q #'
description: Smyčky, podmíněnéy atd.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: c534e016fcb8b50e66c11ca29c253ba0512acc6e
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430947"
---
# <a name="control-flow-in-q"></a>Tok řízení v Q #

V rámci operace nebo funkce se každý příkaz provede v uvedeném pořadí, podobně jako u nejběžnějších imperativních klasických jazyků.
Tento tok řízení lze změnit, ale třemi různými způsoby:

- `if`učiněn
- `for`smyčky
- `repeat`-`until`smyčky

Další informace o druhém odložení [najdete níže](#repeat-until-success-loop).
`if` `for` Konstrukce toku ovládacích prvků a však budou mít známý smysl pro většinu klasických programovacích jazyků.

Důležité jsou `for` smyčky a `if` příkazy mohou být použity i v operacích, pro které jsou automaticky generovány specializace. V takovém případě sousední `for` smyčka smyčky obrátí směr a převezme sousedícího typu každé iterace.
Tento postup se řídí principem "obuv-a-SOCKS": Pokud chcete vrátit zpět vložení do aplikace SOCKS a pak provést operaci, je nutné vrátit zpět na obuv a pak zrušit uvedení na SOCKS.
V takovém případě stále ještě méně se nedaří vyzkoušet a pořídit si své služby SOCKS, dokud budete mít pořád na svou obuv.

## <a name="if-else-if-else"></a>If, else-if, else

`if`Příkaz podporuje podmíněné spuštění.
Skládá se z klíčového slova `if` , otevřené závorky `(` , logického výrazu, uzavírací závorky `)` a bloku příkazu (blok _then_ ).
Za tímto může následovat libovolný počet klauzulí else-if, každý z nich se skládá z klíčového slova `elif` , otevírací závorky `(` , logického výrazu, uzavírací závorky `)` a bloku příkazu (blok _else-if_ ).
Nakonec může být příkaz volitelně dokončen s klauzulí else, která se skládá z klíčového slova `else` následovaného jiným blokem příkazu (blok _Else_ ).

`if`Podmínka je vyhodnocena a je-li nastavena na hodnotu true, je spuštěn blok po.
Pokud je podmínka NEPRAVDA, vyhodnotí se první podmínka else if; Pokud má hodnotu true, je spuštěn blok else-if.
V opačném případě se otestuje druhý blok else-if a třetí a tak dále, dokud není zjištěna buď klauzule s podmínkou true, nebo nejsou k dispozici další klauzule else-if.
Pokud je původní podmínka IF a všechny klauzule else-if vyhodnoceny jako NEPRAVDA, je spuštěn blok else, pokud byl poskytnut jeden.

Všimněte si, že libovolný blok je spuštěný ve svém vlastním oboru.
Vazby provedené v `if` `elif` bloku, nebo nejsou `else` po konci viditelné.

Například:

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
nebo
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a>Smyčka for

`for`Příkaz podporuje iteraci v rozsahu celého čísla nebo nad polem.
Příkaz se skládá z klíčového slova `for` , otevírací závorky `(` následovaný symbolem nebo řazenou kolekcí členů, klíčovým slovem `in` , výrazem typu `Range` nebo polem, uzavírací závorky `)` a bloku příkazu.

Blok příkazu (tělo smyčky) je proveden opakovaně s definovanými symboly (proměnné smyčky) svázané s každou hodnotou v rozsahu nebo poli.
Všimněte si, že pokud je výraz Range vyhodnocen jako prázdný rozsah nebo pole, text nebude proveden vůbec.
Výraz je plně vyhodnocen před vstupem do smyčky a při provádění smyčky se nemění.

Proměnná smyčky je svázána s každým vchodem do těla smyčky a na konci těla není svázána.
Konkrétně proměnná smyčky není svázána po dokončení smyčky for.
Vazba deklarovaného symbolu je neměnná a řídí se stejnými pravidly jako jiné vazby proměnných. 

V některých příkladech `qubits` je Supposing registrem qubits (tj. typu `Qubit[]` ), 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```
Všimněte si, že na konci jsme využili binární operátor aritmetické a posunutí vlevo, `<<<` Podrobnosti o tom, které lze najít v [numerických výrazech](xref:microsoft.quantum.guide.expressions#numeric-expressions) .


## <a name="repeat-until-success-loop"></a>Opakování do smyčky po úspěšném dokončení

Jazyk Q # umožňuje, aby byl tok klasického řízení závislý na výsledcích měření qubits.
Tato funkce zase umožňuje implementovat výkonné pravděpodobnostní miniaplikace, které mohou snížit výpočetní náklady na implementaci unitaries.
Jako příklad můžete snadno implementovat vzory, které se označují jako *opakované a neúspěšné* (ru) v Q #.
Tyto ru vzory jsou pravděpodobnostní programy, které mají *očekávané* nízké náklady v rámci základních bran, ale u kterých se skutečné náklady závisí na skutečném běhu a skutečném proplutí různých možných větví.

Aby bylo možné zjednodušit vzorce opakování až do úspěchu (ru), Q # podporuje konstrukce.

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

kde `expression` je libovolný platný výraz, který je vyhodnocen jako hodnota typu `Bool` .
Tělo smyčky se provede a podmínka se vyhodnotí.
Pokud je podmínka pravdivá, je příkaz dokončen; v opačném případě se oprava provede a příkaz se znovu spustí počínaje textem smyčky.

Všechny tři části smyčky Repeat/dokud (tělo, test a oprava) se považují za jeden obor *pro každé opakování*, takže symboly, které jsou v těle textu, jsou k dispozici v testu a v opravě.
Provedení opravy ale ukončí rozsah příkazu, takže vazby symbolů provedené během těla nebo opravy nejsou v dalších opakováních k dispozici.

Kromě toho `fixup` je příkaz často užitečný, ale není vždy nezbytný.
V případě, že není potřeba, konstrukce
```qsharp
repeat {
    // do stuff
}
until (expression);
```
je také platným vzorem ru.

V dolní části této stránky uvádíme několik [příkladů cyklů ru](#repeat-until-success-examples).

> [!TIP]   
> Nepoužívejte v rámci funkcí smyčky Repeat-do-úspěch. Odpovídající funkce jsou k dispozici v průběhu cyklů ve funkcích. 

## <a name="while-loop"></a>Smyčka while

Vzory opakování až po úspěchu mají velmi stejný zápis na základě stavu. Jsou běžně používány v určitých třídách algoritmů pro stav, a proto je konstrukce vyhrazeného jazyka v Q #. Nicméně cykly, které jsou přerušeny na základě podmínky a jejichž délka spuštění je tudíž neznámá v době kompilace, je nutné zpracovat zvláštní péčí v modulu runtime. Jejich použití v rámci funkcí na druhé straně je neproblematické, protože obsahují pouze kód, který bude spuštěn na konvenčním (nestránkovaném) hardwaru. 

Q # proto podporuje použití smyčky while pouze v rámci funkcí. `while`Příkaz se skládá z klíčového slova `while` , otevřené závorky `(` , podmínky (tj. logický výraz), uzavírací závorky `)` a bloku příkazu.
Blok příkazu (tělo smyčky) je proveden, pokud je podmínka vyhodnocena jako `true` .

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a>Return – příkaz

Příkaz return ukončí provádění operace nebo funkce a vrátí hodnotu volajícímu.
Skládá se z klíčového slova `return` , následovaný výrazem příslušného typu a ukončující středník.

Navrácená instance, která vrací prázdnou řazenou kolekci členů, nevyžaduje `()` příkaz return.
Pokud se požaduje předčasné ukončení, `return ()` může se v tomto případě použít.
Volat, které vracejí jiný typ, vyžadují konečný návratový příkaz.

V rámci operace není maximální počet návratových příkazů.
Kompilátor může vygenerovat upozornění, pokud příkazy následují příkaz return v rámci bloku.

Například:
```qsharp
return 1;
```
nebo
```qsharp
return ();
```
nebo
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a>Příkaz selhání

Příkaz selhání ukončí provádění operace a vrátí volajícímu hodnotu chyby.
Skládá se z klíčového slova `fail` následovaných řetězcem a zakončeným středníkem.
Řetězec se vrátí do ovladače klasického rozhraní jako chybová zpráva.

Počet příkazů selhání v rámci operace není nijak omezen.
Kompilátor může vygenerovat upozornění, pokud příkazy následují po příkazu neúspěchu v rámci bloku.

Například:
```qsharp
fail $"Impossible state reached";
```
nebo použití [interpolované řetězce](xref:microsoft.quantum.guide.expressions#interpolated-strings)
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a>Příklady opakování do až po úspěch

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a>RU vzor pro jednoduché qubit otočení o ose Irrational 

V typickém případu použití následující operace Q # implementuje otočení kolem osy Irrational $ (I + 2i Z)/\sqrt {5} $ v koule Bloch. Toho je možné dosáhnout pomocí známého vzoru ru:

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

### <a name="rus-loop-with-mutable-variable-in-scope"></a>Smyčka ru se proměnlivou proměnnou v oboru

Tento příklad ukazuje použití proměnlivé proměnné, `finished` která je v rozsahu celého cyklu opakování až do opravy a která je inicializována před smyčkou a aktualizována v kroku opravy.

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a>RU bez`fixup`

Například následující kód je okruh pravděpodobnostní, který implementuje důležitou rotující bránu $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ pomocí `H` `T` bran a.
Smyčka končí v průměru v $ \frac {8} {5} $ opakování.
Další podrobnosti najdete v tématu [*opakování až po úspěch: nedeterministické rozklady qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick a Svore, 2014).

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a>RU pro přípravu stavu pro stav

Nakonec ukážeme příklad ru vzoru pro přípravu stavu s hodnotou # \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, počínaje ze stavu $ \ket{+} $.
Viz také [ukázkový test jednotek, který je součástí standardní knihovny](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
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

Významné programové funkce zobrazené v této operaci jsou složitější `fixup` součástí smyčky, která zahrnuje operace s jednou částí, a použití `AssertProb` příkazů k zjištění pravděpodobnosti měření stavu u určitých bodů v programu.
Viz také [testování a ladění](xref:microsoft.quantum.guide.testingdebugging) pro další informace o [`Assert`](xref:microsoft.quantum.intrinsic.assert) [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operacích a.


## <a name="whats-next"></a>A co dál?
Přečtěte si o [testování a ladění](xref:microsoft.quantum.guide.testingdebugging) v Q #.