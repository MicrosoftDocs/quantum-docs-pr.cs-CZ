---
title: 'Výrazy typu v Q #'
description: 'Pochopte, jak zadat, odkazovat a kombinovat konstanty, proměnné, operátory, operace a funkce jako výrazy v Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: 1821df6a3a51a62b44f3ccd96b127577c5db990a
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415384"
---
# <a name="type-expressions-in-q"></a>Výrazy typu v Q #

## <a name="numeric-expressions"></a>Číselné výrazy

Číselné výrazy jsou výrazy typu `Int` , `BigInt` nebo `Double` .
To znamená, že jsou buď celá čísla, nebo čísla s plovoucí desetinnou čárkou.

`Int`literály v Q # jsou zapsány jako posloupnost číslic.
Šestnáctková a binární celá čísla jsou podporována a zapsána `0x` `0b` předponou a v uvedeném pořadí.

`BigInt`literály v Q # mají koncovou `l` nebo `L` příponu.
Hexadecimální Velká celá čísla jsou podporována a napsána předponou "0x".
Následující jsou tedy všechna platná použití `BigInt` literálů:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double`literály v Q # jsou čísla s plovoucí desetinnou čárkou napsaná pomocí desítkových číslic.
Je možné je zapsat s desetinnou čárkou nebo bez nich, `.` nebo exponenciální částí označenou písmenem "e" nebo "e" (po které jsou platné pouze možné záporné znaménko a desítkové číslice).
Níže jsou uvedené platné `Double` literály: `0.0` , `1.2e5` , `1e-5` .

Vzhledem k výrazu pole libovolného typu elementu můžete vytvořit `Int` výraz pomocí [`Length`](xref:microsoft.quantum.core.length) předdefinované funkce a výraz pole uzavřený v závorkách.
Například pokud `a` je svázána s polem, pak `Length(a)` je celočíselný výraz.
Pokud `b` je pole polí celých čísel, `Int[][]` , pak `Length(b)` je počet dílčích polí v a `b` `Length(b[1])` je počet celých čísel ve druhém dílčím poli v `b` .

Zadané dva číselné výrazy stejného typu, binární operátory `+` ,, `-` `*` a `/` mohou být použity k vytvoření nového číselného výrazu.
Typ nového výrazu je stejný jako u typů výrazů prvků.

Zadaným dvěma celočíselnými výrazy, použijte binární operátor `^` (napájení) k vytvoření nového celočíselného výrazu.
Podobně můžete také použít `^` se dvěma dvojitými výrazy k vytvoření nového dvojitého výrazu.
Nakonec můžete použít `^` s velkým celým číslem na levé straně a celé číslo na pravé straně k vytvoření nového výrazu Big Integer.
V takovém případě se druhý parametr musí vejít do 32 bitů; v takovém případě vyvolá chybu za běhu.

Dané dva celočíselné nebo velké celočíselné výrazy, tvoří nový celočíselný nebo velký celočíselný výraz pomocí `%` operátorů (modulo), `&&&` (bitové a), `|||` (bitových nebo) nebo `^^^` (bitových operátorů XOR).

`<<<` `>>>` Pro vytvoření nového výrazu stejného typu, který je stejný jako výraz na levé straně, použijte operátor Integer nebo Big Integer na levé straně a výraz celého čísla na pravé straně.

Druhý parametr (velikost posunu) pro operaci posunu musí být větší nebo roven nule. chování pro záporné hodnoty posunutí není definováno.
Velikost SHIFT pro buď operaci posunutí musí být také do 32 bitů. v takovém případě vyvolá chybu za běhu.
Pokud je číslo posunuto jako celé číslo, je hodnota posunutí interpretována `mod 64` ; to znamená, že posun 1 a posun 65 mají stejný účinek.

Pro celočíselné i velké celočíselné hodnoty jsou posunuty aritmetické operace.
Posunutí záporné hodnoty buď vlevo nebo vpravo, vede k zápornému číslu.
To znamená, že posun jednoho kroku doleva nebo doprava je stejný jako vynásobení nebo dělení 2, v uvedeném pořadí.

Celočíselné dělení a celočíselné zbytky se řídí stejným chováním pro záporná čísla jako C#.
To znamená, že `a % b` vždy má stejné znaménko jako `a` a `b * (a / b) + a % b` vždy se rovná `a` .
Například:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

Operace dělení velkých celých čísel a zbytků fungují stejným způsobem.

S ohledem na libovolný číselný výraz můžete vytvořit nový výraz pomocí `-` unárního operátoru.
Nový výraz je stejného typu jako výraz prvku.

S ohledem na libovolný celočíselný nebo velký celočíselný výraz můžete vytvořit nový výraz stejného typu pomocí `~~~` unárního operátoru (bitového doplňku).

## <a name="boolean-expressions"></a>Výrazy logických hodnot

Dvě `Bool` hodnoty literálu jsou `true` a `false` .

Vzhledem k jakýmkoliv dvěma výrazům stejného primitivního typu lze `==` `!=` použít binární operátory a k vytvoření `Bool` výrazu.
Výraz má hodnotu true, pokud jsou dva výrazy stejné a false, pokud ne.

Hodnoty uživatelsky definovaných typů nelze porovnat, lze porovnat pouze jejich nezabalené hodnoty. Například pomocí operátoru "Unwrap" `!` (popsaný v podrobnostech na [typech v Q #](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

Porovnání rovnosti pro `Qubit` hodnoty je rovnost identity; to znamená, zda dva výrazy identifikují stejný qubit.
Stavy těchto dvou qubits se neshodují, přistupovaly nebo nemění pomocí tohoto porovnání.

Porovnání rovnosti pro `Double` hodnoty může být zavádějící z důvodu zaoblení efektů.
Například, `49.0 * (1.0/49.0) != 1.0`.

Vzhledem k tomu, že jsou zadány dva číselné výrazy, binární operátory `>` , `<` , `>=` a lze `<=` použít k vytvoření nového logického výrazu, který je true, pokud je první výraz v tomto pořadí větší než, menší než nebo roven nebo menší nebo roven druhému výrazu.

U všech dvou logických výrazů použijte `and` binární operátor pro vytvoření nového logického výrazu, který je true, pokud jsou oba výrazy pravdivé. Podobně použití `or` operátoru vytvoří výraz, který má hodnotu true, pokud má jeden z obou výrazů hodnotu true.

S ohledem na logický výraz `not` může být unární operátor použit k vytvoření nového logického výrazu, který je true, pokud je výraz prvku false.

## <a name="string-expressions"></a>Řetězcové výrazy

Q # povoluje použití řetězců v `fail` příkazu (vysvětleno v [toku řízení](xref:microsoft.quantum.guide.controlflow#fail-statement)) a ve [`Message`](xref:microsoft.quantum.intrinsic.message) funkci Standard. Konkrétní chování druhé závisí na simulátoru, který se používá, ale obvykle zapisuje zprávu do hostitelské konzole při volání během programu Q #.

Řetězce v Q # jsou buď literály nebo interpolované řetězce.

Řetězcové literály jsou podobně jako jednoduché řetězcové literály ve většině jazyků: sekvence znaků Unicode uzavřených v uvozovkách `" "` .
V řetězci použijte znak zpětného lomítka `\` k úniku znaku dvojité uvozovky ( `\"` ) nebo k vložení nového řádku (), návratu na začátek řádku `\n` ( `\r` ) nebo tabulátoru ( `\t` ).
Například:

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a>Interpolované řetězce

