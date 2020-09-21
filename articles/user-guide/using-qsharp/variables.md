---
title: Proměnné v Q#
description: Naučte se pracovat s různými proměnnými v Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
no-loc:
- Q#
- $$v
ms.openlocfilehash: bb87f36d3c9b7df195f64e85151e833d494ea945
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835872"
---
# <a name="variables-in-no-locq"></a>Proměnné v Q#

Q# rozlišuje mezi proměnlivými a neproměnlivými symboly nebo *proměnnými*, které jsou vázány nebo přiřazeny k výrazům.
Obecně platí, že použití neměnných symbolů je doporučováno, protože umožňuje kompilátoru provádět větší optimalizace.

Levá strana vazby se skládá ze symbolů typu tuple a na pravé straně výrazu.

## <a name="immutable-variables"></a>Neměnné proměnné

Můžete přiřadit hodnotu libovolného typu v Q# proměnné pro opětovné použití v rámci operace nebo funkce pomocí `let` klíčového slova. 

Neproměnlivá vazba se skládá z klíčového slova `let` následovaný symbolem nebo řazenou kolekcí členů symbolu, znaménko rovná `=` se, výraz pro vazbu symbolů na a ukončující středník.

Například:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

To přiřadí konkrétní pole operátorů Pauli k názvu proměnné (neboli symbol), `measurementOperator` .

> [!NOTE]
> V předchozím příkladu není nutné explicitně zadat typ nové proměnné, protože výraz na pravé straně `let` příkazu je nejednoznačný a kompilátor odvodí správný typ. 

Proměnné definované pomocí `let` jsou *neměnné*, což znamená, že po jejím definování už je nebudete moct změnit jakýmkoli způsobem.
To umožňuje několik užitečných optimalizací, včetně optimalizace klasické logiky, která funguje u proměnných, aby se mohla použít `Adjoint` varianta operace.

## <a name="mutable-variables"></a>Proměnlivé proměnné

Jako alternativu k vytváření proměnných pomocí `let` `mutable` klíčového slova vytvoří proměnlivou proměnnou, která *může* být po jeho počátečním vytvoření znovu svázána pomocí `set` klíčového slova.

Můžete znovu svázat symboly deklarované a svázané jako součást `mutable` příkazu s jinou hodnotou později v kódu. Pokud je symbol znovu svázán později v kódu, jeho typ se nemění a nově vázané hodnoty musí být kompatibilní s tímto typem.

### <a name="rebinding-of-mutable-symbols"></a>Obnovení vazby proměnlivých symbolů

Můžete znovu navazovat proměnlivou proměnnou pomocí `set` příkazu.
Taková revazba se skládá z klíčového slova `set` následovaný symbolem nebo řazenou kolekcí členů symbolů, znaménkem rovnosti `=` , výrazu pro opětovné svázání symbolů a zakončeným středníkem.

Níže jsou uvedeny některé příklady technik příkazu resvázat.

#### <a name="apply-and-reassign-statements"></a>Příkazy Apply a Reassign

Konkrétní druh `set` příkazu, příkaz *Apply a Reassign* , poskytuje pohodlný způsob zřetězení, pokud se pravá strana skládá z aplikace binárního operátoru a výsledek je převázán na levý argument operátoru. Příklad:

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
zvýší hodnotu čítače `counter` v každé iteraci `for` smyčky. Předchozí kód je ekvivalentní 

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

Podobné příkazy jsou k dispozici pro všechny binární operátory, ve kterých typ levé strany odpovídá typu výrazu. Tyto příkazy poskytují pohodlný způsob, jak nashromáždit hodnoty.

Například Supposing `qubits` je registr qubits:
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

#### <a name="update-and-reassign-statements"></a>Příkazy Update a Reassign

Pro [výrazy kopírování a aktualizace](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) na pravé straně existuje podobný zřetězení.
Odpovídající příkazy *Update-a-Reassign* existují pro *pojmenované položky* v uživatelsky definovaných typech a také pro *položky pole*.  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

V případě polí je [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) ve Q# standardní knihovně k dispozici nezbytné nástroje pro řadu běžných požadavků na inicializaci a manipulaci s poli, a proto pomáhá vyhnout se nutnosti aktualizovat položky pole na prvním místě. 

Příkazy Update a Reassign poskytují v případě potřeby alternativu:

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

Pomocí nástrojů knihovny pro pole, která jsou k dispozici v [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) , můžete například snadno definovat funkci, která vrací pole typů, `Pauli` kde element v indexu `i` přebírá danou `Pauli` hodnotu a všechny ostatní položky jsou identity ( `PauliI` ).

Tady jsou dvě definice této funkce s druhým využitím výhod těchto nástrojů.

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli if index==location and PauliI if not
    }    
    return pauliArray;
}
```

Místo toho, aby se při každém indexu v poli převzala iterace, a podmíněně ho nastaví na `PauliI` nebo daný `pauli` typ, můžete místo toho použít `ConstantArray` z [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) k vytvoření pole `PauliI` typů a pak jednoduše vrátit výraz kopírování a aktualizace, ve kterém jste změnili konkrétní hodnotu na indexu `location` :

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a>Dekonstrukce řazené kolekce členů

Kromě přiřazování jedné proměnné můžete použít `let` `mutable` klíčová slova a a jakékoli jiné konstrukce vazby, například `set` -k rozbalení obsahu [typu řazené kolekce členů](xref:microsoft.quantum.guide.types#tuple-types).
Přiřazení tohoto formuláře se říká k *dekonstrukci* prvků této řazené kolekce členů.

Pokud je pravá strana vazby řazená kolekce členů, můžete tuto řazenou kolekci členů dekonstruovat po přiřazení.
Tato dekonstrukce může zahrnovat vnořené řazené kolekce členů a jakákoli úplná nebo částečná dekonstrukce je platná, pokud je tvar řazené kolekce členů na pravé straně kompatibilní s obrazcem řazené kolekce členů symbolů.

Příklad:

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a>Rozsahy vazeb

Obecně se vazby symbolů přestanou přecházet z oboru a stanou se nefunkčními na konci příkazu, ke kterým dojde v.
Toto pravidlo obsahuje dvě výjimky:

- Vazba proměnné smyčky `for` smyčky je v rozsahu pro tělo smyčky for, ale ne za koncem smyčky.
- Všechny tři části `repeat` / `until` smyčky (tělo, test a oprava) fungují jako jeden obor, takže symboly, které jsou svázané s textem, jsou k dispozici v testu a opravě.

U obou typů smyček každý průchod cyklem spouští ve svém vlastním oboru, takže vazby z dřívějšího průchodu nejsou k dispozici v pozdější fázi.
Další informace o těchto smyčkách najdete v tématu [tok řízení](xref:microsoft.quantum.guide.controlflow).

Vnitřní bloky dědí vazby symbolů z vnějších bloků.
Pro každý blok můžete vytvořit pouze jeden symbol; není povoleno definovat symbol se stejným názvem jako jiný symbol, který je v oboru (bez "stínování").
Platné jsou následující sekvence:

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

a

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
...                 // n is not bound to a value
```

Ale to by bylo neplatné:

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

Jak by to bylo:

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="next-steps"></a>Další kroky

Přečtěte si o [práci s Qubits](xref:microsoft.quantum.guide.qubits) v Q# .