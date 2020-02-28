---
title: 'Další s technikami Q #'
description: 'Prozkoumejte Pokročilá témata v Q #, například vytváření obecných funkcí a výpůjčky qubits.'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.going-further
ms.openlocfilehash: 46ebf544c1d6e56f152a06d06151305fa972011a
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906895"
---
# <a name="going-further"></a>Dál #

Teď, když jste se seznámili s tím, jak psát zajímavé programy v Q #, se tato část doplní o několik pokročilých témat, která by se měla ukázat jako užitečná.


## <a name="generic-operations-and-functions"></a>Obecné operace a funkce ##

> [!TIP]
> V této části se předpokládá některá základní znalost [obecného prostředí v C# ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), [obecných typech F# ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [ C++ šablonách](https://docs.microsoft.com/cpp/cpp/templates-cpp)nebo podobných přístupů k metaprogramování šablonou v jiných jazycích.

Mnoho funkcí a operací, které můžeme chtít definovat, se ve skutečnosti nespoléhá na typy jejich vstupů, ale místo toho pouze implicitně používají jejich typy prostřednictvím jiné funkce nebo operace.
Představte si třeba koncept *mapy* společný pro mnoho funkčních jazyků. po předané funkci $f (x) $ a kolekci hodnot $\{x_1, x_2, \dots, x_n\}$, map vrátí novou kolekci $\{f (x_1), f (x_2), \dots, f (x_n)\}$.
K implementaci tohoto v Q # můžeme využít výhod těchto funkcí jako první třídy.
Pojďme si napsat rychlý příklad `Map`, při použití ★ jako zástupného symbolu, přičemž zjistíme, jaké typy potřebujeme.

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Všimněte si, že tato funkce vypadá velmi stejně bez ohledu na to, jaké vlastní typy nahrazujíme.
Mapa z celých čísel na Paul, například vypadá podobně jako mapa z čísel s plovoucí desetinnou čárkou na řetězce:

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

V podstatě jsme mohli napsat verzi `Map` pro každou dvojici typů, ke kterým dochází, ale to přináší řadu potíží.
Pokud například v `Map`zjistíte chybu, je nutné zajistit, aby se oprava používala jednotně napříč všemi verzemi `Map`.
Kromě toho, Pokud vytvoříme nové řazené kolekce členů nebo UDT, je teď také potřeba vytvořit nový `Map` k tomu, aby bylo možné přejít i k novému typu.
I když je to pro malý počet takových funkcí rušivý, protože shromažďujeme více a více funkcí stejné formy jako `Map`, náklady na zavedení nových typů se v poměrně krátkém pořadí stávají nepřiměřeně veliké.

Mnohé z těchto potíží se ale nedostaly do tohoto kompilátoru informace, které potřebuje k tomu, abyste zjistili, jak různé verze `Map` souvisejí.
Chceme, aby kompilátor považoval `Map` jako nějaký druh matematické funkce od Q *# do funkcí q #.*
Tento pojem je formální tím, že povoluje funkce a operace pro *parametry typu*a také jejich běžné parametry řazené kolekce členů.
V předchozích příkladech si chceme představit `Map` jako parametry typu `Int, Pauli` v prvním případě a `Double, String` ve druhém případě.
Ve většině případů lze tyto parametry typu použít, jako by se jednalo o běžné typy: používáme hodnoty parametrů typu k vytváření polí a řazených kolekcí členů, volání funkcí a operací a přiřazení k běžným nebo proměnlivým proměnným.

> [!NOTE]
> Největší případ nepřímých závislostí je, že qubits, kde se program Q # nemůže přímo spoléhat na strukturu `Qubit`ho typu, ale **musí** předat takové typy jiným operacím a funkcím.

Po návratu do výše uvedeného příkladu vidíte, že potřebujeme `Map`, aby bylo možné zadat parametry typu, jeden pro reprezentaci vstupu `fn` a druhý, který představuje výstup z `fn`.
V Q # se to zapisuje přidáním lomených závorek (to `<>`, nikoli brakets $ \braket{}$!) za názvem funkce nebo operace v deklaraci a výpisem každého parametru typu.
Název každého parametru typu musí začínat `'`em Tick, což značí, že se jedná o parametr typu, a ne běžný typ (označovaný také jako *konkrétní* typ).
Pro `Map`zapisujeme:

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Všimněte si, že definice `Map<'Input, 'Output>` vypadá extrémně podobně jako verze, které jsme předtím napsali.
Jediným rozdílem je, že explicitně informovali kompilátor, že `Map` přímo nezávisí na tom, co `'Input` a `'Output` jsou, ale funguje pro všechny dva typy pomocí nepřímo prostřednictvím `fn`.
Po definování `Map<'Input, 'Output>` tímto způsobem můžeme zavolat, jako by šlo o běžnou funkci:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> Zápis obecných funkcí a operací je jedním z míst, kde "řazená kolekce členů" v řazené kolekci členů "je velmi užitečným způsobem, jak se zamyslet na funkce a operace Q #.
> Vzhledem k tomu, že každá funkce přebírá přesně jeden vstup a vrátí přesně jeden výstup, vstup typu `'T -> 'U` odpovídá *libovolné* funkci Q #.
> Podobně lze každou operaci předat do vstupu typu `'T => 'U`.

V druhém příkladu zvažte, jak napsat funkci, která vrací kompozici dvou dalších funkcí:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

V tomto případě je nutné přesně zadat, co `A`, `B`a `C` jsou, proto vážně omezují nástroj naší nové `Compose` funkce.
Po všech `Compose` závisí jenom na `A`, `B`a `C` *prostřednictvím* `innerFn` a `outerFn`.
Alternativně můžeme přidat parametry typu do `Compose`, které naznačují, že funguje pro *všechny* `A`, `B`a `C`, pokud tyto parametry odpovídají následujícím parametrům, které očekává `innerFn` a `outerFn`:

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Standardní knihovny Q # poskytují rozsah takových operací, které jsou parametrizované pro typ, a usnadňují tak vyjádření toku řízení vyšším řádu.
Tyto postupy jsou podrobněji popsány v [příručce ke standardní knihovně Q #](xref:microsoft.quantum.libraries.standard.intro).

## <a name="borrowing-qubits"></a>Výpůjčka Qubits ##

Výpůjční mechanizmus umožňuje přidělení qubits, které lze použít jako pomocné místo během výpočtu. Tyto qubits nejsou obecně v čistém stavu, tj., nejsou nutně inicializovány ve známém stavu, například $ \ket{0}$. Jedna z nich také mluví "nequbitscí", protože jejich stav je neznámý a může být dokonce entangled s ostatními částmi paměti počítače. Mezi známé případy použití undirty qubits jsou implementace více řízených CNOTch bran, které vyžadují jenom velmi málo qubits a implementaci přírůstku.

V Canon existují příklady, které používají klíčové slovo `borrowing`, například funkce `MultiControlledXBorrow` definována níže.
Pokud `controls` označuje qubits ovládacího prvku, který má být přidán do operace `X`, bude tato implementace obsahovat celkový `Length(controls)-2` mnoho nezměněných ancillas.

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

Všimněte si, že rozsáhlé použití `With` kombinátorem---ve formuláři, které platí pro operace, které podporují sousední, tj. `WithA`---byly provedeny v tomto příkladu, což je dobrý programovací styl jako přidání ovládacího prvku do struktur zahrnující `With` pouze rozšíření ovládacího prvku do vnitřní operace. Dále si všimněte, že kromě `body` operace byla explicitně poskytnuta implementace `controlled` těla operace, nikoli použití příkazu `controlled auto`. Důvodem je to, že ví od struktury okruhu, jak snadno přidat další ovládací prvky, které jsou ve srovnání s přidáním ovládacího prvku do každé a každé samostatné brány v `body`vhodné. 

Tento kód se dá porovnávat s jinou funkcí Canon `MultiControlledXClean`, která dosahuje stejného cíle implementace `X` operace řízené vynásobením, ale používá několik čistých qubits pomocí mechanismu `using`. 