Syntaxe Q # pro řetězcové interpolace je podmnožinou syntaxe jazyka C#. Níže jsou uvedené klíčové body, které se týkají Q #:

* Pro identifikaci řetězcového literálu jako interpolované řetězce, předřaďte ho `$` symbolem. Mezi znakem `$` a `"` , který začíná řetězcovým literálem, nesmí být mezera.

* Následuje základní příklad použití [`Message`](xref:microsoft.quantum.intrinsic.message) funkce k zápisu výsledku měření do konzoly spolu s dalšími výrazy Q #.

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* Libovolný platný výraz Q # se může objevit v interpolované řetězci.

* Výrazy uvnitř interpolované řetězce následují syntax Q #, nikoli syntaxe jazyka C#. Nejvýraznějším rozdílem je, že Q # nepodporuje doslovné (víceřádkové) interpolované řetězce.

Další podrobnosti o syntaxi jazyka C# naleznete v tématu [*interpolované řetězce*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).

## <a name="range-expressions"></a>Výrazy rozsahu

S ohledem `Int` na tři výrazy `start` , `step` , a `stop` , výraz `start .. step .. stop` je výraz rozsahu, jehož prvním prvkem je `start` , druhý prvek je, `start+step` třetí prvek je `start+step+step` a tak dále, dokud `stop` nepředáte.
Rozsah může být prázdný, pokud `step` je například kladný a `stop < start` .

