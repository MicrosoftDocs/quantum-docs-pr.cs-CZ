---
title: Typy v Q#
description: 'Seznamte se s různými typy použitými v programovacím jazyce Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: e37ce6e3a2dfad5395cdecf06178d64ec51b79f1
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415280"
---
# <a name="types-in-q"></a>Typy v Q#

Tento článek popisuje model typu Q # a syntaxi pro zadání a práci s typy. Podrobnosti o tom, jak vytvořit a pracovat na výrazech těchto typů, naleznete v tématu [Expression Types](xref:microsoft.quantum.guide.expressions).

Upozorňujeme, že Q # je jazyk *silného typu* , takže pečlivé používání těchto typů může kompilátoru přispět, aby poskytovalo silné záruky na programy Q # v době kompilace.
Aby bylo možné zajistit nejpřísnější záruky, převody mezi typy v Q # musí být explicitní pomocí volání funkcí, které tento převod vyjadřují. Q # poskytuje celou řadu takových funkcí jako součást <xref:microsoft.quantum.convert> oboru názvů.
Přetypování na kompatibilní typy se na druhé straně provede implicitně. 

Q # poskytuje oba primitivní typy, které se používají přímo, a různé způsoby, jak vytvořit nové typy z jiných typů.
Každý ve zbývající části tohoto článku popisujeme.

## <a name="primitive-types"></a>Primitivní typy

Jazyk Q # poskytuje následující *primitivní typy*, které lze použít přímo v programech q #. Tyto primitivní typy lze také použít k vytvoření nových typů.

- `Int`Typ představuje 64 celé číslo se znaménkem, například `2` ,, `107` `-5` .
- `BigInt`Typ představuje celé číslo se znaménkem libovolné velikosti, například,, `2L` `107L` `-5L` .
   Tento typ je založený na rozhraní .NET.<xref:System.Numerics.BigInteger>
   textový.

- `Double`Typ představuje číslo s plovoucí desetinnou čárkou s dvojitou přesností, například,, `0.0` `-1.3` `4e-7` .
- `Bool`Typ představuje logickou hodnotu buď `true` nebo `false` .
- `Range`Typ představuje sekvenci celých čísel, označených jako `start..step..stop` , kde označuje, že krok je nepovinný. 
   Například `start .. stop` odpovídá `start..1..stop` a `1..2..7` představuje sekvenci $ \{ 1, 3, 5, 7 \} $.
- `String`Typ je posloupnost znaků Unicode, která je po vytvoření uživatelem neprůhledná.
  Použijte `string` typ k hlášení zpráv pro klasického hostitele v případě chyby nebo diagnostické události.
- `Unit`Typ může mít pouze jednu hodnotu, `()` . 
  Tento typ použijte k označení, že funkce Q # nebo operace nevrátí žádné informace. 
- `Qubit`Typ představuje bit s podmnožinou nebo qubit.
   `Qubit`s jsou neprůhlední pro uživatele. Jedinou operací, která je k dispozici, je kromě jejich předání jiné operaci testovat identitu (rovnost).
   Nakonec implementujete akce v `Qubit` s voláním vnitřních pokynů na procesor s procesorem (nebo simulátorem pro plnění).
- `Pauli`Typ představuje jednu ze čtyř operátorů Pauli s jedním qubit.
   Tento typ použijte k označení základní operace pro otočení a určení pozorovatele, který se má měřit.
   Jedná se o Výčtový typ, který má čtyři možné hodnoty: `PauliI` , `PauliX` , `PauliY` a `PauliZ` , což jsou konstanty typu `Pauli` .
- `Result`Typ představuje výsledek měření.
   Jedná se o Výčtový typ se dvěma možnými hodnotami: `One` a `Zero` , což jsou konstanty typu `Result` .
   `Zero`indikuje, že došlo k měření + 1 eigenvalue. `One`indikuje, že byl změřen eigenvalue-1.

Konstanty,,,,,, `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` a `Zero` jsou všechny rezervované symboly v Q #.

## <a name="array-types"></a>Typy polí

* Pro libovolný platný typ Q # existuje typ, který představuje pole hodnot daného typu.
    Například `Qubit[]` a `(Bool, Pauli)[]` představuje pole `Qubit` hodnot a `(Bool, Pauli)` hodnot řazené kolekce členů.

* Pole polí je také platné. Rozbalení v předchozím příkladu, pole `(Bool, Pauli)` polí je označeno `(Bool, Pauli)[][]` .

