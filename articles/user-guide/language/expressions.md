---
title: 'Výrazy typu v Q #'
description: 'Pochopte, jak zadat, odkazovat a kombinovat konstanty, proměnné, operátory, operace a funkce jako výrazy v Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: b32644382bb88fb11da00d0d7d78bbd797a0eaaa
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/09/2020
ms.locfileid: "84629998"
---
# <a name="type-expressions-in-q"></a>Výrazy typu v Q #

## <a name="numeric-expressions"></a>Číselné výrazy

Číselné výrazy jsou výrazy typu `Int` , `BigInt` nebo `Double` .
To znamená, že jsou buď celá čísla, nebo čísla s plovoucí desetinnou čárkou.

`Int`literály v Q # jsou zapsány jednoduše jako sekvence číslic.
Šestnáctková a binární celá čísla jsou podporována `0x` `0b` předponou a v uvedeném pořadí.

`BigInt`literály v Q # jsou napsané s koncovým znakem `l` nebo `L` příponou.
Předpona "0x" je podporována hexadecimálními velkými čísly.
Následující jsou tedy všechna platná použití `BigInt` literálů:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double`literály v Q # jsou čísla s plovoucí desetinnou čárkou napsaná pomocí desítkových číslic.
Můžou se zapisovat pomocí desetinné čárky, `.` , nebo exponenciální části označené písmenem "e" nebo "e" (po tom, že jsou platné pouze možné záporné znaménko a desítkové číslice).
Níže jsou uvedené platné `Double` literály: `0.0` , `1.2e5` , `1e-5` .

Vzhledem k výrazu pole libovolného typu elementu `Int` může být výraz vytvořen pomocí [`Length`](xref:microsoft.quantum.core.length) předdefinované funkce s výrazem pole uzavřeným v závorkách `(` a `)` .
Například pokud `a` je svázána s polem, pak `Length(a)` je celočíselný výraz.
Pokud `b` je pole polí celých čísel, `Int[][]` , pak `Length(b)` je počet dílčích polí v a `b` `Length(b[1])` je počet celých čísel ve druhém dílčím poli v `b` .

Zadané dva číselné výrazy stejného typu, binární operátory `+` ,, `-` `*` a `/` mohou být použity k vytvoření nového číselného výrazu.
Typ nového výrazu bude stejný jako u typů výrazů prvků.

Zadaným dvěma celočíselnými výrazy lze binární operátor `^` (napájení) použít k vytvoření nového celočíselného výrazu.
Podobně `^` lze použít se dvěma dvojitými výrazy pro vytvoření nového dvojitého výrazu.
Nakonec `^` lze použít s velkým celým číslem na levé straně a celým číslem na pravé straně k vytvoření nového výrazu Big Integer.
V takovém případě se druhý parametr musí vejít do 32 bitů; v takovém případě se vyvolá Běhová chyba.

Předané dva celočíselné nebo velké celočíselné výrazy mohou být vytvořeny pomocí `%` operátorů (modulo), `&&&` (bitové a), `|||` (bitových nebo) nebo `^^^` (bitových operátorů XOR).

Pro vytvoření nového výrazu stejného typu, který je použit jako levý výraz, lze použít buď celočíselný nebo velký celočíselný výraz na levé straně, a výraz typu Integer na pravé straně, `<<<` operátor (aritmetický levý SHIFT) nebo `>>>` (aritmetický posun Shift).

Druhý parametr (velikost posunu) pro operaci posunu musí být větší nebo roven nule. chování pro záporné hodnoty posunutí není definováno.
Velikost SHIFT pro buď operaci posunutí musí být také do 32 bitů. v takovém případě se vyvolá Běhová chyba.
Pokud číslo, které má být posunuto, je celé číslo, hodnota posunutí je interpretována `mod 64` ; to znamená, že posun 1 a posun 65 mají stejný účinek.

Pro celočíselné i velké celočíselné hodnoty jsou posunuty aritmetické operace.
Posunutí záporné hodnoty doleva nebo doprava bude mít za následek záporné číslo.
To znamená, že posun jednoho kroku doleva nebo doprava je přesně stejný jako násobení nebo dělení 2, v uvedeném pořadí.

Celočíselné dělení a celočíselné zbytky se řídí stejným chováním pro záporná čísla jako C#.
To znamená, že `a % b` vždy bude mít stejné znaménko jako `a` a `b * (a / b) + a % b` bude vždy rovno `a` .
Například:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

Dělení velkých celých čísel a Modulus funguje stejným způsobem.

V případě libovolného číselného výrazu může být výraz New vytvořen pomocí `-` unárního operátoru.
Nový výraz bude stejného typu jako výraz prvku.

S ohledem na libovolný celočíselný nebo velký celočíselný výraz může být nový výraz stejného typu vytvořen pomocí `~~~` unárního operátoru (bitového doplňku).

## <a name="boolean-expressions"></a>Výrazy logických hodnot

Dvě `Bool` hodnoty literálu jsou `true` a `false` .

Vzhledem k jakýmkoliv dvěma výrazům stejného primitivního typu lze `==` `!=` použít binární operátory a k vytvoření `Bool` výrazu.
Výraz bude true, pokud jsou dva výrazy stejné, a false, pokud ne.

Hodnoty uživatelsky definovaných typů nelze porovnat, lze porovnat pouze jejich nezabalené hodnoty. Například pomocí operátoru "Unwrap" `!` (popsaný v podrobnostech na [typech v Q #](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

Porovnání rovnosti pro `Qubit` hodnoty je rovnost identity; to znamená, zda dva výrazy identifikují stejný qubit.
Stav obou qubits se neshoduje, nepoužívá se, neměří ani nemění pomocí tohoto porovnání.

Porovnání rovnosti pro `Double` hodnoty může být zavádějící z důvodu zaoblení efektů.
Například `49.0 * (1.0/49.0) != 1.0` .

Vzhledem k tomu, že jsou zadány dva číselné výrazy, binární operátory `>` , `<` , `>=` a lze `<=` použít k vytvoření nového logického výrazu, který je true, pokud je první výraz v tomto pořadí větší než, menší než nebo roven nebo menší nebo roven druhému výrazu.

Za daných dvou logických výrazů lze `and` `or` binární operátory a použít k vytvoření nového logického výrazu, který má hodnotu true, pokud oba výrazy (odp. buď nebo obojí z) jsou pravdivé.

S ohledem na logický výraz `not` může být unární operátor použit k vytvoření nového logického výrazu, který je true, pokud je výraz prvku false.

## <a name="string-expressions"></a>Řetězcové výrazy

Q # povoluje použití řetězců v `fail` příkazu (vysvětleno v [toku řízení](xref:microsoft.quantum.guide.controlflow#fail-statement)) a ve [`Message`](xref:microsoft.quantum.intrinsic.message) funkci Standard.
Konkrétní chování druhé závisí na použitém simulátoru, ale obvykle zapisuje zprávu do hostitelské konzole při volání během programu Q #.

Řetězce v Q # jsou buď literály nebo interpolované řetězce.

Řetězcové literály jsou podobně jako jednoduché řetězcové literály ve většině jazyků: sekvence znaků Unicode uzavřených do dvojitých uvozovek, `"` .
Uvnitř řetězce je možné znak zpětného lomítka `\` použít k úniku znaku dvojité uvozovky a vložit nový řádek jako znak návratu na začátek řádku `\n` `\r` a kartu jako `\t` .
Například:

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a>Interpolované řetězce

Syntaxe Q # pro řetězcové interpolace je podmnožinou syntaxe jazyka C#, ale je zde shrnuto klíčové body, které se týkají Q #.
Hlavní rozdíly jsou popsány níže.

Pro identifikaci řetězcového literálu jako interpolované řetězce, předřaďte ho `$` symbolem.
Mezi znakem `$` a `"` , který začíná řetězcovým literálem, nelze zadat prázdný znak.

