---
title: 'Proměnné v Q #'
description: Popis výplně
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 407b4ff3570816eb7bdc323a5c5b77dac2d951af
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430896"
---
# <a name="variables-in-q"></a>Proměnné v Q #

Q # rozlišuje proměnlivé a neproměnlivé symboly nebo "proměnné", které jsou vázány nebo přiřazeny výrazům.
Obecně platí, že použití neměnných symbolů je doporučováno, protože umožňuje kompilátoru provádět větší optimalizace.

Levá strana vazby se skládá ze symbolů řazené kolekce členů a pravé strany výrazu.

## <a name="immutable-variables"></a>Neměnné proměnné

Hodnotu jakéhokoli typu v Q # lze přiřadit proměnné pro opětovné použití v rámci operace nebo funkce pomocí `let` klíčového slova.

Neproměnlivá vazba se skládá z klíčového slova `let` následovaný symbolem nebo řazenou kolekcí členů symbolu, znaménko rovná `=` se, výraz pro vazbu symbolů na a ukončující středník.

Například:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

To přiřadí konkrétní pole operátorů Pauli k názvu proměnné (neboli symbol), `measurementOperator` .

> [!NOTE]
> Nemuseli explicitně zadat typ naší nové proměnné, protože výraz na pravé straně `let` příkazu je nejednoznačný a daný typ je odvozený kompilátorem. 

Proměnné definované pomocí `let` jsou *neměnné*, což znamená, že po jejím definování již není možné je nijak měnit.
To umožňuje několik užitečných optimalizací, včetně optimalizace klasické logiky, která působí na proměnné, aby se mohla použít `Adjoint` varianta operace.

## <a name="mutable-variables"></a>Proměnlivé proměnné

Jako alternativu k vytvoření proměnné pomocí `let` `mutable` klíčového slova vytvoří proměnlivou proměnnou, která *může* být po počátečním vytvoření pomocí `set` klíčového slova znovu svázána.

Symboly deklarované a svázané jako součást `mutable` příkazu mohou být později v kódu převázány na jinou hodnotu. Pokud je symbol převázán později v kódu, jeho typ se nezmění a nově vázané hodnoty musí být kompatibilní s tímto typem.

### <a name="rebinding-of-mutable-symbols"></a>Obnovení vazby proměnlivých symbolů

Proměnlivou proměnnou lze znovu svázat pomocí `set` příkazu.
Taková revazba se skládá z klíčového slova `set` následovaný symbolem nebo řazenou kolekcí členů symbolů, znaménkem rovnosti `=` , výrazu pro opětovné svázání symbolů a zakončeným středníkem.

Tady poskytujeme některé možné příklady technik revázání příkazů.

### <a name="apply-and-reassign-statements"></a>Příkazy Apply a Reassign

Konkrétní druh `set` příkazu, který označujeme jako příkaz *Apply a Reassign* , poskytuje pohodlný způsob zřetězení, pokud se pravá strana skládá z aplikace binárního operátoru a výsledek je převázán na levý argument operátoru. Například:
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
zvýší hodnotu čítače `counter` v každé iteraci `for` smyčky. Výše uvedený kód je stejný jako 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

Podobné příkazy jsou k dispozici pro všechny binární operátory, ve kterých typ levé strany odpovídá typu výrazu. To poskytuje například pohodlný způsob, jak nashromáždit hodnoty.

Například Supposing `qubits` je regsiter of qubits:
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

### <a name="update-and-reassign-statements"></a>Příkazy Update a Reassign

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

V případě polí jsou [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) v naší standardní knihovně k dispozici potřebné nástroje pro řadu běžných požadavků na inicializaci a manipulaci s poli, takže se tak můžou vyhnout nutnosti aktualizovat položky pole na prvním místě. 

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

Pomocí nástrojů knihovny pro pole, která jsou k dispozici v systému [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) , můžeme například snadno definovat funkci, která vrací pole Paul, kde Pauli on index `i` přebírá danou hodnotu a všechny ostatní položky jsou identity.

Tady jsou dvě definice této funkce s druhým využitím výhod těchto nástrojů.

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli or PauliI dep. on whether index==location
    }    
    return pauliArray;
}
```

Místo procházení každého indexu v poli a podmíněně jeho nastavování na `PauliI` nebo `Pauli` můžete místo toho použít `ConstantArray` z [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) k vytvoření pole `PauliI` a pak jednoduše vracet výraz kopie a aktualizace, ve kterém jsme změnili hodnotu specifc na indexu `location` :

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a>Dekonstrukce řazené kolekce členů

Kromě přiřazování jedné proměnné, `let` `mutable` klíčová slova a---nebo ve skutečnosti jakékoliv jiné konstrukce vazby, například `set` (popsané níže)---také umožňují rozbalení obsahu [typu řazené kolekce členů](xref:microsoft.quantum.guide.types#tuple-types).
Přiřazení tohoto formuláře se říká k *dekonstrukci* prvků této řazené kolekce členů.

Pokud je pravá strana vazby řazená kolekce členů, pak je možné po přiřazení dekonstruovat tuto řazenou kolekci členů.
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
- Všechny tři části `repeat` / `until` smyčky (tělo, test a oprava) se považují za jediný obor, takže symboly, které jsou svázané s textem, jsou k dispozici v testu a v opravě.

U obou typů smyček projde smyčka ve vlastním oboru, takže vazby z dřívějšího průchodu nejsou k dispozici v pozdější fázi.
Podrobnosti o těchto smyčkách najdete v [toku řízení](xref:microsoft.quantum.guide.controlflow).

Vazby symbolů z vnějších bloků jsou děděny pomocí vnitřních bloků.
Symbol může být vázaný jenom jednou na blok; není povoleno definovat symbol se stejným názvem jako jiný symbol, který je v oboru (bez "stínování").
Následující sekvence by byly platné:

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

## <a name="whats-next"></a>A co dál?
Přečtěte si o [práci s Qubits](xref:microsoft.quantum.guide.qubits) v Q #.