Rozsah je zahrnut na obou koncích. To znamená, že pokud rozdíl mezi `start` a `stop` je celočíselný násobek `step` , bude poslední prvek rozsahu `stop` .

Při daných dvou `Int` výrazech `start` a `stop` výraz `start .. stop` je výraz rozsahu, který je roven `start .. 1 .. stop` .
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

Literál řazené kolekce členů je sekvence výrazů prvků příslušného typu oddělených čárkami, které jsou uzavřeny v závorkách.
Například `(1, One)` je `(Int, Result)` výraz.

Kromě literálů jsou jedinými výrazy řazené kolekce členů symboly, které jsou vázány na hodnoty řazené kolekce členů, prvky pole řazené kolekce členů a volání, která vrací řazené kolekce členů.

## <a name="user-defined-type-expressions"></a>Výrazy uživatelsky definovaného typu

Literál uživatelsky definovaného typu se skládá z názvu typu následovaného literálem řazené kolekce členů základního typu řazené kolekce členů typu.
Například pokud `IntPair` je uživatelem definovaný typ založený na `(Int, Int)` , pak `IntPair(2, 3)` je platný literál tohoto typu.

Kromě literálů jsou jedinými výrazy uživatelsky definovaného typu symboly, které jsou vázány na hodnoty daného typu, prvky pole polí daného typu a volání, která vrací tento typ.

## <a name="unwrap-expressions"></a>Rozbalit výrazy

V Q # se operátor rozbalení označuje jako koncová značka vykřičník `!` .
Například pokud `IntPair` je uživatelem definovaný typ s podkladovým typem `(Int, Int)` a `s` je proměnná s hodnotou `IntPair(2, 3)` , pak `s!` je `(2, 3)` .

Pro uživatelsky definované typy definované v jiných uživatelsky definovaných typech můžete zopakovat operátor rozbalení. Například `s!!` označuje zdvojnásobení nezabalenou hodnotu `s` .
Proto, pokud `WrappedPair` je uživatelem definovaný typ s podkladovým typem `IntPair` , a `t` je proměnná s hodnotou `WrappedPair(IntPair(1,2))` , pak `t!!` je `(1,2)` .

`!`Operátor má vyšší prioritu než všechny ostatní operátory, kromě `[]` indexace pole a řezů.
`!`a dá se `[]` vytvořit vazba. to znamená, že je `a[i]![3]` čten jako `((a[i])!)[3]` : Vezměte `i` element elementu `a` , rozbalíte ho a potom Získejte třetí prvek nezabalené hodnoty (který musí být pole).

Priorita `!` operátoru má jeden dopad, který nemusí být zřejmý.
Vrátí-li funkce nebo operace hodnotu, která je poté nezabalena, musí být volání funkce nebo operace uzavřena v závorkách, aby se argumenty řazené kolekce členů navázaly na volání, nikoli na rozbalení.
Například:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Výrazy Array

Literál pole je sekvence jednoho nebo více výrazů prvků oddělených čárkami, které jsou uzavřeny v hranatých závorkách `[]` .
Všechny elementy musí být kompatibilní se stejným typem.

