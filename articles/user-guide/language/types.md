---
title: 'Typy v Q #'
description: 'Seznamte se s různými typy použitými v programovacím jazyce Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: 58370193bd62e306197a9e07c28f8611f043e55c
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431134"
---
# <a name="types-in-q"></a>Typy v Q #

Tato stránka obsahuje model typu Q # a popisuje syntaxi pro zadání a práci s typy.
Na další stránce [Zadejte výrazy](xref:microsoft.quantum.guide.expressions), podrobnosti o tom, jak vytvořit a pracovat na výrazech těchto typů.

Upozorňujeme, že Q # je jazyk *silného typu* , takže pečlivé používání těchto typů může kompilátoru přispět, aby poskytovalo silné záruky na programy Q # v době kompilace.
Aby bylo možné zajistit nejpřísnější záruky, převody mezi typy v Q # musí být explicitní pomocí volání funkcí, které tento převod vyjadřují. Celá řada takových funkcí je k dispozici jako součást <xref:microsoft.quantum.convert> oboru názvů.
Přetypování na kompatibilní typy na druhé straně se implicitně stane. 

Q # poskytuje jak primitivní typy, které lze použít přímo, a různé způsoby, jak vytvořit nové typy z jiných typů.
Popíšeme všechny ve zbývající části tohoto oddílu.

## <a name="primitive-types"></a>Primitivní typy

Jazyk Q # poskytuje několik *primitivních typů*, ze kterých lze sestavit další typy:

- `Int`Typ představuje 64 celé číslo se znaménkem, např.: `2` , `107` , `-5` .
- `BigInt`Typ představuje celé číslo se znaménkem libovolné velikosti, např. `2L` , `107L` , `-5L` .
   Tento typ je založený na rozhraní .NET.<xref:System.Numerics.BigInteger>
   textový.
- `Double`Typ představuje číslo s plovoucí desetinnou čárkou s dvojitou přesností, například: `0.0` , `-1.3` , `4e-7` .
- `Bool`Typ představuje logickou hodnotu, která může být buď `true` nebo `false` .
- `Range`Typ představuje sekvenci celých čísel, která je označena jako `start..step..stop` , kde označuje krok s možnostmi. 
   To `start .. stop` odpovídá `start..1..stop` , a například `1..2..7` představuje sekvenci $ \{ 1, 3, 5, 7 \} $.
- `String`Typ je posloupnost znaků Unicode, která je po vytvoření uživatelem neprůhledná.
  Tento typ slouží k hlášení zpráv na klasického hostitele v případě chyby nebo diagnostické události.
- `Unit`Typ je typ, který povoluje pouze jednu hodnotu `()` . 
  Tento typ slouží k označení, že funkce Q # nebo operace nevrátí žádné informace. 
- `Qubit`Typ představuje bit s podmnožinou nebo qubit.
   `Qubit`s jsou neprůhlední pro uživatele; jedinou operací, která je k dispozici, je kromě jejich předání jiné operaci testovat identitu (rovnost).
   V konečném případě `Qubit` jsou akce u s implementovány voláním vnitřních instrukcí na procesor nebo na základě jeho simulace.
- `Pauli`Typ představuje jednu ze čtyř operátorů Pauli s jedním qubit.
   Tento typ slouží k označení základní operace pro rotace a určení pozorovatele, které se měří.
   Toto je výčtový typ, který má čtyři možné hodnoty: `PauliI` , `PauliX` , `PauliY` a `PauliZ` , což jsou konstanty typu `Pauli` .
- `Result`Typ představuje výsledek měření.
   Toto je výčtový typ se dvěma možnými hodnotami: `One` a `Zero` , což jsou konstanty typu `Result` .
   `Zero`indikuje, že došlo k měření + 1 eigenvalue. `One`označuje eigenvalue-1.

Konstanty,,,,,, `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` a `Zero` jsou všechny rezervované symboly v Q #.

## <a name="array-types"></a>Typy polí

Vzhledem k platnému typu Q # `'T` existuje typ, který představuje pole hodnot typu `'T` .
Tento typ pole je reprezentován jako, `'T[]` například `Qubit[]` nebo `Int[][]` .
Například kolekce celých čísel je označena `Int[]` , zatímco pole `(Bool, Pauli)` hodnot pole je označeno `(Bool, Pauli)[][]` .

