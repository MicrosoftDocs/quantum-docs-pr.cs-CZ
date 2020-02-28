---
title: 'Výrazy Q #'
description: 'Pochopte, jak zadat, odkazovat a kombinovat konstanty, proměnné, operátory, operace a funkce jako výrazy v Q #.'
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: fbde873f220d737db17f889d00be33541e3eb59b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907405"
---
# <a name="expressions"></a>Výrazy

## <a name="grouping"></a>Seskupování

V případě libovolného výrazu je stejný výraz uzavřený v závorkách výraz stejného typu.
`(7)` je například výraz `Int`, `([1,2,3])` je výraz typu `Int`s a `((1,2))` je výraz typu `(Int, Int)`.

Ekvivalenci mezi jednoduchými hodnotami a řazenými kolekcemi členů s jedním prvkem popsanými v [modelu typu](xref:microsoft.quantum.language.type-model#tuple-types) odebere nejednoznačnost mezi `(6)` jako skupinu a `(6)` jako řazenou kolekci členů s jedním prvkem.

## <a name="symbols"></a>Symboly

Název vázaného symbolu nebo přiřazený k hodnotě typu `'T` je výraz typu `'T`.
Například pokud je symbol `count` svázán s celočíselnou hodnotou `5`, pak `count` je celočíselný výraz.

## <a name="numeric-expressions"></a>Číselné výrazy

Číselné výrazy jsou výrazy typu `Int`, `BigInt`nebo `Double`.
To znamená, že jsou buď celá čísla, nebo čísla s plovoucí desetinnou čárkou.

literály `Int` v Q # jsou identické s celočíselnými literály v C#, s tím rozdílem, že nejsou vyžadovány žádné koncové čárky "l" nebo "l" (nebo povoleny).
V uvedeném pořadí jsou podporována šestnáctková a binární celá čísla s předponou 0x a 0b.

literály `BigInt` v Q # jsou identické s velkými celočíselnými řetězci v .NET s koncovým řetězcem "l" nebo "L".
Předpona "0x" je podporována hexadecimálními velkými čísly.
Následující jsou tedy všechna platná použití `BigInt` literály:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

literály `Double` v Q # jsou identické s dvojitými literály v C#, s tím rozdílem, že nejsou vyžadovány žádné koncové znaky "d" nebo "d" (nebo povoleny).

Vzhledem k výrazu pole libovolného typu elementu může být výraz `Int` vytvořen pomocí předdefinované funkce `Length` a výraz pole uzavřený v závorkách, `(` a `)`.
Například pokud je `a` svázána s polem, `Length(a)` je celočíselný výraz.
Je-li `b` pole celých čísel, `Int[][]`a `Length(b)` je počet dílčích polí v `b`a `Length(b[1])` je počet celých čísel ve druhém dílčím poli v `b`.

Pro vytvoření nového číselného výrazu lze použít binární operátory `+`, `-`, `*`a `/`, které jsou zadány dvěma číselnými výrazy stejného typu.
Typ nového výrazu bude stejný jako u typů výrazů prvků.

Zadaným dvěma celočíselnými výrazy, binární operátor `^` (napájení) lze použít k vytvoření nového celočíselného výrazu.
Podobně `^` lze použít se dvěma dvojitými výrazy k vytvoření nového dvojitého výrazu.
Nakonec `^` možné použít s velkým celým číslem na levé straně a celé číslo na pravé straně k vytvoření nového výrazu Big Integer.
V takovém případě se druhý parametr musí vejít do 32 bitů; v takovém případě se vyvolá Běhová chyba.

Předané dva celočíselné nebo velké celočíselné výrazy mohou být tvořeny výrazem `%` (modulo), `&&&` (bitových a), `|||` (bitových nebo) nebo `^^^` (bitových operátorů XOR).

Pro vytvoření nového výrazu stejného typu, jako je výraz na levé straně, je možné použít buď celočíselný nebo velký výraz celého čísla na levé straně, a výraz typu Integer na pravé straně, operátor `<<<` (aritmetický posun doleva) nebo `>>>` (aritmetický posun).

Druhý parametr (velikost posunu) pro operaci posunu musí být větší nebo roven nule. chování pro záporné hodnoty posunutí není definováno.
Velikost SHIFT pro buď operaci posunutí musí být také do 32 bitů. v takovém případě se vyvolá Běhová chyba.
Pokud číslo, které má být posunuto, je celé číslo, hodnota posunutí je interpretována `mod 64`; To znamená, že posun 1 a Shift 65 mají stejný účinek.

Pro celočíselné i velké celočíselné hodnoty jsou posunuty aritmetické operace.
Posunutí záporné hodnoty doleva nebo doprava bude mít za následek záporné číslo.
To znamená, že posun jednoho kroku doleva nebo doprava je přesně stejný jako násobení nebo dělení 2, v uvedeném pořadí.

Celočíselné dělení a celočíselné zbytky se řídí stejným chováním jako C#záporná čísla.
To znamená, že `a % b` vždycky budou stejné znaménko jako `a`a `b * (a / b) + a % b` se vždycky rovná `a`.
Příklad:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

Dělení velkých celých čísel a Modulus funguje stejným způsobem.

V případě libovolného číselného výrazu může být nový výraz vytvořen pomocí operátoru `-` unární.
Nový výraz bude stejného typu jako výraz prvku.

S ohledem na libovolný celočíselný nebo velký celočíselný výraz může být nový výraz stejného typu vytvořen pomocí unárního operátoru `~~~` (bitový doplněk).

## <a name="boolean-expressions"></a>Výrazy logických hodnot

Dvě `Bool` hodnoty literálu jsou `true` a `false`.

Vzhledem k jakýmkoli dvěma výrazům stejného primitivního typu lze použít binární operátory `==` a `!=` k vytvoření výrazu `Bool`.
Výraz bude true, pokud jsou dva výrazy stejné, a false, pokud ne.

Hodnoty uživatelsky definovaných typů nelze porovnat, lze porovnat pouze jejich nezabalené hodnoty. Například použití operátoru "Unwrap" `!` (vysvětleno na [stránce modelu typu Q #](xref:microsoft.quantum.language.type-model#user-defined-types)),

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

Porovnání rovnosti pro hodnoty `Qubit` je rovnost identity; To znamená, zda dva výrazy identifikují stejný qubit.
Stav obou qubits se neshoduje, nepoužívá se, neměří ani nemění pomocí tohoto porovnání.

Porovnání rovnosti pro hodnoty `Double` může být zavádějící z důvodu zaoblení efektů.
`49.0 * (1.0/49.0) != 1.0`například.

Vzhledem k tomu, že jsou zadány dva číselné výrazy, binární operátory `>`, `<`, `>=`a `<=` lze použít k vytvoření nového logického výrazu, který má hodnotu true, pokud je první výraz v tomto pořadí větší než, menší než, větší nebo roven nebo menší nebo roven druhému výrazu.

V případě jakýchkoli dvou logických výrazů lze použít binární operátory `and` a `or` k vytvoření nového logického výrazu, který má hodnotu true, pokud jsou oba výrazy (odp. buď nebo oba) pravdivé.

S ohledem na jakýkoliv logický výraz lze použít unární operátor `not` k vytvoření nového logického výrazu, který je true, pokud je výraz prvku false.

## <a name="string-expressions"></a>Řetězcové výrazy

Q # povoluje použití řetězců v příkazu `fail` a ve funkci `Log` Standard.

Řetězce v Q # jsou buď literály nebo interpolované řetězce.
Řetězcové literály jsou podobně jako jednoduché řetězcové literály ve většině jazyků: sekvence znaků Unicode uzavřená v dvojitých uvozovkách, `"`.
Uvnitř řetězce je možné znak zpětného lomítka `\` použít k úniku znaku dvojité uvozovky a vložení nového řádku jako `\n`, návratu na začátek jako `\r`a kartu jako `\t`.
Příklad:

```qsharp
"\"Hello world!\", she said.\n"
```

Syntaxe Q # pro interpolování řetězců je podmnožinou syntaxe C# 7,0; Q # nepodporuje doslovné (Multi-line) interpolované řetězce.
Viz [*interpolované řetězce*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) pro C# syntaxi.

Výrazy uvnitř interpolované řetězce následují syntaxe Q #, nikoli C# syntaxe.
Libovolný platný výraz Q # se může objevit v interpolované řetězci.

## <a name="qubit-expressions"></a>Výrazy qubit

Jedinými `Qubit` výrazy jsou symboly, které jsou vázány na `Qubit` hodnoty nebo prvky pole `Qubit` polí.
Neexistují žádné `Qubit` literály.

## <a name="pauli-expressions"></a>Výrazy Pauli

Čtyři `Pauli` hodnoty, `PauliI`, `PauliX`, `PauliY`a `PauliZ`, jsou všechny platné výrazy `Pauli`.

Kromě toho jediné `Pauli` výrazy jsou symboly, které jsou vázány na `Pauli` hodnoty nebo prvky pole `Pauli` polí.

## <a name="result-expressions"></a>Výsledné výrazy

Dvě `Result` hodnoty, `One` a `Zero`, jsou platné `Result` výrazy.

Kromě toho jediné `Result` výrazy jsou symboly, které jsou vázány na `Result` hodnoty nebo prvky pole `Result` polí.
Konkrétně Všimněte si, že `One` není stejná jako celé číslo `1`a mezi nimi není přímý převod.
Totéž platí pro `Zero` a `0`.

## <a name="range-expressions"></a>Výrazy rozsahu

Pro všechny tři `Int` výrazy `start`, `step`a `stop`je `start .. step .. stop` výraz rozsahu, jehož prvním prvkem je `start`, druhý prvek je `start+step`, třetí prvek je `start+step+step`atd., dokud nebude předán `stop`.
Rozsah může být prázdný, pokud je například `step` kladný a `stop < start`.
Poslední prvek rozsahu bude `stop`, pokud rozdíl mezi `start` a `stop` je integrální násobek `step`; To znamená, že rozsah je zahrnut na obou koncích.

Pro všechny dva `Int` výrazy `start` a `stop`je `start .. stop` výraz rozsahu, který se rovná `start .. 1 .. stop`.
Všimněte si, že implicitní `step` je + 1, i když `stop` je menší než `start`; v takovém případě je rozsah prázdný.

Mezi příklady oblastí patří:

- `1..3` je rozsah 1, 2, 3.
- `2..2..5` je rozsah 2, 4.
- `2..2..6` je rozsah 2, 4, 6.
- `6..-2..2` je rozsah 6, 4, 2.
- `2..1` je prázdný rozsah.
- `2..6..7` je rozsah 2.
- `2..2..1` je prázdný rozsah.
- `1..-1..2` je prázdný rozsah.

## <a name="callable-expressions"></a>Výrazy, které se mají volat

Volatelné literály je název operace nebo funkce definované v oboru kompilace.
Například `X` je literál operace, který odkazuje na standardní knihovnu `X` operace a `Message` je literál funkce, který odkazuje na `Message` funkci standardní knihovny.

Pokud operace podporuje `Adjoint` funktor, `Adjoint op` je výraz operace.
Podobně pokud operace podporuje `Controlled` funktor, `Controlled op` je výraz operace.
Typy těchto výrazů jsou zadány v [funktory](xref:microsoft.quantum.language.type-model#functors).

Funktory (`Adjoint` a `Controlled`) sváže více než všechny ostatní operátory, s výjimkou operátoru Unwrap `!` a pole Indexing `[]`.
Níže jsou uvedené všechny právní a za předpokladu, že operace podporují funktory, který se používá:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

Dá se použít jako hodnota, která se dá použít jako hodnota, řekněme, že se přiřadí proměnné nebo přejdou na jinou možnou volat.
V tomto případě musí být v případě, že je možné volat parametry typu, zadány jako součást hodnoty, kterou lze volat.
Hodnota, která se nedá volat, nemůže mít nespecifikované parametry typu.

Pokud `Fun` například funkce s podpisovým `'T1->Unit`:

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Volat výrazy vyvolání

Vzhledem k volání (operace nebo funkce) a výrazu řazené kolekce členů na vstupním typu signatury, která se dá volat, může být výraz vyvolání vytvořen připojením výrazu řazené kolekce členů k výrazu, který je k volání.
Typ výrazu vyvolání je výstupní typ signatury, kterou chcete volat.

Například pokud `Op` je operace s podpisovým `((Int, Qubit) => Double)`, `Op(3, qubit1)` je výraz typu `Double`.
Podobně, pokud je `Sin` funkce s podpisovým `(Double -> Double)`, `Sin(0.1)` je výraz typu `Double`.
Nakonec, pokud je `Builder` funkce se signaturou `(Int -> (Int -> Int))`, `Builder(3)` je funkce z do int.

Vyvolání výsledku výrazu s možností volání vyžaduje navíc pár závorek kolem volání.
Proto pokud chcete vyvolat výsledek volání `Builder` z předchozího odstavce, správná syntaxe je:

```qsharp
(Builder(3))(2)
```

Při vyvolání typu, který se dá volat, se skutečné parametry typu můžou zadat v lomených závorkách `<` a `>` po možném výrazu.
To je obvykle zbytečné, protože kompilátor Q # odvodí skutečné typy.
Je vyžadován pro částečnou aplikaci (viz níže), pokud je argument typu bez parametrů ponechán neurčen.
Někdy je to užitečné i při předávání operací s různými funktory, které jsou schopné volat.

Pokud má například `Func` signatura `('T1, 'T2, 'T1) -> 'T2`, `Op1` a `Op2` mají signatury `(Qubit[] => Unit is Adj)`a `Op3` má podpis `(Qubit[] => Unit)`, k vyvolání `Func` s `Op1` jako první argument, `Op2` jako druhé a `Op3` jako třetí:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

Specifikace typu je povinná, protože `Op3` a `Op1` mají různé typy, takže kompilátor bude považovat za dvojznačný bez specifikace.

### <a name="partial-application"></a>Částečná aplikace

S ohledem na výraz, který lze volat, lze vytvořit novou voláním podmnožiny argumentů, které lze volat.
Tato metoda se nazývá _Částečná aplikace_.

V Q # je částečně aplikovaná metoda volání vyjádřena zapsáním normálního výrazu vyvolání, ale pomocí podtržítka, `_`pro neurčené argumenty.
Výsledná volat má stejný typ výsledku jako základní volat a stejné specializace pro operace.
Vstupní typ částečné aplikace je jednoduše původní typ, ze kterého byly odebrány zadané argumenty.

Pokud se proměnlivá proměnná předává jako zadaný argument při vytváření částečné aplikace, použije se aktuální hodnota proměnné.
Změna hodnoty proměnné následně nebude mít vliv na částečnou aplikaci.

Například pokud `Op` má typ `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:

- `Op(5,(_,_))` má `(((Qubit,Qubit), Double) => Unit is Adj)`typu, a proto má `Op(5,_)`.
- `Op(_,(_,1.0))` má `((Int, (Qubit,Qubit)) => Unit is Adj)`typu.
- `Op(_,((q1,q2),_))` má `((Int,Double) => Unit is Adj)`typu.
   Všimněte si, že se tady používá ekvivalenci typu Singleton v řazené kolekci členů.

Pokud má částečně použité volání metody typu, které kompilátor nemůže odvodit, musí být k dispozici na webu vyvolání.
Částečná aplikace nemůže mít nespecifikované parametry typu.

Například pokud `Op` má typ `(('T1, Qubit, 'T1) => Unit : Adjoint)`:

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a>Rekurze

Je možné, že volat v Q # můžou být přímo nebo nepřímo rekurzivní.
To znamená, že operace nebo funkce může volat sám sebe nebo může volat jinou metodu, kterou přímo nebo nepřímo volá operaci, kterou lze volat.

Existují dva důležité komentáře k použití rekurze, ale:

- Použití rekurze v operacích může být v konfliktu s některými optimalizacemi.
  To může mít zásadní vliv na dobu provádění algoritmu.
- Při provádění na skutečném zařízení ve formátu paměti může být prostor zásobníku omezený a důkladná rekurze může vést k chybě za běhu.
  Konkrétně kompilátor Q # a modul runtime neidentifikují a optimalizují koncovou rekurzi.

## <a name="tuple-expressions"></a>Výrazy řazené kolekce členů

Literál řazené kolekce členů je sekvence výrazů prvků příslušného typu oddělených čárkami, které jsou uzavřeny v `(` a `)`.
Například `(1, One)` je výraz `(Int, Result)`.

Kromě literálů jsou jedinými výrazy řazené kolekce členů symboly, které jsou vázány na hodnoty řazené kolekce členů, prvky pole řazené kolekce členů a volání, která vrací řazené kolekce členů.

## <a name="user-defined-type-expressions"></a>Výrazy uživatelsky definovaného typu

Literál uživatelsky definovaného typu se skládá z názvu typu následovaného literálem řazené kolekce členů základního typu řazené kolekce členů typu.
Například pokud `IntPair` je uživatelem definovaný typ založený na `(Int, Int)`, pak `IntPair(2,3)` být platným literálem tohoto typu.

Kromě literálů jsou jedinými výrazy uživatelsky definovaného typu symboly, které jsou vázány na hodnoty daného typu, prvky pole polí daného typu a volání, která vrací tento typ.

## <a name="unwrap-expressions"></a>Rozbalit výrazy

V Q # je operátorem rozbalení znak koncového vykřičníku `!`.
Například pokud `IntPair` je uživatelem definovaný typ s podkladovým typem `(Int, Int)`a `s` byla proměnná s hodnotou `IntPair(2,3)`, `s!` `(2,3)`.

Pro uživatelsky definované typy definované v jiných uživatelsky definovaných typech. operátor rozbalení může být opakován; například `s!!` označuje dvakrát nezabalenou hodnotu `s`.
Proto pokud `WrappedPair` je uživatelem definovaný typ s podkladovým typem `IntPair`a `t` je proměnná s hodnotou `WrappedPair(IntPair(1,2))`, `t!!` `(1,2)`.

Operátor `!` má vyšší prioritu než všechny ostatní operátory kromě `[]` pro indexování pole a vytváření řezů.
umístění vazby `!` a `[]`. To znamená, `a[i]![3]` by měly být čteny jako `((a[i])!)[3]`: přebírat `i`"th elementu `a`, rozbalíte ho a pak získáme třetí prvek nezabalené hodnoty (který musí být pole).

Priorita operátoru `!` má jeden dopad, který nemusí být zřejmý.
Vrátí-li funkce nebo operace hodnotu, která je poté nezabalena, musí být volání funkce nebo operace uzavřena v závorkách, aby se argumenty řazené kolekce členů navázaly na volání, nikoli na rozbalení.
Příklad:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Výrazy Array

Literál pole je sekvence jednoho nebo více výrazů prvků, které jsou odděleny čárkami a uzavřeny v `[` a `]`.
Všechny elementy musí být kompatibilní se stejným typem.

Je-li běžný typ prvku typ operace nebo funkce, všechny prvky musí mít stejné vstupní a výstupní typy.
Typ elementu pole bude podporovat všechny funktory, které jsou podporovány všemi prvky.
Například pokud jsou `Qubit[] => Unit``Op1`, `Op2`a `Op3`, ale `Op1` podporuje `Adjoint`, `Op2` podporuje `Controlled`a `Op3` podporuje obojí:

- `[Op1, Op2]` je pole `(Qubit[] => Unit)`ch operací.
- `[Op1, Op3]` je pole `(Qubit[] => Unit is Adj)`ch operací.
- `[Op2, Op3]` je pole `(Qubit[] => Unit is Ctl)`ch operací.

Prázdné literály pole, `[]`, nejsou povoleny.
Místo toho, aby používaly `new ★[0]`, kde `★` jako zástupný symbol pro vhodný typ, umožňuje vytvořit požadované pole s nulovou délkou.

Zadáním dvou polí stejného typu lze pomocí binárního operátoru `+` vytvořit nové pole, které je zřetězením dvou polí.
Například `[1,2,3] + [4,5,6]` je `[1,2,3,4,5,6]`.

### <a name="array-creation"></a>Vytvoření pole

Když je zadán typ a výraz `Int`, operátor `new` lze použít k přidělení nového pole dané velikosti.
`new Int[i+1]` by například přidělila nové pole `Int` s `i+1` elementy.

Prvky nového pole jsou inicializovány na výchozí hodnotu závislou na typu.
Ve většině případů se jedná o nějakou odchylku nuly.

Pro qubits a volat, které jsou odkazy na entity, neexistuje přiměřená výchozí hodnota.
Proto pro tyto typy je výchozí hodnota neplatný odkaz, který nelze použít, aniž by došlo k chybě za běhu.
To se podobá odkazu s hodnotou null v jazycích, C# jako je například nebo Java.
Pole obsahující qubits nebo volat musí být správně inicializována s jinými než výchozími hodnotami, aby bylo možné jejich prvky bezpečně použít. Vhodné inicializační rutiny lze nalézt v <xref:microsoft.quantum.arrays>.

Výchozí hodnoty pro každý typ jsou:

Typ | Výchozí
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | _Neplatný qubit_
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | Prázdný rozsah `1..1..0`
 `Callable` | _Neplatný volat_
 `Array['T]` | `'T[0]`

Typy řazené kolekce členů jsou inicializovány elementem po prvku.


### <a name="jagged-arrays"></a>Vícenásobná pole

Vícenásobné pole, někdy označované jako "pole polí", je pole, jehož prvky jsou pole. Prvky vícenásobného pole mohou mít různé velikosti. Následující příklad ukazuje, jak deklarovat a inicializovat vícenásobné pole reprezentující tabulku násobení.

```qsharp
let N = 4;
mutable multiplicationTable = new Int[][N];
for (i in 1..N) {

    mutable row = new Int[i];
    for (j in 1..i) {
        set row w/= j-1 <- i * j;
    }
    set multiplicationTable w/= i-1 <- row;
}
```


### <a name="array-slices"></a>Řezy pole

S ohledem na výraz pole a výraz `Range` může být výraz New vytvořen pomocí operátoru `[` a `]`ho průřezu pole.
Nový výraz bude stejný jako typ pole a bude obsahovat položky pole indexované prvky `Range`v pořadí definovaném `Range`.
Například pokud je `a` svázán s polem `Double`s, pak `a[3..-1..0]` je výraz `Double[]`, který obsahuje první čtyři prvky `a`, ale v obráceném pořadí, jak jsou uvedeny v `a`.

Pokud je `Range` prázdné, bude výsledný řez pole nulovou délkou.

Pokud výraz pole není jednoduchý identifikátor, musí být uzavřen závorky, aby bylo možné vytvořit řezy.
Například pokud `a` a `b` jsou pole `Int`s, řez z zřetězení by byl vyjádřen jako:

```qsharp
(a+b)[1..2..7]
```

Všechna pole v Q # jsou založená na nule.
To znamená, že první prvek pole `a` je vždy `a[0]`.

Od naší verze 0,8 podporujeme kontextové výrazy pro průřezy rozsahu. Konkrétně je možné vynechat počáteční a koncové hodnoty rozsahu v kontextu výrazu průřezu rozsahu. V takovém případě kompilátor použije následující pravidla k odvodit zamýšlené oddělovače pro daný rozsah. 

Pokud je třeba počáteční hodnota rozsahu vynechána, pak odvozená počáteční hodnota. 
- je nula, pokud není zadán žádný krok, nebo je zadaný krok kladný a 
- je délka pole v průřezu minus jedna, pokud je zadaný krok záporný. 

Pokud je hodnota konec rozsahu vynechána, pak odvozená koncová hodnota 
- je délka pole řezu minus jedna, pokud není zadán žádný krok, nebo je zadaný krok kladný a 
- je nula, pokud je zadaný krok záporný. 

```qsharp
let arr = [1,2,3,4,5,6];
let slice1  = arr[3...];      // slice1 is [4,5,6];
let slice2  = arr[0..2...];   // slice2 is [1,3,5];
let slice3  = arr[...2];      // slice3 is [1,2,3];
let slice4  = arr[...2..3];   // slice4 is [1,3];
let slice5  = arr[...2...];   // slice5 is [1,3,5];
let slice7  = arr[4..-2...];  // slice7 is [5,3,1];
let slice8  = arr[...-1..3];  // slice8 is [6,5,4];
let slice9  = arr[...-1...];  // slice9 is [6,5,4,3,2,1];
let slice10 = arr[...];       // slice10 is [1,2,3,4,5,6];
```

## <a name="array-element-expressions"></a>Výrazy prvků pole

S ohledem na výraz pole a výraz `Int` může být výraz New vytvořen pomocí operátoru `[` a `]` elementu pole.
Nový výraz bude stejného typu jako typ prvku pole.
Pokud je například `a` svázán s polem `Double`s, pak `a[4]` je výraz `Double`.

Pokud výraz pole není jednoduchý identifikátor, musí být uzavřen závorky, aby bylo možné vybrat prvek.
Například pokud `a` a `b` jsou pole `Int`s, prvek ze zřetězení by byl vyjádřen jako:

```qsharp
(a+b)[13]
```

Všechna pole v Q # jsou založená na nule.
To znamená, že první prvek pole `a` je vždy `a[0]`.


## <a name="copy-and-update-expressions"></a>Výrazy kopírování a aktualizace

Nová pole je možné vytvořit z existujících pomocí výrazů kopírování a aktualizace.
Výraz kopírování a aktualizace je výrazem `expression1 w/ expression2 <- expression3`formuláře, kde `expression1` musí být typu `T[]` pro určitý typ `T`. Druhý `expression2` definuje indexy prvků, které mají být upraveny v porovnání s polem v `expression1` a musí být buď typu `Int`, nebo typu `Range`. Pokud je `expression2` typu `Int`, `expression3` musí být typu `T`. Pokud je `expression2` typu `Range`, `expression3` musí být typu `T[]`.

Výraz kopie a aktualizace `arr w/ idx <- value` vytvoří nové pole se všemi prvky nastavenými na odpovídající prvek v `arr`, s výjimkou elementů v `idx`, které jsou nastaveny na jeden nebo s v `value`. Pokud například `arr` obsahuje `[0,1,2,3]`pole, pak 
- `arr w/ 0 <- 10` je pole `[10,1,2,3]`.
- `arr w/ 2 <- 10` je pole `[0,1,10,3]`.
- `arr w/ 0..2..3 <- [10,12]` je pole `[10,1,12,3]`.

Podobné výrazy existují pro pojmenované položky v uživatelsky definovaných typech. Zvažte například typ. 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Pokud `c` obsahuje hodnotu typu `Complex(1.,-1.)`a pak `c w/ Re <- 0.` je výraz typu `Complex`, který je vyhodnocen jako `Complex(0.,-1.)`.

## <a name="conditional-expressions"></a>Podmíněné výrazy

Vzhledem k dvěma dalším výrazům stejného typu a logickému výrazu může být podmíněný výraz vytvořen pomocí otazníku `?` a svislým pruhem `|`.
`a==b ? c | d`například.
V tomto příkladu bude hodnota podmíněného výrazu `c`, pokud má `a==b` hodnotu true a `d`, pokud má hodnotu false.

Tyto dva výrazy mohou být vyhodnoceny na operace, které mají stejné vstupy a výstupy, ale podporují různé funktory.
V tomto případě typ podmíněného výrazu je operace s těmito vstupy a výstupy, které podporují všechny funktory Podporované oběma výrazy.
Například pokud jsou `Qubit[]=>Unit``Op1`, `Op2`a `Op3`, ale `Op1` podporuje `Adjoint`, `Op2` podporuje `Controlled`a `Op3` podporuje obojí:

- `flag ? Op1 | Op2` je operace `(Qubit[] => Unit)`.
- `flag ? Op1 | Op3` je operace `(Qubit[] => Unit is Adj)`.
- `flag ? Op2 | Op3` je operace `(Qubit[] => Unit is Ctl)`.

Pokud jeden ze dvou možných výsledných výrazů zahrnuje volání funkce nebo operace, bude toto volání provedeno pouze v případě, že je výsledkem ta, která bude hodnotou volání.
Například v případě `a==b ? C(qs) | D(qs)`, pokud je `a==b` true, bude vyvolána operace `C`, a pokud je hodnota false, bude vyvolána pouze `D`.
To se podobá krátkodobému okruhu v jiných jazycích.


## <a name="operator-precedence"></a>Priorita operátorů

Všechny binární operátory jsou asociativní zprava, s výjimkou `^`.

Hranaté závorky, `[` a `]`pro průřezy pole a indexování se sváže před jakýmkoli operátorem.

Funktory `Adjoint` a vazba `Controlled` po vyřazení pole, ale před všemi ostatními operátory.

Kulaté závorky pro operace a volání funkce se také vážou před libovolným operátorem, ale po vyřazení a funktory pole.

Operátory v pořadí podle priority, od nejvyšších po nejnižší:

Operátor | Aritou | Popis | Typy operandů
---------|----------|---------|---------------
 koncový `!` | Unární | Rozbalení | Libovolný uživatelsky definovaný typ
 `-`, `~~~`, `not` | Unární | Numerický negativní, bitový doplněk, logická negace | `Int`, `BigInt` nebo `Double` pro `-`, `Int` nebo `BigInt` pro `~~~``Bool``not`
 `^` | Binární hodnota | Celočíselný výkon | `Int` nebo `BigInt` pro základní `Int` pro exponent
 `/`, `*`, `%` | Binární hodnota | Dělení, násobení, celočíselné zbytky | `Int`, `BigInt` nebo `Double` pro `/` a `*``Int` nebo `BigInt` pro `%`
 `+`, `-` | Binární hodnota | Sčítání nebo řetězce a zřetězení polí, odčítání | `Int`, `BigInt` nebo `Double`, navíc `String` nebo libovolný typ pole pro `+`
 `<<<`, `>>>` | Binární hodnota | Levý SHIFT, posun doprava | `Int` nebo `BigInt`
 `<`, `<=`, `>`, `>=` | Binární hodnota | Méně než, méně než nebo-rovno, větší než, větší než nebo rovno, větší než nebo rovno | `Int`, `BigInt` nebo `Double`
 `==`, `!=` | Binární hodnota | rovná se, nerovná se porovnávání | jakýkoli primitivní typ
 `&&&` | Binární hodnota | Bitový operátor AND | `Int` nebo `BigInt`
 `^^^` | Binární hodnota | Bitový operátor XOR | `Int` nebo `BigInt`
 <code>\|\|\|</code> | Binární hodnota | Bitový operátor OR | `Int` nebo `BigInt`
 `and` | Binární hodnota | Logický operátor AND | `Bool`
 `or` | Binární hodnota | Logický operátor OR | `Bool`
 `..` | Binární/Ternární | Operátor rozsahu | `Int`
 `?` `|` | Ternární | Podmíněné | `Bool` na levé straně
`w/` `<-` | Ternární | Kopírování a aktualizace | viz [výrazy pro kopírování a aktualizaci](#copy-and-update-expressions)