Pokud jsou zadána dvě pole stejného typu, použijte binární `+` operátor pro vytvoření nového pole, které je zřetězením dvou polí.
Příklad: `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.

### <a name="array-creation"></a>Vytvoření pole

Pro zadání typu a `Int` výrazu použijte `new` operátor k přidělení nového pole dané velikosti.
Například `new Int[i + 1]` přidělí nové `Int` pole `i + 1` elementům.

Prázdné literály pole, například `[]` , nejsou povoleny.
Místo toho můžete vytvořit pole s nulovou délkou pomocí `new T[0]` , kde `T` je zástupný symbol pro vhodný typ.

Prvky nového pole se inicializují do výchozí hodnoty závislé na typu.
Ve většině případů se jedná o určitou variaci nula.

Pro qubits a volat, které jsou odkazy na entity, neexistuje přiměřená výchozí hodnota.
Proto pro tyto typy je výchozí hodnota neplatný odkaz, který nelze použít, aniž by došlo k chybě za běhu, podobně jako odkaz s hodnotou null v jazycích, jako je C# nebo Java.
Pole obsahující qubits nebo volat musí být inicializována s jinými než výchozími hodnotami, aby bylo možné jejich prvky bezpečně použít. Vhodné inicializační rutiny naleznete v tématu <xref:microsoft.quantum.arrays> .

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

Typy řazené kolekce členů inicializují element po prvku.


### <a name="array-elements"></a>Prvky pole

Pro výraz pole a `Int` výraz vytvořte nový výraz pomocí operátoru elementu pole `[]` .
Nový výraz je stejného typu jako typ prvku pole.
Například pokud `a` je svázán s polem typu `Double` , pak `a[4]` je `Double` výraz.

Pokud výraz pole není jednoduchý identifikátor, je nutné jej uzavřít do závorek pro výběr elementu.
Například pokud `a` a `b` jsou obě pole typu `Int` , je prvek z zřetězení vyjádřen jako:

```qsharp
(a + b)[13]
```

Všechna pole v Q # jsou založená na nule.
To znamená, že první prvek pole `a` je vždy `a[0]` .


### <a name="array-slices"></a>Řezy pole

Při zadání výrazu pole a `Range` výrazu se vytvoří nový výraz s použitím operátoru řezu array `[ ]` .
Nový výraz je stejného typu jako pole a obsahuje položky pole indexované prvky `Range` , v pořadí definovaném `Range` .
Například pokud `a` je svázán s polem typu `Double` , pak `a[3..-1..0]` je `Double[]` výraz, který obsahuje první čtyři prvky, `a` ale v obráceném pořadí, jak jsou uvedeny v `a` .

Pokud `Range` je hodnota prázdná, pak výsledný řez pole má nulovou délku.

Stejně jako u odkazů na prvky pole, pokud výraz pole není jednoduchý identifikátor, je nutné jej uzavřít do závorek a vytvořit jeho výřez.
Například pokud `a` a `b` jsou obě pole typu `Int` , řez z zřetězení je vyjádřen jako:

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a>Odvozené počáteční/koncové hodnoty

Od naší [verze 0,8](xref:microsoft.quantum.relnotes)podporujeme kontextové výrazy pro průřezy rozsahu. Konkrétně můžete vynechat počáteční a koncové hodnoty rozsahu v kontextu výrazu dělení rozsahu. V takovém případě kompilátor použije následující pravidla pro odvození zamýšlených oddělovačů pro rozsah:

* Pokud je hodnota *začátek* rozsahu vynechána, pak odvozená počáteční hodnota.
  * je nula, pokud není zadán žádný krok, nebo je zadaný krok kladný.  
  * je délka pole řezu minus jedna, pokud je zadaný krok záporný.

* Pokud je hodnota *konec* rozsahu vynechána, pak odvozená koncová hodnota
  * je délka pole řezu minus jedna, pokud není zadán žádný krok, nebo je zadaný krok kladný.
  * je nula, pokud je zadaný krok záporný.

Tady je několik příkladů:

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

Vzhledem k tomu, že všechny typy Q # jsou typy hodnot (s qubits, které pobírají trochu speciální role), tvoří kopii "kopie", když je hodnota vázána na symbol nebo když je symbol převázán. To znamená, že chování Q # je stejné jako při vytvoření kopie pomocí operátoru přiřazení. 

Samozřejmě jsou v praxi v případě potřeby znovu vytvořeny pouze příslušné součásti. To má vliv na to, jak kopírujete pole, protože není možné aktualizovat položky pole. Chcete-li upravit existující pole, je nutné využít mechanismus *kopírování a aktualizace* .

Můžete vytvořit nové pole z existujícího pole pomocí výrazů *kopírování a aktualizace* , které používají operátory `w/` a `<-` .
Výraz kopírování a aktualizace je výrazem formuláře `expression1 w/ expression2 <- expression3` , kde

* `expression1`musí být typu `T[]` pro nějaký typ `T` .
* `expression2`definuje, které indexy v poli určeném `expression1` pro úpravy mají být upraveny. `expression2`musí být buď Type, `Int` nebo type `Range` .
* `expression3`je hodnota, která se používá k aktualizaci prvků v `expression1` , v závislosti na indexech zadaných v `expression2` . Pokud `expression2` je typ `Int` , `expression3` musí být typ `T` . Pokud `expression2` je typ `Range` , `expression3` musí být typ `T[]` .

Například výraz kopírování a aktualizace `arr w/ idx <- value` vytvoří nové pole se všemi prvky nastavenými na odpovídající prvky v `arr` , s výjimkou prvků určených parametrem `idx` , který je nastaven na hodnotu (y) v `value` . 

Zadané `arr` pole obsahuje `[0,1,2,3]` , pak 

- `arr w/ 0 <- 10`je pole `[10,1,2,3]` .
- `arr w/ 2 <- 10`je pole `[0,1,10,3]` .
- `arr w/ 0..2..3 <- [10,12]`je pole `[10,1,12,3]` .

#### <a name="copy-and-update-expressions-for-named-items"></a>Výrazy kopírování a aktualizace pro pojmenované položky

Podobné výrazy existují pro pojmenované položky v uživatelsky definovaných typech. 

Zvažte například typ 

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

Můžete také vytvořit pole, které lze volat.

* Je-li běžný typ prvku typ operace nebo funkce, všechny prvky musí mít stejné vstupní a výstupní typy.
* Typ elementu pole podporuje všechny [funktory](xref:microsoft.quantum.guide.operationsfunctions) , které jsou podporovány všemi prvky.
Například pokud `Op1` , `Op2` a `Op3` všechny jsou `Qubit[] => Unit` operace, ale `Op1` podporují `Adjoint` , `Op2` podporují `Controlled` a `Op3` podporují obojí:
  * `[Op1, Op2]`je pole `(Qubit[] => Unit)` operací.
  * `[Op1, Op3]`je pole `(Qubit[] => Unit is Adj)` operací.
  * `[Op2, Op3]`je pole `(Qubit[] => Unit is Ctl)` operací.

Nicméně zatímco operace `(Qubit[] => Unit is Adj)` a `(Qubit[] => Unit is Ctl)` mají společný základní typ `(Qubit[] => Unit)` , *pole* těchto operací nesdílejí společný základní typ.

Například `[[Op1], [Op2]]` by aktuálně vyvolala chybu, protože se pokusí vytvořit pole dvou nekompatibilních typů polí `(Qubit[] => Unit is Adj)[]` a `(Qubit[] => Unit is Ctl)[]` .

Další informace o tom, jak volat, najdete v tématu věnovaném vydaným [výrazům](#callable-expressions) na této stránce nebo [operacích a funkcích v Q #](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="conditional-expressions"></a>Podmíněné výrazy

Vzhledem k dvěma výrazům stejného typu a logickému výrazu tvoří podmíněný výraz pomocí otazníku, `?` a svislého panelu `|` . Je `a==b ? c | d` -li zadána hodnota podmíněného výrazu, má hodnotu `c` true a je-li hodnota `a==b` `d` false.

### <a name="conditional-expressions-with-callables"></a>Podmíněné výrazy s volat

Podmíněné výrazy mohou být vyhodnoceny na operace, které mají stejné vstupy a výstupy, ale podporují různé funktory. V tomto případě typ podmíněného výrazu je operace se vstupy a výstupy, které podporují libovolný funktory podporovaný oběma výrazy.
Například pokud `Op1` , `Op2` a `Op3` jsou všechny `Qubit[]=>Unit` , ale `Op1` podporují `Adjoint` , `Op2` podporují `Controlled` a `Op3` podporují obojí:

- `flag ? Op1 | Op2`je `(Qubit[] => Unit)` operace.
- `flag ? Op1 | Op3`je `(Qubit[] => Unit is Adj)` operace.
- `flag ? Op2 | Op3`je `(Qubit[] => Unit is Ctl)` operace.

Pokud jeden ze dvou možných výsledných výrazů zahrnuje volání funkce nebo operace, provede toto volání pouze v případě, že je tento výsledek ten, který je hodnotou volání. Například `a==b ? C(qs) | D(qs)` Pokud `a==b` má hodnotu true, `C` je vyvolána operace, a pokud je hodnota false, bude `D` vyvolána pouze operace. Tento přístup je podobný jako u *krátkých okruhů* v jiných jazycích.

## <a name="callable-expressions"></a>Výrazy, které se mají volat

Volatelné literály je název operace nebo funkce definované v oboru kompilace. Například `X` je literál operace, který odkazuje na standardní `X` operace knihovny a `Message` je literál funkce, který odkazuje na standardní `Message` funkci knihovny.

Pokud operace podporuje `Adjoint` funktor, pak `Adjoint op` je výraz operace.
Podobně platí, že pokud operace podporuje `Controlled` funktor, pak `Controlled op` je výraz operace.
Další informace o typech těchto výrazů naleznete v tématu [specializace operací volání](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).

Funktory ( `Adjoint` a `Controlled` ) sváže více než všechny ostatní operátory, s výjimkou operátoru Unwrap `!` a pole s indexem `[ ]` .
Následující všechny jsou tedy platné, za předpokladu, že operace podporují funktory použité:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a>Výrazy s parametry, které je typu volat

Můžete použít literál, který lze volat jako hodnotu, například pro přiřazení k proměnné nebo předání na jinou možnost, která se dá volat. V takovém případě, pokud je možné volat [parametry typu](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), je nutné zadat parametry jako součást hodnoty, kterou lze volat.

Hodnota, která se nedá volat, nemůže mít nespecifikované parametry typu. Například pokud `Fun` je funkce s podpisem `'T1->Unit` :

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Volat výrazy vyvolání