Následuje základní příklad použití [`Message`](xref:microsoft.quantum.intrinsic.message) funkce k zápisu výsledku měření do konzoly spolu s dalšími výrazy Q #.

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
Libovolný platný výraz Q # se může objevit v interpolované řetězci.

Další podrobnosti o syntaxi jazyka C# lze nalézt v [*řetězci interpolované řetězce*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).
Nejvýraznějším rozdílem je, že Q # nepodporuje doslovné (víceřádkové) interpolované řetězce.
Výrazy uvnitř interpolované řetězce následují syntax Q #, nikoli syntaxe jazyka C#.

## <a name="range-expressions"></a>Výrazy rozsahu

S ohledem na tři `Int` výrazy `start` , `step` , `stop` a `start .. step .. stop` je výraz rozsahu, jehož prvním prvkem je `start` , druhý prvek je, `start+step` třetí prvek je `start+step+step` atd., dokud `stop` není předán.
Rozsah může být prázdný, pokud je instance například `step` pozitivní a `stop < start` .
Poslední prvek rozsahu bude, `stop` Pokud rozdíl mezi `start` a `stop` je integrální násobek `step` ; to znamená, že rozsah je zahrnut na obou koncích.

Při daných dvou `Int` výrazech `start` a `stop` `start .. stop` je výraz rozsahu, který je roven `start .. 1 .. stop` .
Všimněte si, že předpokládaná `step` je + 1, i když `stop` je menší než `start` ; v takovém případě je rozsah prázdný.