> [!NOTE] 
> V tomto příkladu `(Bool, Pauli)[][]` představuje potenciálně vícenásobné pole polí a ne obdélníkové dvourozměrné pole. Q # nepodporuje obdélníková multidimenzionální pole.

* Hodnota pole může být napsána ve zdrojovém kódu Q # pomocí hranatých závorek kolem prvků pole, jako v `[PauliI, PauliX, PauliY, PauliZ]` .
Běžný základní typ všech položek v poli určuje typ literálu pole. Proto Sestavte pole s prvky, které nemají žádný společný základní typ, vyvolá chybu.  
Příklad naleznete v tématu [pole volat](xref:microsoft.quantum.guide.expressions#arrays-of-callables).

    > [!WARNING]
    > Po vytvoření nelze prvky pole změnit.
    > K vytvoření upraveného pole použijte [Příkazy Update-and-Reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) nebo [copy-and-Update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).

* Alternativně lze pole vytvořit z jeho velikosti pomocí `new` klíčového slova:

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* Použijte základní funkci `Length` k získání počtu prvků z pole jako `Int` .
* Pole mohou být zastaralá, aby získala buď jednotlivé prvky, nebo nová pole obsahující podmnožinu prvků pole.
Dolní indexy polí jsou založené na nule a musí být typu `Int` nebo typu `Range` :

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a>Typy řazené kolekce členů

Řazené kolekce členů jsou účinným konceptem použitým v rámci Q # ke shromáždění hodnot dohromady do jedné hodnoty, což usnadňuje jejich předání.
Zejména pomocí zápisu řazené kolekce členů můžete vyjádřit, že každá operace a možnost volat přebírá přesně jeden vstup a vrátí přesně jeden výstup.

* Předanému nule nebo více různým typům, `T0` `T1` ,..., `Tn` můžete odznačte nový *typ řazené kolekce členů* jako `(T0, T1, ..., Tn)` .
Typy použité k vytvoření nového typu řazené kolekce členů mohou být řazené kolekce členů, jako v `(Int, (Qubit, Qubit))` .
Takové vnořování je vždy omezené, ale v případě, že typy řazené kolekce členů nemůžou za žádných okolností obsahovat samy sebe.

* Hodnoty nového typu řazené kolekce členů jsou řazené kolekce členů vytvořené pomocí sekvencí hodnot z každého typu v řazené kolekci členů.
Například `(3, false)` je řazená kolekce členů, jejíž typ je typ řazené kolekce členů `(Int, Bool)` .
Je možné vytvořit pole řazených kolekcí členů, řazené kolekce členů polí, řazené kolekce členů a tak dále.

* Od Q # 0,3 `Unit` je název *typu* prázdné řazené kolekce členů; `()` používá se pro *hodnotu* prázdné řazené kolekce členů.

* Instance řazené kolekce členů jsou neměnné.
Q # neposkytuje mechanismus pro změnu obsahu řazené kolekce členů po vytvoření.



### <a name="singleton-tuple-equivalence"></a>Rovnost řazené kolekce členů singleton

Je možné vytvořit singleton (jeden prvek) řazené kolekce členů `('T1)` , například `(5)` nebo `([1,2,3])` .
Q # však považuje typ Tuple typu Singleton za ekvivalent hodnoty uzavřeného typu.
To znamená, že neexistuje žádný rozdíl mezi `5` a `(5)` , ani mezi `5` a `(((5)))` , ani mezi `(5, (6))` a `(5, 6)` .
Je stejně platná pro zápis, `(5)+3` protože je možné zapisovat. `5+3` oba výrazy jsou vyhodnoceny `8` .

Tato rovnocennost se vztahuje na všechny účely, včetně přiřazení a výrazů.
V případě libovolného výrazu je stejný výraz uzavřený v závorkách výraz stejného typu.
Například `(7)` je výraz typu `Int` , `([1,2,3])` je výraz typu `Int[]` a `((1,2))` je výraz typu `(Int, Int)` .

Konkrétně to znamená, že můžete zobrazit operaci nebo funkci, jejíž typ řazené kolekce členů nebo výstupní řazené kolekce členů má jedno pole jako přebírání jednoho argumentu nebo vrácení jedné hodnoty.

Tato vlastnost odkazuje jako na _rovnost v řazené kolekci členů typu Singleton_.


## <a name="user-defined-types"></a>Uživatelsky definované typy

Uživatelsky definovaná deklarace typu se skládá z klíčového slova `newtype` , následované názvem uživatelsky definovaného typu, a `=` platnou specifikací typu a ukončující středník.

Například:

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* Každý zdrojový soubor Q # může deklarovat libovolný počet uživatelsky definovaných typů.
* Názvy typů musí být v rámci oboru názvů jedinečné a nemusí být v konfliktu s názvy operací a funkcí.
* Uživatelsky definované typy jsou odlišné, i když základní typy jsou identické.
Konkrétně neexistuje žádný automatický převod mezi hodnotami dvou uživatelsky definovaných typů, a to i v případě, že jsou základní typy identické.

### <a name="named-vs-anonymous-items"></a>Pojmenované vs. anonymní položky

Soubor Q # může definovat nový pojmenovaný typ obsahující jednu hodnotu jakéhokoli právního typu.
Pro libovolný typ řazené kolekce členů `T` můžete deklarovat nový uživatelsky definovaný typ, který je podtypem `T` s `newtype` příkazem.
V @"microsoft.quantum.math" oboru názvů jsou například komplexní čísla definovány jako uživatelsky definovaný typ:

```qsharp
newtype Complex = (Double, Double);
```
Tento příkaz vytvoří nový typ se dvěma anonymními položkami typu `Double` .   

Kromě anonymních položek podporuje uživatelsky definované typy také *pojmenované položky* jako Q # verze 0,7 nebo vyšší. Například můžete pojmenovat položky `Re` pro dvojitou hodnotu představující reálnou část komplexního čísla a `Im` pro imaginární část: 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Pojmenování jedné položky v uživatelsky definovaném typu neznamená, že všechny položky musí být pojmenovány – podporuje se libovolná kombinace pojmenovaných a nepojmenovaných položek. Kromě toho mohou být také pojmenovány vnitřní položky.
Typ `Nested` , jak je definován níže, má například nadřízený typ `(Double, (Int, String))` , který `Int` je pojmenován pouze položka typu a všechny ostatní položky jsou anonymní. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

Pojmenované položky mají výhodu, ke kterým lze přistupovat přímo prostřednictvím *operátoru přístupu* `::` . 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

Kromě poskytování krátkých aliasů pro potenciálně složité typy řazené kolekce členů, což je významná výhoda definování takových typů, je, že mohou zdokumentovat záměr konkrétní hodnoty.
Návrat do příkladu `Complex` , jeden mohl také definovat 2D polární souřadnice jako uživatelsky definovaný typ:

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

I když oba `Complex` i `Polar` oba mají základní typ `(Double, Double)` , jsou tyto dva typy zcela nekompatibilní v Q # a minimalizují riziko náhodného volání komplexní matematické funkce s polárními souřadnicemi a naopak.

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>Přístup k anonymním položkám pomocí operátoru rozbalení

Pro přístup k anonymním položkám nejprve extrahuje zabalenou hodnotu pomocí operátoru přípony `!` .
Pomocí operátoru "Unwrap" `!` můžete extrahovat hodnotu obsaženou v uživatelsky definovaném typu.
Typ takového výrazu "Unwrap" je základní typ uživatelsky definovaného typu. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

Jeden operátor rozbalení rozbalí jednu vrstvu obtékání. Pro přístup k hodnotě zabalené v násobení použijte více operátorů rozbalení.

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

Další informace o operátoru rozbalení naleznete v tématu [Expression Types in Q #](xref:microsoft.quantum.guide.expressions).

### <a name="creating-values-of-user-defined-types"></a>Vytváření hodnot uživatelsky definovaných typů

Vytvořte hodnoty uživatelsky definovaného typu voláním odpovídajícího konstruktoru typu:

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Alternativně můžete vytvořit nové hodnoty z existujících pomocí [výrazů kopírování a aktualizace](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions). Stejně jako u polí, výrazy kopírování a aktualizace kopírují všechny hodnoty položky původního výrazu, s výjimkou zadaných pojmenovaných položek. Pro tyto výjimky jsou hodnoty těchto položek hodnotami definované na pravé straně výrazu. Jakékoli jiné jazykové konstrukce, které jsou k dispozici pro položky pole, například [Příkazy Update-a-Reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), existují také pro pojmenované položky v uživatelsky definovaných typech.

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

* Uživatelsky definované typy lze použít kdekoli, kde používáte jiné typy.
Konkrétně je možné definovat pole uživatelsky definovaného typu a zahrnout uživatelsky definovaný typ jako prvek typu řazené kolekce členů.

* Není možné vytvářet struktury rekurzivního typu.
To znamená, že typ, který definuje uživatelsky definovaný typ, nemůže být typ řazené kolekce členů, který obsahuje prvek uživatelsky definovaného typu.
Obecně platí, že uživatelsky definované typy nemůžou mít cyklicky závislé závislosti, takže následující sada definic typů je neplatná:

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a>Typy operací a funkcí

Zadané typy `'Tinput` a `'Tresult` :

* `('Tinput => 'Tresult)`je základní typ pro každou *operaci*, například `((Qubit, Pauli) => Result)` .
* `('Tinput -> 'Tresult)`je základní typ pro libovolnou *funkci*, například `(Int -> Int)` . 

Nazývají se *signatury* , které lze volat.

* Všechny volat s hodnotou Q # jako vstup mají jednu hodnotu a jako výstup vrátí jednu hodnotu.
* Můžete použít řazené kolekce členů pro vstupní i výstupní hodnoty.
* Volat, které nemají žádný výsledek, vrátí `Unit` .
* Volat, které nemají žádný vstup, přebírají jako vstup prázdnou řazenou kolekci členů.

### <a name="functors"></a>Funktory

Typy *funkcí* jsou zcela určeny jejich signaturou. Například funkce, která vypočítá sinus úhlu, by měla typ `(Double -> Double)` . 

*Operace* mají určité další vlastnosti, které se vyjadřují jako součást typu operace. Tyto vlastnosti obsahují informace o tom, které operace *funktory* podporuje.
Například pokud provedení operace spoléhá na stav jiného qubits, pak by měla podporovat `Controlled` funktor; Pokud má operace hodnotu Inverted, měla by podporovat `Adjoint` funktor.

> [!NOTE]
> Tento článek popisuje, jak funktory mění signaturu operace. Další podrobnosti o funktory a operacích naleznete [v tématu Operations and Functions in Q #](xref:microsoft.quantum.guide.operationsfunctions). 

Chcete-li `Controlled` v typu operace vyžadovat podporu pro a/nebo `Adjoint` funktor, je nutné přidat poznámku indikující odpovídající vlastnosti.
Poznámka `is Ctl` (například `(Qubit => Unit is Ctl)` ) indikuje, že operace je ovladatelné. To znamená, že jeho spuštění spoléhá na stav jiného qubit nebo qubits. Podobně Poznámka `is Adj` znamená, že operace má sousední, to znamená, že se může jednat o "Inverted", který po sobě provede operaci, a pak její sousední vztah do stavu opustí stav beze změny. 

Pokud chcete vyžadovat, aby operace tohoto typu podporovala i `Adjoint` `Controlled` funktor, můžete to vyjádřit jako `(Qubit => Unit is Adj + Ctl)` . Například integrovaná <xref:microsoft.quantum.intrinsic.x> operace Pauli je typu `(Qubit => Unit is Adj + Ctl)` . 

Typ operace, který nepodporuje žádné funktory, je určen samotným typem vstupu a výstupu bez další poznámky.

### <a name="type-parameterized-functions-and-operations"></a>Typ – parametrizované funkce a operace

Typy, které lze volat, mohou obsahovat *parametry typu*.
Použijte symbol, který je předponou jednoduché uvozovky k označení parametru typu; Například je platným `'A` parametrem typu.
Další informace a podrobnosti o tom, jak definovat typ s parametry volat, naleznete v tématu [Operations and Functions in Q #](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).

Parametr typu se může v jednom podpisu objevit více než jednou.
Například funkce, která použije jinou funkci na každý prvek pole a vrátí shromážděné výsledky má signaturu `(('A[], 'A->'A) -> 'A[])` .
Podobně funkce, která vrací složení dvou operací, má signaturu `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .

Když vyvoláte typ s parametrem Invoke, všechny argumenty, které mají stejný parametr typu, musí být stejného typu.

Q # neposkytuje mechanismus pro omezení možných typů, které může uživatel nahradit parametrem typu.

## <a name="next-steps"></a>Další kroky

Teď, když jste viděli všechny typy, které tvoří jazyk Q #, najdete informace [v tématu výrazy typu v Q #](xref:microsoft.quantum.guide.expressions) a Naučte se, jak vytvořit a manipulovat se výrazy těchto různých typů.