V druhém příkladu si všimněte, že představuje potenciálně vícenásobné pole polí a ne obdélníkové dvourozměrné pole.
Q # neposkytuje podporu pro pravoúhlá pole s multidimenzionálními hodnotami.

Hodnota pole může být napsána ve zdrojovém kódu Q # pomocí hranatých závorek kolem prvků pole, jako v `[PauliI, PauliX, PauliY, PauliZ]` .
Typ literálu pole je určen běžným základním typem všech položek v poli. 

> [!WARNING]
> Po vytvoření pole nelze prvky pole změnit.
> K vytvoření upraveného pole lze použít [Příkazy Update a Reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) a [výrazy Copy a Update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) .

Alternativně lze pole vytvořit z jeho velikosti pomocí `new` klíčového slova:

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

V obou případech lze po sestavení pole použít základní funkci `Length` k získání počtu prvků jako `Int` .
Pole lze podskriptovat pomocí hranatých závorek s podscripty typu `Int` nebo typu `Range` , aby získaly buď jednotlivé prvky, nebo nová pole obsahující podmnožinu prvků pole.
Dolní indexy polí jsou počítány od nuly:

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>Typy řazené kolekce členů

Vzhledem k nule nebo více různým typům, `T0` `T1` ,..., `Tn` můžeme jako *typ zadat nový typ řazené kolekce členů* `(T0, T1, ..., Tn)` .
Typy použité k vytvoření nového typu řazené kolekce členů mohou být řazené kolekce členů, jako v `(Int, (Qubit, Qubit))` .
Takové vnořování je vždy omezené, ale v případě, že typy řazené kolekce členů nemůžou za žádných okolností obsahovat samy sebe.

Hodnoty nového typu řazené kolekce členů jsou řazené kolekce členů vytvořené pomocí sekvencí hodnot z každého typu v řazené kolekci členů.
Například `(3, false)` je řazená kolekce členů, jejíž typ je typ řazené kolekce členů `(Int, Bool)` .
Je možné vytvořit pole řazených kolekcí členů, řazené kolekce členů, řazené kolekce členů, atd.

Od Q # 0,3 `Unit` je název *typu* prázdné řazené kolekce členů; `()` používá se pro prázdnou *hodnotu*řazené kolekce členů.

Instance řazené kolekce členů jsou neměnné.
Q # neposkytuje mechanismus pro změnu obsahu řazené kolekce členů po vytvoření.

Řazené kolekce členů jsou účinným konceptem použitým v rámci Q # ke shromáždění hodnot dohromady do jedné hodnoty, což usnadňuje jejich předání.
Konkrétně při použití notace řazené kolekce členů můžeme vyjádřit, že každá operace a možnost volat přebírá přesně jeden vstup a vrátí přesně jeden výstup.

### <a name="singleton-tuple-equivalence"></a>Rovnost řazené kolekce členů singleton

Je možné vytvořit singleton (jeden prvek) řazené kolekce členů, `('T1)` například `(5)` nebo `([1,2,3])` .
Otázka č. Q však považuje typ Tuple typu Singleton za úplný ekvivalent hodnoty uzavřeného typu.
To znamená, že neexistuje žádný rozdíl mezi `5` a `(5)` , ani mezi `5` a `(((5)))` , ani mezi `(5, (6))` a `(5, 6)` .
Je stejně platná pro zápis `(5)+3` jako k zápisu `5+3` a oba výrazy budou vyhodnoceny `8` .

Tato rovnocennost se vztahuje na všechny účely, včetně přiřazení a výrazů.
V případě libovolného výrazu je stejný výraz uzavřený v závorkách výraz stejného typu.
Například `(7)` výraz je výraz `Int` , `([1,2,3])` je výraz typu array `Int` s a `((1,2))` je výraz s typem `(Int, Int)` .

Konkrétně to znamená, že operace nebo funkce, jejíž vstupní řazená kolekce členů nebo výstupní řazená kolekce členů má jedno pole, může být považována za jeden argument nebo vrací jedinou hodnotu.

Tato vlastnost odkazuje jako na _rovnost v řazené kolekci členů typu Singleton_.


## <a name="user-defined-types"></a>Uživatelsky definované typy

Uživatelsky definovaná deklarace typu se skládá z klíčového slova `newtype` , následované názvem uživatelsky definovaného typu, a `=` platnou specifikací typu a ukončující středník.

Příklad:

```qsharp
newtype PairOfInts = (Int, Int);
```

