---
title: 'Příkazy Q #'
description: 'Přečtěte si o správném použití příkazů v Q #, včetně deklarací funkcí a operací, deklarací proměnných a přiřazení a volání operací.'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: e801a5fdd24b973f47d23d2aca6f11bbebf333d4
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904668"
---
# <a name="statements-and-other-constructs"></a>Příkazy a další konstrukce

## <a name="comments"></a>Komentáře

Komentáře začínají dvěma lomítky, `//`a pokračují až do konce řádku.
Komentář se může objevit kdekoli ve zdrojovém souboru Q #.

### <a name="documentation-comments"></a>Dokumentační komentáře

Komentáře, které začínají třemi lomítky, `///`, jsou zpracovány speciálně kompilátorem, když se objeví bezprostředně před oborem názvů, operací, specializací, funkcí nebo definicí typu.
V takovém případě je jejich obsah považován za dokumentaci pro definovaný typ s možnou podporou nebo uživatelem, jako u jiných jazyků .NET.

V rámci `///` komentáře je text, který se zobrazí jako součást dokumentace k rozhraní API, formátován jako [Markdownu](https://daringfireball.net/projects/markdown/syntax), s různými částmi dokumentace, které jsou označeny pomocí hlaviček se speciálně jmenovanými.
Jako rozšíření pro Markdownu mohou být křížové odkazy na operace, funkce a uživatelsky definované typy v Q # zahrnuty pomocí `@"<ref target>"`, kde `<ref target>` je nahrazen plně kvalifikovaným názvem odkazovaného objektu kódu.
V případě potřeby může také modul dokumentace podporovat další rozšíření Markdownu.

Příklad:

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

Následující názvy se rozpoznávají jako hlavičky komentářů k dokumentaci.

- **Summary**: stručný souhrn chování funkce nebo operace nebo účelu typu. První odstavec souhrnu se používá pro informace o přechodu myší. Měl by být prostý text.
- **Popis**: Popis chování funkce nebo operace nebo účelu typu. Souhrn a popis jsou zřetězeny, aby tvořily vygenerovaný soubor dokumentace pro funkci, operaci nebo typ.
  Popis může obsahovat symboly a rovnice ve formátu LaTeX v řádcích.
- **Input**: Popis vstupní řazené kolekce členů pro operaci nebo funkci.
  Může obsahovat další pododdíly Markdownu označující jednotlivé prvky vstupní řazené kolekce členů.
- **Výstup**: Popis řazené kolekce členů vrácený operací nebo funkcí.
- **Parametry typu**: prázdný oddíl, který obsahuje jeden další pododdíl pro každý parametr obecného typu.
- **Příklad**: krátký příklad operace, funkce nebo typu se používá.
- **Poznámky**: různé prose popisující nějaký aspekt operace, funkce nebo typu.
- **Viz také**: seznam plně kvalifikovaných názvů, které označují související funkce, operace nebo uživatelsky definované typy.
- **Odkazy**: seznam odkazů a citace pro položku, která je popsána.

## <a name="namespaces"></a>Obory názvů

Každá operace Q #, funkce a uživatelsky definovaný typ je definována v rámci oboru názvů.
Q # se řídí stejnými pravidly pro pojmenování jako jiné jazyky .NET.
Q # ale nepodporuje relativní odkazy na obory názvů.
To znamená, že pokud byl obor názvů `a.b` otevřen, odkaz na název operace `c.d` nebude přeložen na operaci s úplným názvem `a.b.c.d`.

V rámci bloku oboru názvů lze pomocí direktivy `open` importovat všechny typy a volat deklarované v určitém oboru názvů a odkazovat na ně podle jejich nekvalifikovaného názvu. Volitelně může být definován krátký název pro otevřený obor názvů tak, aby všechny elementy z tohoto oboru názvů mohly (a musí) být kvalifikovány definovaným krátkým názvem. Direktiva `open` se vztahuje na celý blok oboru názvů v rámci souboru.

Typ nebo volat, který je definován v jiném oboru názvů, který není otevřen v aktuálním oboru názvů, musí být odkazován pomocí jeho plně kvalifikovaného názvu.
Například operace s názvem `Op` v oboru názvů `X.Y` musí být odkazována pomocí plně kvalifikovaného názvu `X.Y.Op`, pokud obor názvů `X.Y` nebyl otevřen dříve v aktuálním bloku. Jak je uvedeno výše, i když byl otevřen obor názvů `X`, není možné odkazovat na operaci jako `Y.Op`.
Pokud byl v tomto oboru názvů a souboru definován krátký název `Z` pro `X.Y`, `Op` musí být odkazována jako `Z.Op`. 

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

Je obvykle lepší zahrnout obor názvů pomocí direktivy `open`.
Použití plně kvalifikovaného názvu je vyžadováno, pokud dva obory názvů definují konstrukce se stejným názvem a aktuální zdroj používá konstrukce z obou.

## <a name="formatting"></a>Formátování

Většina příkazů Q # a direktiv končí zakončeným středníkem, `;`.
Příkazy a deklarace, jako `for` a `operation`, které končí blokem příkazu, nevyžadují ukončující středník.
Každý Popis příkazu Poznamenejte, zda je nutný ukončovací středník.

Příkazy, jako jsou výrazy, deklarace a direktivy, mohou být rozděleny na více řádků.
Je třeba zabránit více příkazům na jednom řádku.

## <a name="statement-blocks"></a>Bloky příkazů

Příkazy Q # jsou seskupeny do bloků příkazů.
Blok příkazu začíná levou `{` a končí uzavíracím `}`em.

Blok příkazu, který je vložený v jiném bloku, se považuje za dílčí blok obsahujícího bloku. obsahující a dílčí bloky se označují také jako vnější a vnitřní bloky.

## <a name="symbol-binding-and-assignment"></a>Vazba symbolů a přiřazení

Q # rozlišuje proměnlivé a neproměnlivé symboly.
Obecně platí, že použití neměnných symbolů je doporučováno, protože umožňuje kompilátoru provádět větší optimalizace.

Levá strana vazby se skládá ze symbolů řazené kolekce členů a pravé strany výrazu.

Vzhledem k tomu, že všechny typy Q # jsou typy hodnot – s qubits, které pobírají trochu speciální roli, je vytvořena, když je hodnota vázána na symbol nebo když je symbol převázán. To znamená, že chování Q # je stejné jako při vytvoření kopie při přiřazení. Konkrétně to zahrnuje také pole. Samozřejmě v praxi jsou ve skutečnosti v případě potřeby znovu vytvořeny pouze relevantní součásti. 

### <a name="tuple-deconstruction"></a>Dekonstrukce řazené kolekce členů

Pokud je pravá strana vazby řazená kolekce členů, pak je možné po přiřazení dekonstruovat tuto řazenou kolekci členů.
Tato dekonstrukce může zahrnovat vnořené řazené kolekce členů a jakákoli úplná nebo částečná dekonstrukce je platná, pokud je tvar řazené kolekce členů na pravé straně kompatibilní s obrazcem řazené kolekce členů symbolů.
Dekonstrukci řazené kolekce členů se dá použít taky v případě, že je pravá strana `=` výraz vracející řazené kolekce členů.

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a>Neměnné symboly

Neměnné symboly jsou vázány pomocí příkazu `let`.
To zhruba odpovídá deklaraci proměnné a inicializaci v jazycích, jako C#například, s výjimkou toho, že po svázání se symboly Q # nedají změnit; vazby `let` jsou neměnné.

Neproměnlivá vazba se skládá z klíčového slova `let`následovaný symbolem nebo řazenou kolekcí členů symbolu, znak rovná se `=`, výrazu, na který se symboly mají svázat, a ukončující středník.
Typ vázaných symbolů je odvozený na základě výrazu na pravé straně.

### <a name="mutable-symbols"></a>Proměnlivé symboly

Proměnlivé symboly jsou definovány a inicializovány pomocí příkazu `mutable`.
Symboly deklarované a svázané jako součást příkazu `mutable` mohou být později v kódu převázány na jinou hodnotu. 

Proměnlivý výraz vazby se skládá z klíčového slova `mutable`následovaný symbolem nebo řazenou kolekcí členů symbolu, znak rovná se `=`, výrazu, na který se symboly mají svázat, a ukončující středník.
Typ vázaných symbolů je odvozený na základě výrazu na pravé straně. Pokud je symbol znovu svázán později v kódu, jeho typ se nemění a vázaná hodnota musí být kompatibilní s tímto typem.

### <a name="rebinding-of-mutable-symbols"></a>Obnovení vazby proměnlivých symbolů

Proměnlivou proměnnou lze znovu svázat pomocí příkazu `set`.
Taková revazba se skládá z klíčového slova `set`následovaný symbolem nebo řazenou kolekcí členů symbolu, znaménkem rovná se `=`, výrazu pro zpětný vazbu symbolů na a ukončující středník.
Hodnota musí být kompatibilní s typy (y) symbolů, ke kterým je vázáno.

#### <a name="apply-and-reassign-statement"></a>Příkaz Apply a Reassign

Konkrétní druh příkazu set-Statement, který označujeme jako příkaz Apply a Reassign, poskytuje pohodlný způsob zřetězení, pokud se pravá strana skládá z aplikace binárního operátoru a výsledek je převázán na levý argument operátoru. Například:
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
Podobné příkazy jsou k dispozici pro všechny binární operátory, ve kterých typ levé strany odpovídá typu výrazu. To poskytuje například pohodlný způsob, jak shromáždit hodnoty:
```qsharp
mutable results = new Result[0];
for (qubit in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a>Update-a-Reassign – příkaz

Pro výrazy kopírování a aktualizace na pravé straně existuje podobný zřetězení. Odpovídající příkazy Update-a-Reassign existují pro pojmenované položky v uživatelsky definovaných typech a také pro položky pole.  

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

V případě polí mají naše standardní knihovny k disměrnému nástroji pro řadu běžných požadavků na inicializaci a manipulaci s poli, takže se tak můžou vyhnout nutnosti aktualizovat položky pole na prvním místě. Příkazy Update a Reassign poskytují v případě potřeby alternativu:

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

> [!TIP]   
> Vyhněte se zbytečnému použití příkazů Update a Reassign pomocí nástrojů, které jsou k dispozici v <xref:microsoft.quantum.arrays>.

Funkce
```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];
    for (index in 0 .. length - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
Například je možné jednoduše zjednodušit pomocí funkce `ConstantArray` v `Microsoft.Quantum.Arrays`a vrácení výrazu Copy-and-Update:

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

### <a name="binding-scopes"></a>Rozsahy vazeb

Obecně se vazby symbolů přestanou přecházet z oboru a stanou se nefunkčními na konci příkazu, ke kterým dojde v.
Toto pravidlo obsahuje dvě výjimky:

- Vazba proměnné smyčky smyčky `for` je v rozsahu pro tělo smyčky for, ale ne za koncem smyčky.
- Všechny tři části `repeat`/`until` smyčka (tělo, test a oprava) se považují za jeden obor, takže symboly, které jsou svázané s textem, jsou k dispozici v testu a v opravě.

U obou typů smyček projde smyčka ve vlastním oboru, takže vazby z dřívějšího průchodu nejsou k dispozici v pozdější fázi.

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

## <a name="control-flow"></a>Tok řízení

### <a name="for-loop"></a>Smyčka for

Příkaz `for` podporuje iteraci v rozsahu celého čísla nebo nad polem.
Příkaz obsahuje klíčové slovo `for`, levou závorku `(`následovaný symbolem nebo řazenou kolekcí členů, klíčové slovo `in`, výraz typu `Range` nebo Array, uzavírací závorka `)`a blok příkazu.

Blok příkazu (tělo smyčky) je proveden opakovaně s definovanými symboly (proměnné smyčky) svázané s každou hodnotou v rozsahu nebo poli.
Všimněte si, že pokud je výraz Range vyhodnocen jako prázdný rozsah nebo pole, text nebude proveden vůbec.
Výraz je plně vyhodnocen před vstupem do smyčky a při provádění smyčky se nemění.

Vazba deklarovaného symbolu je neměnná a řídí se stejnými pravidly jako jiné vazby proměnných. Konkrétně je možné destrukci například položky pole pro iteraci nad polem při přiřazení k proměnným smyčky.

Například:

```qsharp
// ...
for (qubit in qubits) { // qubits contains a Qubit[]
    H(qubit);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

Proměnná smyčky je svázána s každým vchodem do těla smyčky a na konci těla není svázána.
Konkrétně proměnná smyčky není svázána po dokončení smyčky for.

### <a name="repeat-until-success-loop"></a>Opakování do smyčky po úspěšném dokončení

Příkaz `repeat` podporuje vzorek "opakovat až do úspěchu".
Skládá se z klíčového slova `repeat`následovaný blokem příkazu (tělo _smyčky_ ), klíčovým slovem `until`, logickým výrazem a buď ukončující středník, nebo klíčovým slovem `fixup` následovaným jiným blokem příkazu ( _opravou_).
Tělo smyčky, podmínka a oprava jsou považovány za jeden obor, takže symboly svázané v těle jsou k dispozici v podmínce a opravě.

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

Tělo smyčky se provede a podmínka se vyhodnotí.
Pokud je podmínka pravdivá, je příkaz dokončen; v opačném případě se oprava provede a příkaz se znovu spustí počínaje textem smyčky.
Všimněte si, že dokončení provádění opravy končí rozsahem příkazu, takže vazby symbolů provedené během těla nebo opravy nejsou k dispozici v následných opakováních.

Například následující kód je okruh pravděpodobnostní, který implementuje důležitou bránu pro otočení $V _3 = (\boldone + 2 i Z)/\sqrt{5}$ pomocí brány Hadamard a T.
V průměru končí smyčka v $ \frac{8}{5}$.
Podrobnosti najdete v tématu [*opakování až po úspěch: nedeterministické rozklady Single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick a Svore, 2014).

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

> [!TIP]   
> Nepoužívejte v rámci funkcí smyčky Repeat-do-úspěch. Odpovídající funkce jsou k dispozici v průběhu cyklů ve funkcích. 

### <a name="while-loop"></a>Smyčka while

Vzory opakování až po úspěchu mají velmi stejný zápis na základě stavu. Jsou běžně používány v určitých třídách algoritmů pro stav, a proto je konstrukce vyhrazeného jazyka v Q #. Nicméně cykly, které jsou přerušeny na základě podmínky a jejichž délka spuštění je tudíž neznámá v době kompilace, je nutné zpracovat zvláštní péčí v modulu runtime. Jejich použití v rámci funkcí na druhé straně je neproblematické, protože obsahují pouze kód, který bude spuštěn na konvenčním (nestránkovaném) hardwaru. 

Q # proto podporuje použití smyčky while pouze v rámci funkcí. Příkaz `while` se skládá z `while`klíčového slova, otevřené závorky `(`, podmínky (tj. logický výraz), uzavírací závorky `)`a bloku příkazu.
Blok příkazu (tělo smyčky) je proveden, dokud je podmínka vyhodnocena jako `true`.

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a>Podmíněný příkaz

Příkaz `if` podporuje podmíněné spuštění.
Skládá se z klíčového slova `if`, otevírací závorky `(`, logického výrazu, uzavírací závorky `)`a bloku příkazu (blok _then_ ).
Za tímto může následovat libovolný počet klauzulí else-if, každý z nich se skládá z klíčového slova `elif`, otevírací závorky `(`, logického výrazu, uzavírací závorky `)`a bloku příkazu (blok _else-if_ ).
Nakonec může být příkaz volitelně dokončen s klauzulí else, která se skládá z klíčového slova `else` následovaný jiným blokem příkazu (blok _Else_ ).
Podmínka je vyhodnocena a je-li nastavena na hodnotu true, je spuštěn blok po.
Pokud je podmínka NEPRAVDA, vyhodnotí se první podmínka else if; Pokud má hodnotu true, je spuštěn blok else-if.
V opačném případě se otestuje druhý blok else-if a třetí a tak dále, dokud není zjištěna buď klauzule s podmínkou true, nebo nejsou k dispozici další klauzule else-if.
Pokud je původní podmínka IF a všechny klauzule else-if vyhodnoceny jako NEPRAVDA, je spuštěn blok else, pokud byl poskytnut jeden.

Všimněte si, že libovolný blok je spuštěný ve svém vlastním oboru.
Vazby provedené uvnitř bloku then, else-if nebo else nejsou viditelné po konci příkazu if.

Například:

```qsharp
if (result == One) {
    X(target);
} 
```

nebo

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a>Vrátit

Příkaz return ukončí provádění operace nebo funkce a vrátí hodnotu volajícímu.
Skládá se z klíčového slova `return`následovaný výrazem příslušného typu a ukončující středník.

Nelze volat, která vrací prázdnou řazenou kolekci členů, `()`, nevyžaduje příkaz return.
Pokud je žádoucí předčasné ukončení, `return ()` možné v tomto případě použít.
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

### <a name="fail"></a>Chyba

Příkaz selhání ukončí provádění operace a vrátí volajícímu hodnotu chyby.
Skládá se z klíčového slova `fail`následovaný řetězcem a zakončeným středníkem.
Řetězec se vrátí do ovladače klasického rozhraní jako chybová zpráva.

Počet příkazů selhání v rámci operace není nijak omezen.
Kompilátor může vygenerovat upozornění, pokud příkazy následují po příkazu neúspěchu v rámci bloku.

Například:

```qsharp
fail $"Impossible state reached";
```

nebo

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a>Správa qubit

Všimněte si, že žádný z těchto příkazů není povolen v rámci těla funkce.
Jsou platné pouze v rámci operací.

### <a name="clean-qubits"></a>Vyčistit Qubits

Příkaz `using` slouží k získání nového qubits pro použití během bloku příkazu.
Qubits je zaručeno, že budou inicializovány do výpočetního `Zero`ho stavu.
Qubits by měl být ve stavu výpočtu `Zero` na konci bloku příkazu; simulátory se doporučuje vyhovět.

Příkaz se skládá z klíčového slova `using`následovaný levou kulatou závorkou `(`, vazbou, uzavírací závorkou `)`a blok příkazů, ve kterém bude qubits k dispozici.
Vazba se řídí stejným vzorem jako `let` příkazy: buď jeden symbol, nebo záznamovou sadu symbolů, následovaný znaménkem rovná se `=`a buď jednou hodnotou, nebo porovnáním řazené kolekce členů inicializátorů.
Inicializátory jsou k dispozici buď pro jeden qubit, který je označen jako `Qubit()`, nebo pole qubits, označeno `Qubit[`, výraz `Int` a `]`.

Například:

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="borrowed-qubits"></a>Vypůjčený Qubits

Příkaz `borrowing` slouží k získání qubits pro dočasné použití. Příkaz se skládá z klíčového slova `borrowing`následovaný levou kulatou závorkou `(`, vazbou, uzavírací závorkou `)`a blok příkazů, ve kterém bude qubits k dispozici.
Vazba následuje stejný vzor a pravidla jako ta v příkazu `using`.

Například:

```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

Vypůjčený qubits je v neznámém stavu a na konci bloku příkazu se překročí rozsah.
Dlužník se zavazuje, že opustí qubits ve stejném stavu, ve kterém byly ve chvíli, kdy byly vypůjčené, tj. jejich stav na začátku a na konci bloku příkazu by měl být stejný.
Konkrétně se nejedná o klasický stav, což znamená, že ve většině případů by výpůjční rozsahy neměly obsahovat měření. 

Příklad vypůjčeného Roettelerho použití najdete v tématu věnovaném [*faktorování pomocí 2n + 2 qubits s Toffoli modulárním násobení*](https://arxiv.org/abs/1611.07995) (Haner, Svore a qubit 2017).

Při výpůjční qubits se systém nejprve pokusí vyplňovat požadavek z qubits, které se používají, ale nejsou k dispozici během těla `borrowing`ho příkazu.
Pokud není dostatečná taková qubits, přidělí se nové qubits, aby se žádost dokončila.

## <a name="conjugations"></a>Conjugations

Na rozdíl od klasických bitů, uvolňování paměti je trochu více zapojeno, protože nevidomé resetující qubits může mít nežádoucí důsledky zbývajícího výpočtu, pokud qubits stále entangled. K tomu je možné se vyhnout tím, že před uvolněním paměti vykonává správné "rušení". Běžným vzorem pro výpočetní výkon je následující: 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

: NOVINKA: od naší verze 0,9 podporujeme příkaz conjugation, který implementuje výše uvedenou transformaci. Pomocí tohoto příkazu lze operaci `ApplyWith` implementovat následujícím způsobem:

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
Takový příkaz conjugation zjevně je mnohem užitečnější, pokud vnější a vnitřní transformace nejsou snadno dostupné jako operace, ale místo toho jsou vhodnější pro popis pomocí bloku skládajícího se z několika příkazů. 

Inverzní transformace pro příkazy definované v rámci bloku je automaticky generována kompilátorem a provedena po dokončení bloku Apply. Vzhledem k tomu, že jakékoli proměnlivé proměnné použité jako součást bloku nelze znovu svázat v bloku Apply, je vygenerovaná transformace zaručena jako sousední v výpočtu v bloku. 

## <a name="expression-evaluation-statements"></a>Příkazy vyhodnocení výrazu

Jako příkaz lze použít jakýkoli výraz volání typu `Unit`.
To je primárně použito při volání operací na qubits, které vracejí `Unit` vzhledem k tomu, že účelem příkazu je upravit implicitní stav.
Příkazy vyhodnocení výrazu vyžadují ukončující středník.

Například:

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