Mezi příklady oblastí patří:

- `1..3`je rozsah 1, 2, 3.
- `2..2..5`je rozsah 2, 4.
- `2..2..6`je rozsah 2, 4, 6.
- `6..-2..2`je rozsah 6, 4, 2.
- `2..1`je prázdný rozsah.
- `2..6..7`je rozsah 2.
- `2..2..1`je prázdný rozsah.
- `1..-1..2`je prázdný rozsah.

## <a name="qubit-expressions"></a>Výrazy qubit

Jediné `Qubit` výrazy jsou symboly, které jsou vázány na `Qubit` hodnoty nebo prvky pole `Qubit` polí.
Neexistují žádné `Qubit` literály.

## <a name="pauli-expressions"></a>Výrazy Pauli

Čtyři `Pauli` hodnoty, `PauliI` ,, `PauliX` `PauliY` a `PauliZ` , jsou platné `Pauli` výrazy.

Kromě toho jsou jedinými `Pauli` výrazy symboly, které jsou vázány na `Pauli` hodnoty nebo prvky pole `Pauli` polí.

## <a name="result-expressions"></a>Výsledné výrazy

Dvě `Result` hodnoty `One` a `Zero` jsou platné `Result` výrazy.

Kromě toho jsou jedinými `Result` výrazy symboly, které jsou vázány na `Result` hodnoty nebo prvky pole `Result` polí.
Konkrétně si všimněte, že není `One` stejný jako celé číslo `1` a mezi nimi není přímý převod.
Totéž platí pro `Zero` a `0` .

## <a name="tuple-expressions"></a>Výrazy řazené kolekce členů

Literál řazené kolekce členů je sekvence výrazů prvků příslušného typu, které jsou odděleny čárkami a uzavřeny v `(` a `)` .
Například `(1, One)` je `(Int, Result)` výraz.

Kromě literálů jsou jedinými výrazy řazené kolekce členů symboly, které jsou vázány na hodnoty řazené kolekce členů, prvky pole řazené kolekce členů a volání, která vrací řazené kolekce členů.

## <a name="user-defined-type-expressions"></a>Výrazy uživatelsky definovaného typu

Literál uživatelsky definovaného typu se skládá z názvu typu následovaného literálem řazené kolekce členů základního typu řazené kolekce členů typu.
Například pokud `IntPair` je uživatelem definovaný typ založený na `(Int, Int)` , pak `IntPair(2, 3)` by byl platným literálem tohoto typu.

Kromě literálů jsou jedinými výrazy uživatelsky definovaného typu symboly, které jsou vázány na hodnoty daného typu, prvky pole polí daného typu a volání, která vrací tento typ.

## <a name="unwrap-expressions"></a>Rozbalit výrazy

V Q # se operátor rozbalení označuje jako koncová značka vykřičník `!` .
Například pokud `IntPair` je uživatelem definovaný typ s podkladovým typem `(Int, Int)` a `s` byl proměnnou s hodnotou `IntPair(2, 3)` , potom `s!` by byl `(2, 3)` .