Každý zdrojový soubor Q # může deklarovat libovolný počet uživatelsky definovaných typů.
Názvy typů musí být v rámci oboru názvů jedinečné a nemusí být v konfliktu s názvy operací a funkcí.

Uživatelsky definované typy jsou odlišné, i když základní typy jsou identické.
Konkrétně neexistuje žádný automatický převod mezi hodnotami dvou uživatelsky definovaných typů i v případě, že jsou základní typy identické.

### <a name="named-vs-anonymous-items"></a>Pojmenované vs. anonymní položky

Soubor Q # může definovat nový pojmenovaný typ obsahující jednu hodnotu jakéhokoli právního typu.
Pro libovolný typ řazené kolekce členů `T` můžeme deklarovat nový uživatelsky definovaný typ, který je podtypem `T` s `newtype` příkazem.
V @"microsoft.quantum.math" oboru názvů je například komplexní čísla definována jako uživatelsky definovaný typ:

```qsharp
newtype Complex = (Double, Double);
```
Tento příkaz vytvoří nový typ se dvěma anonymními položkami typu `Double` .   

Kromě anonymních položek podporuje uživatelsky definované typy také *pojmenované položky* jako Q # verze 0,7 nebo vyšší. Například můžeme mít název k položkám `Re` pro dvojitou hodnotu představující reálnou část komplexního čísla a `Im` pro imaginární část: 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Pojmenování jedné položky v uživatelsky definovaném typu neznamená, že všechny položky musí být pojmenovány – podporuje se libovolná kombinace pojmenovaných a nepojmenovaných položek. Kromě toho mohou být také pojmenovány vnitřní položky.
Typ `Nested` definovaný níže pro příklad má základní typ `(Double, (Int, String))` , z nějž `Int` je pojmenována pouze položka typu a všechny ostatní položky jsou anonymní. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

Pojmenované položky mají výhodu, ke kterým lze přistupovat přímo prostřednictvím *operátoru přístupu* `::` . 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

Kromě poskytování krátkých aliasů pro potenciálně složité typy řazené kolekce členů, což je jedna významná výhoda pro definování takových typů, je, že mohou zdokumentovat záměr konkrétní hodnoty.
Návrat do příkladu `Complex` , jeden mohl také definovat 2D polární souřadnice jako uživatelsky definovaný typ:

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

I když oba i mají `Complex` `Polar` základní typ `(Double, Double)` , jsou tyto dva typy zcela nekompatibilní v Q # a minimalizují riziko náhodného volání komplexní matematické funkce s polárními souřadnicemi a naopak.
Tímto způsobem mají uživatelsky definované typy podobnou roli jako záznamy v F # například. 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>Přístup k anonymním položkám pomocí operátoru rozbalení

Aby bylo možné přistupovat k anonymním položkám na druhé straně, je třeba zabalenou hodnotu nejprve extrahovat pomocí operátoru přípony `!` .
Operátor "Unwrap" `!` umožňuje extrahovat hodnotu obsaženou v uživatelsky definovaném typu.
Typ takového výrazu "Unwrap" je základní typ uživatelsky definovaného typu. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

Operátor rozbalení rozbalí právě jednu vrstvu obtékání.
Pro přístup k hodnotě zabalené na násobení lze použít více operátorů rozbalení.

Například:

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