Vzhledem k výrazu, který je možné volat (operace nebo funkce) a výrazu řazené kolekce členů vstupního typu signatury, můžete vytvořit *výraz volání* připojením výrazu řazené kolekce členů k výrazu, který je k volání.
Typ výrazu vyvolání je výstupní typ signatury, kterou chcete volat.

Například pokud `Op` je operace s podpisem `((Int, Qubit) => Double)` , `Op(3, qubit1)` je výraz typu `Double` .
Podobně, pokud `Sin` je funkce s signaturou `(Double -> Double)` , `Sin(0.1)` je výraz typu `Double` .
Nakonec, pokud `Builder` je funkce s signaturou `(Int -> (Int -> Int))` , pak `Builder(3)` je funkce z `Int` na `Int` .

Vyvolání výsledku výrazu s možností volání vyžaduje navíc pár závorek kolem volání.
Proto pokud chcete vyvolat výsledek volání `Builder` z předchozího odstavce, správná syntaxe je:

```qsharp
(Builder(3))(2)
```

Při vyvolání [typu](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) , který je možné volat, můžete zadat skutečné parametry typu v rámci lomených závorek `< >` po volání.
Tato akce je obvykle zbytečná, protože kompilátor Q # odvodí skutečné typy.
Nicméně *je* vyžadován pro [částečnou aplikaci](xref:microsoft.quantum.guide.operationsfunctions#partial-application) , pokud je argument typu bez parametrů ponechán neurčen.
To je užitečné také při předávání operací s různými funktory, které jsou schopné volat.

Například pokud `Func` má signatura `('T1, 'T2, 'T1) -> 'T2` a má signaturu `Op1` `Op2` `(Qubit[] => Unit is Adj)` a `Op3` má signaturu, `(Qubit[] => Unit)` pro vyvolání `Func` `Op1` jako první argument jako `Op2` druhý a `Op3` jako třetí:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

Specifikace typu je povinná `Op3` , protože a `Op1` má jiné typy, takže kompilátor bude považovat za dvojznačný bez specifikace.


## <a name="operator-precedence"></a>Priorita operátorů

* Všechny binární operátory jsou asociativní zprava, s výjimkou `^` .

* Hranaté závorky, `[ ]` pro průřezy a indexování polí vytvořte vazby před libovolným operátorem.

* Funktory `Adjoint` a `Controlled` BIND po vyřazení pole, ale před všemi ostatními operátory.

* Kulaté závorky pro operace a volání funkce se také vážou před libovolným operátorem, ale po vyřazení a funktory pole.

Operátory Q # v pořadí podle priority, od nejvyšší po nejnižší:

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
`w/` `<-` | Ternární | Kopírování a aktualizace | Viz [výrazy pro kopírování a aktualizaci](#copy-and-update-expressions)

## <a name="next-steps"></a>Další kroky

Teď, když můžete pracovat s výrazy v Q #, přejít k [operacím a funkcím v q #](xref:microsoft.quantum.guide.operationsfunctions) a zjistit, jak definovat a volat operace a funkce.