Pro uživatelsky definované typy definované v jiných uživatelsky definovaných typech se může opakovat operátor rozbalení; například `s!!` označuje zdvojnásobně nezabalenou hodnotu `s` .
Proto, pokud `WrappedPair` je uživatelem definovaný typ s podkladovým typem `IntPair` , a `t` je proměnná s hodnotou `WrappedPair(IntPair(1,2))` , potom `t!!` by byla `(1,2)` .

`!`Operátor má vyšší prioritu než všechny ostatní operátory, kromě `[]` indexace pole a řezů.
`!`a dá se `[]` vytvořit vazba. to znamená, že `a[i]![3]` by měl být čten jako `((a[i])!)[3]` : Vezměte `i` "element" `a` , rozbalíte ho a pak Získejte třetí prvek nezabalené hodnoty (který musí být pole).

Priorita `!` operátoru má jeden dopad, který nemusí být zřejmý.
Vrátí-li funkce nebo operace hodnotu, která je poté nezabalena, musí být volání funkce nebo operace uzavřena v závorkách, aby se argumenty řazené kolekce členů navázaly na volání, nikoli na rozbalení.
Například:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Výrazy Array

Literál pole je sekvence jednoho nebo více výrazů prvků, které jsou odděleny čárkami a uzavřeny v `[` a `]` .
Všechny elementy musí být kompatibilní se stejným typem.

Při zadání dvou polí stejného typu `+` může být binární operátor použit k vytvoření nového pole, které je zřetězením dvou polí.
Například `[1,2,3] + [4,5,6]` je `[1,2,3,4,5,6]` .

### <a name="array-creation"></a>Vytvoření pole

Pro daný typ a `Int` výraz lze `new` operátor použít k přidělení nového pole dané velikosti.
Například `new Int[i + 1]` by bylo přiděleno nové `Int` pole s `i + 1` prvky.

Prázdné literály pole, `[]` nejsou povoleny.
Místo toho použití `new ★[0]` , kde `★` je jako zástupný symbol pro vhodný typ, umožňuje vytvořit požadované pole s nulovou délkou.

Prvky nového pole jsou inicializovány na výchozí hodnotu závislou na typu.
Ve většině případů se jedná o nějakou odchylku nuly.

Pro qubits a volat, které jsou odkazy na entity, neexistuje přiměřená výchozí hodnota.
Proto pro tyto typy je výchozí hodnota neplatný odkaz, který nelze použít, aniž by došlo k chybě za běhu.
To se podobá odkazu s hodnotou null v jazycích, jako je C# nebo Java.
Pole obsahující qubits nebo volat musí být správně inicializována s jinými než výchozími hodnotami, aby bylo možné jejich prvky bezpečně použít. Vhodné inicializační rutiny lze nalézt v <xref:microsoft.quantum.arrays> .

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
 `Range` | Prázdný rozsah`1..1..0`
 `Callable` | _Neplatný volat_
 `Array['T]` | `'T[0]`

Typy řazené kolekce členů jsou inicializovány elementem po prvku.


### <a name="array-elements"></a>Prvky pole

S ohledem na výraz pole a `Int` výraz může být nový výraz vytvořen pomocí `[` `]` operátoru a elementu pole.
Nový výraz bude stejného typu jako typ prvku pole.
Například pokud `a` je svázán s polem `Double` s, pak `a[4]` je `Double` výraz.

Pokud výraz pole není jednoduchý identifikátor, musí být uzavřen v závorkách, aby bylo možné vybrat prvek.
Například pokud `a` a `b` jsou obě pole třídy `Int` s, prvek ze zřetězení by byl vyjádřen jako:

```qsharp
(a + b)[13]
```

Všechna pole v Q # jsou založená na nule.
To znamená, že první prvek pole `a` je vždy `a[0]` .


### <a name="array-slices"></a>Řezy pole

S ohledem na výraz pole a `Range` výraz může být výraz New vytvořen pomocí `[` `]` operátoru a řezu Array.
Nový výraz bude stejný jako typ pole a bude obsahovat položky pole indexované prvky `Range` , v pořadí definovaném `Range` .
Například pokud `a` je svázána s polem `Double` s, pak `a[3..-1..0]` je `Double[]` výraz, který obsahuje první čtyři prvky, `a` ale v obráceném pořadí, jak jsou uvedeny v `a` .