Další podrobnosti o operátoru rozbalení lze nalézt ve [výrazech typu v Q #](xref:microsoft.quantum.guide.expressions).

### <a name="creating-values-of-user-defined-types"></a>Vytváření hodnot uživatelsky definovaných typů

Hodnoty uživatelsky definovaného typu lze vytvořit voláním odpovídajícího konstruktoru typu:

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Případně můžete nové hodnoty vytvořit z existujících pomocí [výrazů kopírování a aktualizace](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions). Podobně jako u polí tyto výrazy kopírují všechny hodnoty položky původního výrazu s výjimkou zadaných pojmenovaných položek. Pro tyto hodnoty jsou nastaveny na ty definované na pravé straně výrazu. Jakékoli jiné jazykové konstrukce, například [Příkazy Update-a-Reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), které jsou k dispozici pro položky pole existují také pro pojmenované položky v uživatelsky definovaných typech.

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

Uživatelsky definované typy lze použít kdekoli v jakémkoli jiném typu.
Konkrétně je možné definovat pole uživatelsky definovaného typu a zahrnout uživatelsky definovaný typ jako prvek typu řazené kolekce členů.

Poznámka: nemůžete vytvořit struktury rekurzivního typu.
To znamená, že typ, který definuje uživatelsky definovaný typ, nemůže být typ řazené kolekce členů, který obsahuje prvek uživatelsky definovaného typu.
Obecněji, uživatelsky definované typy nemůžou mít na sobě navzájem cyklické závislosti, takže následující sada definic typu by mohla být neplatná:

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a>Typy operací a funkcí

Základní typ pro všechny volat lze zapsat jako `('Tinput => 'Tresult)` nebo `('Tinput -> 'Tresult)` , kde `'Tinput` a `'Tresult` jsou typy.
Nazývají se *signatury* , které lze volat.

Všechny volat pomocí Q # se považují za vstupní hodnotu a jako výstup vrátí jedinou hodnotu.
Vstupní i výstupní hodnoty mohou být řazené kolekce členů.
Je k dispozici bez výsledku vrácení `Unit` .
Volat, které nemají žádný vstup, přebírají jako vstup prázdnou řazenou kolekci členů.

> [!NOTE]
> První formulář s, se `=>` používá pro operace, druhý formulář, with `->` , for Functions.
> Například `((Qubit, Pauli) => Result)` představuje signaturu pro možnou operaci měření s jedním qubit.
Typy *funkcí* jsou zcela určeny jejich signaturou.
Například funkce, která vypočítá sinus úhlu, by měla typ `(Double -> Double)` .

*Operations*---, ale funkce not---mají určité další vlastnosti, které se vyjadřují jako součást typu operace. Tyto vlastnosti zahrnují informace o tom, co *funktory* operace podporuje.
Například pokud provádění operace může být podmíněně na stav jiného qubits, měla by podporovat `Controlled` funktor; Pokud má operace hodnotu INVERT, měla by podporovat `Adjoint` funktor. Funktory a operace jsou podrobněji popsány v tématu [operace a funkce v Q #](xref:microsoft.quantum.guide.operationsfunctions), ale v této části jednoduše probereme, jak tato změna signatura operace mění.

Aby `Controlled` bylo nutné v typu operace vyžadovat podporu pro a/nebo `Adjoint` funktor, musíme přidat poznámku indikující odpovídající vlastnosti.
Anotace `is Ctl` (např. `(Qubit => Unit is Ctl)` ) indikuje, že operace je ovladatelné---to znamená, že je vykonávání stavu jiného qubit nebo qubits. Podobně `is Adj` označuje, že operace má sousední, nebo jednoduše, může být "obrácená" tak, že se po sobě provede operace, a potom její sousední vztah do stavu opustí stav beze změny. 

Pokud chceme vyžadovat, aby operace tohoto typu podporovala i `Adjoint` `Controlled` funktor, můžeme to vyjádřit jako `(Qubit => Unit is Adj + Ctl)` . Například integrovaná <xref:microsoft.quantum.intrinsic.x> operace Pauli je typu `(Qubit => Unit is Adj + Ctl)` . 

Typ operace, který nepodporuje žádné funktory, je určen samotným typem vstupu a výstupu bez další poznámky.

### <a name="type-parameterized-functions-and-operations"></a>Typ – parametrizované funkce a operace

Typy, které lze volat, mohou obsahovat parametry typu.
Parametry typu jsou označeny symbolem, který je předponou jedné uvozovky. Například je platným `'A` parametrem typu.
Podrobnosti o definování typu, který lze volat, jsou k dispozici na stránce [operace a funkce v Q #](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) .

Parametr typu se může v jednom podpisu objevit více než jednou.
Například funkce, která použije jinou funkci na každý prvek pole a vrátí shromážděné výsledky, by měly signaturu `(('A[], 'A->'A) -> 'A[])` .
Podobně funkce, která vrací složení dvou operací, může mít signaturu `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .

Při vyvolání volání typu s parametrem typu musí být všechny argumenty, které mají stejný parametr typu, stejného typu.

Q # neposkytuje mechanismus pro omezení možných typů, které mohou být nahrazeny parametrem typu.

## <a name="whats-next"></a>A co dál?
Teď, když jste viděli všechny typy, které tvoří jazyk Q #, můžete přejít na [typ výrazy v Q #](xref:microsoft.quantum.guide.expressions) a podívat se, jak vytvořit a manipulovat s výrazy těchto různých typů.


