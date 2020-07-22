---
title: 'Tok řízení v Q #'
description: Smyčky, podmíněnéy atd.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: b652736168a71b905deaf7c4fdb29a8751b3dfaf
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870987"
---
# <a name="control-flow-in-q"></a>Tok řízení v Q #

V rámci operace nebo funkce každý příkaz běží v uvedeném pořadí, podobně jako ostatní běžně imperativní klasické jazyky.
Tok řízení lze však upravit třemi různými způsoby:

* `if`učiněn
* `for`smyčky
* `repeat-until-success`smyčky

`if` `for` Konstrukce toku ovládacích prvků a postupují ve známém smyslu pro většinu klasických programovacích jazyků. [`Repeat-until-success`](#repeat-until-success-loop)smyčky jsou popsány dále v tomto článku.

Důležité je, `for` smyčky a `if` příkazy lze použít v operacích, pro které jsou automaticky generovány [specializace](xref:microsoft.quantum.guide.operationsfunctions) . V tomto scénáři sousední `for` smyčka smyčky obrátí směr a převezme souseda pro každou iteraci.
Tato akce následuje po principu "obuv-a-SOCKS": Pokud chcete vrátit zpět do aplikace SOCKS a potom provést operaci, musíte zrušit uvedení na obuv a pak zrušit vložení na SOCKS. 

## <a name="if-else-if-else"></a>If, else-if, else

`if`Příkaz podporuje podmíněné spuštění.
Skládá se z klíčového slova `if` , logického výrazu v závorkách a bloku příkazu (blok _then_ ).
Volitelně může následovat libovolný počet klauzulí else-if, z nichž každá se skládá z klíčového slova `elif` , logického výrazu v závorkách a bloku příkazu (blok _else-if_ ).
Nakonec příkaz může volitelně končit klauzulí else, která se skládá z klíčového slova `else` následovaného jiným blokem příkazu (blok _Else_ ).

`if`Podmínka je vyhodnocena a je-li nastavena na *hodnotu true*, je spuštěn blok *a* .
Pokud je podmínka *NEPRAVDA*, vyhodnotí se první podmínka else if; Pokud je to pravda, pak je spuštěn blok *else-if* .
V opačném případě se druhý blok else-if vyhodnocuje a pak třetí a tak dále, dokud není nalezena klauzule s podmínkou true nebo pokud nejsou k dispozici další klauzule else-if.
Pokud je původní podmínka *if* a všechny klauzule else-if vyhodnoceny jako *false*, je spuštěn blok *Else* , pokud je k dispozici.

Všimněte si, že všechny spuštěné bloky se spustí v rámci svého vlastního oboru.
Vazby provedené v `if` `elif` bloku, nebo nejsou `else` po ukončení bloku viditelné.

Příklad:

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

`for`Příkaz podporuje iteraci v celé celočíselné oblasti nebo poli.
Příkaz se skládá z klíčového slova `for` následovaných řazenou kolekcí členů symbolu nebo symbolu, klíčového slova `in` a výrazu typu `Range` nebo pole, vše v závorkách a bloku příkazu.

Blok příkazu (tělo smyčky) se opakovaně spouští s definovaným symbolem (proměnná smyčky) svázaná s každou hodnotou v rozsahu nebo poli.
Všimněte si, že pokud je výraz Range vyhodnocen jako prázdný rozsah nebo pole, tělo se nespustí vůbec.
Výraz je plně vyhodnocen před vstupem do smyčky a při provádění smyčky se nemění.

Proměnná smyčky je svázána s každým vchodem do těla smyčky a není vázána na konci těla.
Proměnná smyčky není svázána po dokončení smyčky for.
Vazba proměnné smyčky je neměnná a řídí se stejnými pravidly jako jiné vazby proměnných. 

V těchto příkladech `qubits` je registr qubits (tj. typu `Qubit[]` ), 

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

Všimněte si, že na konci jsme využili binární operátor aritmetické a posunutí vlevo, `<<<` . Další informace najdete v tématu [číselné výrazy](xref:microsoft.quantum.guide.expressions#numeric-expressions).

## <a name="repeat-until-success-loop"></a>Opakování do smyčky po úspěšném dokončení

Jazyk Q # umožňuje, aby byl tok klasického řízení závislý na výsledcích měření qubits.
Tato funkce zase umožňuje implementovat výkonné pravděpodobnostní miniaplikace, které mohou snížit výpočetní náklady na implementaci unitaries.
Příklady tohoto příkladu jsou vzory *Repeat-to-Success* (ru) v Q #.
Tyto ru vzory jsou pravděpodobnostní programy, které mají *očekávané* nízké náklady v souvislosti s základními branami; vzniklé náklady závisí na skutečném běhu a prokládání několika možných větví.

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
Tělo smyčky se spustí a podmínka se vyhodnotí.
Pokud je podmínka pravdivá, je příkaz dokončen; v opačném případě se oprava spustí a příkaz se spustí znovu, počínaje textem smyčky.

Všechny tři části smyčky ru (tělo, test a oprava) se považují za jeden obor *pro každé opakování*, takže symboly, které jsou svázané s textem, jsou k dispozici v testu i v opravě.
Nicméně dokončení provádění opravy ukončí rozsah příkazu, takže vazby symbolů provedené během těla nebo opravy nejsou k dispozici v následných opakováních.

Kromě toho `fixup` je příkaz často užitečný, ale není vždy nezbytný.
V případě, že není potřeba, konstrukce

```qsharp
repeat {
    // do stuff
}
until (expression);
```

je také platným vzorem ru.

Další příklady a podrobnosti najdete v [příkladech Zopakování kroků](#repeat-until-success-examples) v tomto článku.

> [!TIP]   
> Nepoužívejte v rámci funkcí smyčky Repeat-do-úspěch. Použijte *while* k zajištění odpovídajících funkcí v rámci funkcí. 

## <a name="while-loop"></a>Smyčka while

Vzory opakování až po úspěchu mají velmi stejný zápis na základě stavu. Jsou široce používány v určitých třídách algoritmů pro stav, a to v rámci třídy Q #. Nicméně cykly, které jsou přerušeny na základě podmínky a jejichž délka spuštění je tedy neznámá v době kompilace, jsou zpracovávány zvláštní péčí v modulu runtime. Jejich použití v rámci funkcí je však neproblematické, protože tyto smyčky obsahují pouze kód, který běží na konvenčním (nestránkovaném) hardwaru. 

Q #, proto podporuje použití smyčky while pouze v rámci funkcí. `while`Příkaz se skládá z klíčového slova `while` , logického výrazu v závorkách a bloku příkazu.
Blok příkazu (tělo smyčky) běží, pokud je podmínka vyhodnocena jako `true` .

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="return-statement"></a>Return – příkaz

Příkaz return ukončí běh operace nebo funkce a vrátí hodnotu volajícímu.
Skládá se z klíčového slova `return` , následovaný výrazem příslušného typu a ukončující středník.

Příklad:
```qsharp
return 1;
```
nebo
```qsharp
return (results, qubits);
```

* Navrácená instance, která vrací prázdnou řazenou kolekci členů, nevyžaduje `()` příkaz return.
* Chcete-li zadat předčasné ukončení operace nebo funkce, použijte `return ();` .
Volat, které vracejí jiný typ, vyžadují konečný návratový příkaz.
* V rámci operace není maximální počet návratových příkazů.
Kompilátor může vygenerovat upozornění, pokud příkazy následují příkaz return v rámci bloku.

   
## <a name="fail-statement"></a>Příkaz selhání

Příkaz selhání ukončí běh operace a vrátí volajícímu hodnotu chyby.
Skládá se z klíčového slova `fail` následovaných řetězcem a zakončeným středníkem.
Příkaz vrátí řetězec klasického ovladače jako chybovou zprávu.

Počet příkazů selhání v rámci operace není nijak omezen.
Kompilátor může vygenerovat upozornění, pokud příkazy následují po příkazu neúspěchu v rámci bloku.

Příklad:

```qsharp
fail $"Impossible state reached";
```
nebo použití [interpolované řetězce](xref:microsoft.quantum.guide.expressions#interpolated-strings)
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a>Příklady opakování do až po úspěch

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a>RU vzor pro jednoduché qubit otočení o ose Irrational 

V typickém případu použití následující operace Q # implementuje otočení kolem osy Irrational $ (I + 2i Z)/\sqrt {5} $ v koule Bloch. Implementace používá známý vzor ru:

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a>RU smyčka se proměnlivou proměnnou v oboru

Tento příklad ukazuje použití proměnlivé proměnné, `finished` , která je v rámci rozsahu celé smyčky Repeat-to-refixup a která je inicializována před smyčkou a aktualizována v kroku opravy.

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

Tento příklad ukazuje smyčku ru bez kroku opravy. Kód je okruh pravděpodobnostní, který implementuje důležitou rotující bránu $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ pomocí `H` bran a `T` .
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

Tady je příklad ru vzoru pro přípravu stavového pole $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, počínaje ze stavu $ \ket{+} $.

Mezi významné programové funkce uvedené v této operaci patří:

* Složitější `fixup` součást smyčky, která zahrnuje operace po částech. 
* Použití `AssertMeasurementProbability` příkazů k zjištění pravděpodobnosti měření stavu v určitém počtu bodů v programu.

Další informace o [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) operacích a naleznete v tématu [testování a ladění](xref:microsoft.quantum.guide.testingdebugging).

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
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

Další informace najdete v tématu [Ukázka testování částí, která je k dispozici ve standardní knihovně](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

## <a name="next-steps"></a>Další kroky

Přečtěte si o [testování a ladění](xref:microsoft.quantum.guide.testingdebugging) v Q #.