Pokud `Range` je pole prázdné, bude výsledný řez pole nulovou délkou.

Stejně jako u odkazů na prvky pole, pokud výraz pole není jednoduchý identifikátor, musí být uzavřeny závorky, aby bylo možné vytvořit řezy.
Pokud `a` a `b` jsou obě pole typu `Int` s, řez z zřetězení by byl vyjádřen jako:

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a>Odvozené počáteční/koncové hodnoty

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

### <a name="copy-and-update-expressions"></a>Výrazy kopírování a aktualizace

Vzhledem k tomu, že všechny typy Q # jsou typy hodnot – s qubitsem, který vychází z trochu speciální role, je vytvořena "kopie", když je hodnota vázána na symbol, nebo když je symbol převázán. To znamená, že chování Q # je stejné jako při vytvoření kopie při přiřazení.
Samozřejmě v praxi jsou ve skutečnosti v případě potřeby znovu vytvořeny pouze relevantní součásti. 

Konkrétně to zahrnuje také pole.
Konkrétně není možné aktualizovat položky pole. Chcete-li upravit existující pole, je nutné využít mechanismus *kopírování a aktualizace* .

Nová pole je možné vytvořit z existujících pomocí výrazů *kopírování a aktualizace* .
Výraz kopírování a aktualizace je výrazem formuláře `expression1 w/ expression2 <- expression3` , kde `expression1` musí být typu `T[]` pro nějaký typ `T` .
Druhý `expression2` definuje indexy prvků, které mají být upraveny v porovnání s polem v `expression1` a musí být buď typu `Int` nebo typu `Range` .
Pokud `expression2` je typ `Int` , `expression3` musí být typu `T` . Pokud `expression2` je typ `Range` , `expression3` musí být typu `T[]` .

Výraz kopírování a aktualizace `arr w/ idx <- value` vytvoří nové pole se všemi prvky nastavenými na odpovídající element v `arr` , s výjimkou elementů v `idx` , které jsou nastaveny na jeden (y) v `value` . Například pokud `arr` obsahuje pole `[0,1,2,3]` , pak 
- `arr w/ 0 <- 10`je pole `[10,1,2,3]` .
- `arr w/ 2 <- 10`je pole `[0,1,10,3]` .
- `arr w/ 0..2..3 <- [10,12]`je pole `[10,1,12,3]` .

#### <a name="copy-and-update-expressions-for-named-items"></a>Výrazy kopírování a aktualizace pro pojmenované položky

Podobné výrazy existují pro pojmenované položky v uživatelsky definovaných typech. 

Zvažte například typ. 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Pokud `c` obsahuje hodnotu typu `Complex(1., -1.)` , pak `c w/ Re <- 0.` je výraz typu `Complex` , který je vyhodnocen jako `Complex(0., -1.)` .

### <a name="jagged-arrays"></a>Vícenásobná pole

Vícenásobné pole, někdy označované jako "pole polí", je pole, jehož prvky jsou pole.
Prvky vícenásobného pole mohou mít různé velikosti.
Následující příklad ukazuje, jak deklarovat a inicializovat vícenásobné pole reprezentující tabulku násobení.

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

### <a name="arrays-of-callables"></a>Pole, která se mají volat 

Všimněte si, že další podrobnosti o volat typy lze najít níže a také na další stránce, [operace a funkce v Q #](xref:microsoft.quantum.guide.operationsfunctions).

Je-li běžný typ prvku typ operace nebo funkce, všechny prvky musí mít stejné vstupní a výstupní typy.
Typ elementu pole bude podporovat všechny funktory, které jsou podporovány všemi prvky.
Například pokud `Op1` , `Op2` a `Op3` jsou všechny `Qubit[] => Unit` , ale `Op1` podporují `Adjoint` , `Op2` podporují `Controlled` a `Op3` podporují obojí:

- `[Op1, Op2]`je pole `(Qubit[] => Unit)` operací.
- `[Op1, Op3]`je pole `(Qubit[] => Unit is Adj)` operací.
- `[Op2, Op3]`je pole `(Qubit[] => Unit is Ctl)` operací.

Nicméně zatímco `(Qubit[] => Unit is Adj)` a `(Qubit[] => Unit is Ctl)` operace mají společný základní typ `(Qubit[] => Unit)` , mějte na paměti, že pole *of* těchto operátorů nesdílejí společný základní typ. Například by v `[[Op1], [Op2]]` současné době vyvolala chybu, protože se pokouší vytvořit pole nekompatibilních typů polí `(Qubit[] => Unit is Adj)[]` a `(Qubit[] => Unit is Ctl)[]` .


## <a name="conditional-expressions"></a>Podmíněné výrazy

Vzhledem k dvěma dalším výrazům stejného typu a logickému výrazu může být podmíněný výraz vytvořen pomocí otazníku `?` a svislého panelu `|` .
Například `a==b ? c | d` .
V tomto příkladu bude hodnota podmíněného výrazu v `c` případě hodnoty `a==b` true a v `d` případě false.

### <a name="conditional-expressions-with-callables"></a>Podmíněné výrazy s volat

Tyto dva výrazy mohou být vyhodnoceny na operace, které mají stejné vstupy a výstupy, ale podporují různé funktory.
V tomto případě typ podmíněného výrazu je operace s těmito vstupy a výstupy, které podporují všechny funktory Podporované oběma výrazy.
Například pokud `Op1` , `Op2` a `Op3` jsou všechny `Qubit[]=>Unit` , ale `Op1` podporují `Adjoint` , `Op2` podporují `Controlled` a `Op3` podporují obojí:

- `flag ? Op1 | Op2`je `(Qubit[] => Unit)` operace.
- `flag ? Op1 | Op3`je `(Qubit[] => Unit is Adj)` operace.
- `flag ? Op2 | Op3`je `(Qubit[] => Unit is Ctl)` operace.

Pokud jeden ze dvou možných výsledných výrazů zahrnuje volání funkce nebo operace, bude toto volání provedeno pouze v případě, že je výsledkem ta, která bude hodnotou volání.
Například v případě `a==b ? C(qs) | D(qs)` , pokud `a==b` je hodnota true, bude `C` vyvolána operace, a pokud je hodnota false, `D` bude vyvolána pouze.
To se podobá krátkodobému okruhu v jiných jazycích.

## <a name="callable-expressions"></a>Výrazy, které se mají volat

Volatelné literály je název operace nebo funkce definované v oboru kompilace.
Například `X` je literál operace, který odkazuje na standardní `X` operace knihovny a `Message` je literál funkce, který odkazuje na standardní `Message` funkci knihovny.

Pokud operace podporuje `Adjoint` funktor, pak `Adjoint op` je výraz operace.
Podobně platí, že pokud operace podporuje `Controlled` funktor, pak `Controlled op` je výraz operace.
Typy těchto výrazů jsou určeny při [volání specializace operace](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).

Funktory ( `Adjoint` a `Controlled` ) sváže více než všechny ostatní operátory s výjimkou operátoru Unwrap `!` a pole s indexem [].
Níže jsou uvedené všechny právní a za předpokladu, že operace podporují funktory, který se používá:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a>Výrazy s parametry, které je typu volat

Dá se použít jako hodnota, která se dá použít jako hodnota, řekněme, že se přiřadí proměnné nebo přejdou na jinou možnou volat.
V tomto případě musí být v případě, že je možné volat [parametry typu](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), zadány jako součást hodnoty, kterou lze volat.
Hodnota, která se nedá volat, nemůže mít nespecifikované parametry typu.

Pokud `Fun` je například funkce s signaturou `'T1->Unit` :

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Volat výrazy vyvolání

Vzhledem k volání (operace nebo funkce) a výrazu řazené kolekce členů na vstupním typu signatury, která se dá volat, může být výraz vyvolání vytvořen připojením výrazu řazené kolekce členů k výrazu, který je k volání.
Typ výrazu vyvolání je výstupní typ signatury, kterou chcete volat.

Například pokud `Op` je operace s signaturou `((Int, Qubit) => Double)` , `Op(3, qubit1)` je výraz typu `Double` .
Podobně, pokud `Sin` je funkce s signaturou `(Double -> Double)` , `Sin(0.1)` je výraz typu `Double` .
Nakonec, pokud `Builder` je funkce s signaturou `(Int -> (Int -> Int))` , `Builder(3)` je funkce z do int.

Vyvolání výsledku výrazu s možností volání vyžaduje navíc pár závorek kolem volání.
Proto pokud chcete vyvolat výsledek volání `Builder` z předchozího odstavce, správná syntaxe je:

```qsharp
(Builder(3))(2)
```

Při vyvolání [typu](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) , který se dá volat, se skutečné parametry typu můžou zadat v lomených závorkách `<` a `>` po volání výrazu.
To je obvykle zbytečné, protože kompilátor Q # odvodí skutečné typy.
Nicméně *je* vyžadován pro [částečnou aplikaci](xref:microsoft.quantum.guide.operationsfunctions#partial-application) , pokud je argument typu bez parametrů ponechán neurčen.
Někdy je to užitečné i při předávání operací s různými funktory, které jsou schopné volat.

Například pokud `Func` má signatura `('T1, 'T2, 'T1) -> 'T2` a má signaturu `Op1` `Op2` `(Qubit[] => Unit is Adj)` a `Op3` má signaturu, `(Qubit[] => Unit)` pro vyvolání `Func` `Op1` jako první argument jako `Op2` druhý a `Op3` jako třetí:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

Specifikace typu je povinná `Op3` , protože a `Op1` má jiné typy, takže kompilátor bude považovat za dvojznačný bez specifikace.


## <a name="operator-precedence"></a>Priorita operátorů

Všechny binární operátory jsou asociativní zprava, s výjimkou `^` .

Hranaté závorky `[` a `]` pro vytváření řezů a indexování polí sváže před libovolným operátorem.

Funktory `Adjoint` a `Controlled` BIND po vyřazení pole, ale před všemi ostatními operátory.

Kulaté závorky pro operace a volání funkce se také vážou před libovolným operátorem, ale po vyřazení a funktory pole.

Operátory v pořadí podle priority, od nejvyšších po nejnižší:

Operátor | Aritou | Popis | Typy operandů
---------|----------|---------|---------------
 koncové`!` | Unární | Rozbalení | Libovolný uživatelsky definovaný typ
 `-`, `~~~`, `not` | Unární | Numerický negativní, bitový doplněk, logická negace | `Int`, nebo pro, pro, `BigInt` `Double` `-` `Int` `BigInt` `~~~` `Bool` pro`not`
 `^` | Binární | Celočíselný výkon | `Int`nebo `BigInt` pro základ `Int` pro exponent
 `/`, `*`, `%` | Binární | Dělení, násobení, celočíselné zbytky | `Int`, `BigInt` nebo `Double` pro `/` a `*` , `Int` nebo `BigInt` pro`%`
 `+`, `-` | Binární | Sčítání nebo řetězce a zřetězení polí, odčítání | `Int`, `BigInt` nebo `Double` , navíc `String` nebo libovolný typ pole pro`+`
 `<<<`, `>>>` | Binární | Levý SHIFT, posun doprava | `Int` nebo `BigInt`
 `<`, `<=`, `>`, `>=` | Binární | Méně než, méně než nebo-rovno, větší než, větší než nebo rovno, větší než nebo rovno | `Int`, `BigInt` nebo`Double`
 `==`, `!=` | Binární | rovná se, nerovná se porovnávání | jakýkoli primitivní typ
 `&&&` | Binární | Bitový operátor AND | `Int` nebo `BigInt`
 `^^^` | Binární | Bitový operátor XOR | `Int` nebo `BigInt`
 <code>\|\|\|</code> | Binární | Bitový operátor OR | `Int` nebo `BigInt`
 `and` | Binární | Logický operátor AND | `Bool`
 `or` | Binární | Logický operátor OR | `Bool`
 `..` | Binární/Ternární | Operátor rozsahu | `Int`
 `?` `|` | Ternární | Podmíněné | `Bool`na levé straně
`w/` `<-` | Ternární | Kopírování a aktualizace | viz [výrazy pro kopírování a aktualizaci](#copy-and-update-expressions)

## <a name="next-steps"></a>Další kroky

Teď, když můžete pracovat s výrazy v Q #, můžete přejít na [operace a funkce v q #](xref:microsoft.quantum.guide.operationsfunctions) a zjistit, jak definovat a volat operace a funkce.
