---
title: 'Typ Q # model | Microsoft Docs'
description: Model typu Q#
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 0aabb144779da301b71ad215c8e975cc29b4dcce
ms.sourcegitcommit: ca5015fed409eaf0395a89c2e4bc6a890c360aa2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76871630"
---
# <a name="the-type-model"></a>Model typu

V této části se dozvíte o modelu typu Q # a popisuje syntaxi pro zadání a práci s typy.
Upozorňujeme, že Q # je jazyk *silného typu* , takže pečlivé používání těchto typů může kompilátoru přispět, aby poskytovalo silné záruky na programy Q # v době kompilace.

Aby bylo možné zajistit nejpřísnější záruky, převody mezi typy v Q # musí být explicitní pomocí volání funkcí, které tento převod vyjadřují. K dispozici je celá řada takových funkcí jako součást oboru názvů <xref:microsoft.quantum.convert>.
Přetypování na kompatibilní typy na druhé straně se implicitně stane. 

Q # poskytuje jak primitivní typy, které lze použít přímo, a různé způsoby, jak vytvořit nové typy z jiných typů.
Popíšeme všechny ve zbývající části tohoto oddílu.

## <a name="primitive-types"></a>Primitivní typy

Jazyk Q # poskytuje několik *primitivních typů*, ze kterých lze sestavit další typy:

- Typ `Int` představuje celé číslo se znaménkem 64, např.: `2`, `107``-5`.
- Typ `BigInt` představuje celé číslo se znaménkem libovolné velikosti, např. `2L`, `107L``-5L`.
   Tento typ je založený na <xref:System.Numerics.BigInteger> .NET.
   textový.
- Typ `Double` představuje číslo s plovoucí desetinnou čárkou s dvojitou přesností, např.: `0.0`, `-1.3`, `4e-7`.
- Typ `Bool` představuje logickou hodnotu, která může být buď `true` nebo `false`.
- Typ `Qubit` představuje bit qubit nebo.
   `Qubit`s jsou neprůhledné pro uživatele; jedinou operací, která je k dispozici, je kromě jejich předání jiné operaci testovat identitu (rovnost).
   V konečném případě se akce u `Qubit`s implementují voláním vnitřních instrukcí na procesor s více procesory (nebo na jeho simulaci).
- Typ `Pauli` představuje jednu ze čtyř operátorů Pauli s jedním qubit.
   Tento typ slouží k označení základní operace pro rotace a určení pozorovatele, které se měří.
   Toto je výčtový typ, který má čtyři možné hodnoty: `PauliI`, `PauliX`, `PauliY`a `PauliZ`, což jsou konstanty typu `Pauli`.
- Typ `Result` představuje výsledek měření.
   Toto je výčtový typ se dvěma možnými hodnotami: `One` a `Zero`, což jsou konstanty typu `Result`.
   `Zero` označuje, že došlo k měření + 1 eigenvalue; `One` označuje eigenvalue-1.
- Typ `Range` představuje sekvenci celých čísel, označených `start..step..stop`, kde označuje krok s možnostmi. 
   To znamená, že `start .. stop` odpovídá `start..1..stop`a například `1..2..7` představuje sekvenci $\{1, 3, 5, 7\}$.
- Typ `String` je posloupnost znaků Unicode, která je po vytvoření uživatelem neprůhledná.
  Tento typ slouží k hlášení zpráv na klasického hostitele v případě chyby nebo diagnostické události.
- Typ `Unit` je typ, který povoluje pouze jednu hodnotu `()`. 
  Tento typ slouží k označení, že funkce Q # nebo operace nevrátí žádné informace. 

Konstanty `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`a `Zero`, jsou všechny rezervované symboly v Q #.

## <a name="array-types"></a>Typy polí

Vzhledem k platnému `'T`typu Q # existuje typ, který představuje pole hodnot typu `'T`.
Tento typ pole je reprezentován jako `'T[]`; například `Qubit[]` nebo `Int[][]`.
Například kolekce celých čísel je označena `Int[]`, zatímco pole polí hodnot `(Bool, Pauli)` je označeno `(Bool, Pauli)[][]`.

V druhém příkladu si všimněte, že představuje potenciálně vícenásobné pole polí a ne obdélníkové dvourozměrné pole.
Q # neposkytuje podporu pro pravoúhlá pole s multidimenzionálními hodnotami.

Hodnota pole může být napsána ve zdrojovém kódu Q # pomocí hranatých závorek kolem prvků pole, jak je uvedeno v `[PauliI, PauliX, PauliY, PauliZ]`.
Typ literálu pole je určen běžným základním typem všech položek v poli. 

> [!WARNING]
> Po vytvoření pole nelze prvky pole změnit.
> K vytvoření upraveného pole lze použít příkazy Update a Reassign a výrazy Copy a Update.

Pole lze také vytvořit z jeho velikosti pomocí klíčového slova `new`:

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

V obou případech je po sestavení pole základní funkce `Length` možné použít k získání počtu prvků jako `Int`.
Pole mohou být v dolních lomených závorkách, s dolními indexy buď typu `Int`, nebo typu `Range`, pro získání jednoho nebo nového pole obsahujícího podmnožinu prvků pole.
Dolní indexy polí jsou počítány od nuly:

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>Typy řazené kolekce členů

Vzhledem k nule nebo více různým typům `T0`, `T1`,... `Tn`, můžeme jako `(T0, T1, ..., Tn)`poznamenat nový *typ řazené kolekce členů* .
Typy, které slouží k vytvoření nového typu řazené kolekce členů, mohou být řazené kolekce členů, jako v `(Int, (Qubit, Qubit))`.
Takové vnořování je vždy omezené, ale v případě, že typy řazené kolekce členů nemůžou za žádných okolností obsahovat samy sebe.

Hodnoty nového typu řazené kolekce členů jsou řazené kolekce členů vytvořené pomocí sekvencí hodnot z každého typu v řazené kolekci členů.
Například `(3, false)` je řazená kolekce členů, jejíž typ je typ řazené kolekce členů `(Int, Bool)`.
Je možné vytvořit pole řazených kolekcí členů, řazené kolekce členů, řazené kolekce členů, atd.

Od Q # 0,3 je `Unit` název *typu* prázdné řazené kolekce členů; pro prázdnou *hodnotu*řazené kolekce členů se používá `()`.

Instance řazené kolekce členů jsou neměnné.
Q # neposkytuje mechanismus pro změnu obsahu řazené kolekce členů po vytvoření.

Řazené kolekce členů jsou účinným konceptem použitým v rámci Q # ke shromáždění hodnot dohromady do jedné hodnoty, což usnadňuje jejich předání.
Konkrétně při použití notace řazené kolekce členů můžeme vyjádřit, že každá operace a možnost volat přebírá přesně jeden vstup a vrátí přesně jeden výstup.

### <a name="singleton-tuple-equivalence"></a>Rovnost řazené kolekce členů singleton

Je možné vytvořit singleton (jeden prvek) řazené kolekce členů, `('T1)`, například `(5)` nebo `([1,2,3])`.
Otázka č. Q však považuje typ Tuple typu Singleton za úplný ekvivalent hodnoty uzavřeného typu.
To znamená, že se nejedná o rozdíl mezi `5` a `(5)`ani mezi `5`mi a `(((5)))`nebo mezi `(5, (6))` a `(5, 6)`.

Tato rovnocennost se vztahuje na všechny účely, včetně přiřazení a výrazů.
Je stejná jako platná pro zápis `(5)+3` jako zápis `5+3`a oba výrazy se vyhodnotí jako `8`.
Konkrétně to znamená, že operace nebo funkce, jejíž vstupní řazená kolekce členů nebo výstupní řazená kolekce členů má jedno pole, může být považována za jeden argument nebo vrací jedinou hodnotu.

Tato vlastnost odkazuje jako na _rovnost v řazené kolekci členů typu Singleton_.

## <a name="user-defined-types"></a>Uživatelsky definované typy

Soubor Q # může definovat nový pojmenovaný typ obsahující jednu hodnotu jakéhokoli právního typu.
Pro jakýkoli typ řazené kolekce členů `T`můžeme deklarovat nový uživatelsky definovaný typ, který je podtypem `T` pomocí příkazu `newtype`.
V oboru názvů @"microsoft.quantum.math" jsou například komplexní čísla definovány jako uživatelsky definovaný typ:

```qsharp
newtype Complex = (Double, Double);
```

Tento příkaz vytvoří nový typ se dvěma anonymními položkami typu `Double`.   
Kromě anonymních položek podporuje uživatelsky definované typy také pojmenované položky jako Q # verze 0,7 nebo vyšší. Například můžeme mít název položky `Re` pro dvojitou hodnotu, která představuje skutečnou část komplexního čísla a `Im` pro imaginární část: 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Pojmenování jedné položky v uživatelsky definovaném typu neznamená, že všechny položky musí být pojmenovány – podporuje se libovolná kombinace pojmenovaných a nepojmenovaných položek. Kromě toho mohou být pojmenovány také vnitřní položky.
Typ `Nested`, jak je definováno níže pro příklad má `(Double, (Int, String))`základního typu, z něhož je pojmenována pouze položka typu `Int` a všechny ostatní položky jsou anonymní. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
Pojmenované položky mají výhodu, ke kterým lze přistupovat přímo prostřednictvím operátoru přístupu `::`. 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

Aby bylo možné přistupovat k anonymním položkám na druhé straně, je třeba zabalenou hodnotu nejprve extrahovat pomocí operátoru přípony `!`.
Operátor "Unwrap", `!`umožňuje extrahovat hodnotu obsaženou v uživatelsky definovaném typu.
Typ takového výrazu "Unwrap" je základní typ uživatelsky definovaného typu. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

Operátor rozbalení rozbalí právě jednu vrstvu obtékání.
Pro přístup k hodnotě zabalené na násobení lze použít více operátorů rozbalení.

Příklad:

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

Další podrobnosti najdete v oddílu věnovaném [rozbalení výrazů](xref:microsoft.quantum.language.expressions#unwrap-expressions) a [prioritě operátorů](xref:microsoft.quantum.language.expressions#operator-precedence) .

Hodnoty uživatelsky definovaného typu lze vytvořit voláním odpovídajícího konstruktoru typu:

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Případně můžete nové hodnoty vytvořit z existujících pomocí [výrazů kopírování a aktualizace](xref:microsoft.quantum.language.expressions#copy-and-update-expressions). Podobně jako u polí tyto výrazy kopírují všechny hodnoty položky původního výrazu s výjimkou zadaných pojmenovaných položek. Pro tyto hodnoty jsou nastaveny na ty definované na pravé straně výrazu. Jakékoli jiné jazykové konstrukce, jako například [Příkazy Update-a-Reassign](xref:microsoft.quantum.language.statements#update-and-reassign-statement), které jsou k dispozici pro položky pole pro pojmenované položky v uživatelsky definovaných typech.

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

Není možné vytvářet struktury rekurzivního typu.
To znamená, že typ, který definuje uživatelsky definovaný typ, nemůže být typ řazené kolekce členů, který obsahuje prvek uživatelsky definovaného typu.
Obecněji, uživatelsky definované typy nemůžou mít na sobě navzájem cyklické závislosti, takže následující sada definic typu by mohla být neplatná:

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

Kromě poskytování krátkých aliasů pro potenciálně složité typy řazené kolekce členů, což je jedna významná výhoda pro definování takových typů, je, že mohou zdokumentovat záměr konkrétní hodnoty.
Návrat na příklad `Complex`, jeden mohl také definovat 2D polární souřadnice jako uživatelsky definovaný typ:

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

I když mají oba `Complex` i `Polar` základní typ `(Double, Double)`, jsou tyto dva typy zcela nekompatibilní v Q #, což minimalizuje riziko náhodného volání komplexní matematické funkce s polárními souřadnicemi a naopak.
Tímto způsobem mají uživatelsky definované typy podobnou roli jako záznamy F# například. 


## <a name="operation-and-function-types"></a>Typy operací a funkcí

_Operace_ Q # je podprogram.
To znamená, že se jedná o volanou rutinu, která obsahuje kvantové operace.

_Funkce_ Q # je klasická subrutina používaná v rámci algoritmu pro každé z nich.
Může obsahovat klasický kód, ale žádné nečinnosti.
Konkrétně funkce nemusí přidělovat ani půjčovat qubits a nesmí volat operace.
Je však možné předat jejich operace nebo qubits ke zpracování.
Funkce jsou tedy zcela deterministické v tom smyslu, že volání se stejnými argumenty budou vždy vracet stejný výsledek. 

Operace a funkce se společně nazývají _volat_.  Níže vidíte některé [Příklady](#examples) .

Všechny volat pomocí Q # se považují za vstupní hodnotu a jako výstup vrátí jedinou hodnotu.
Vstupní i výstupní hodnoty mohou být řazené kolekce členů.
Je k dispozici, které nemají `Unit`žádného výsledku vrácení.
Volat, které nemají žádný vstup, přebírají jako vstup prázdnou řazenou kolekci členů.

Základní typ pro jakékoli vyzkoušení se zapisuje jako `('Tinput => 'Tresult)` nebo `('Tinput -> 'Tresult)`, kde jsou typy `'Tinput` i `'Tresult`.
Pro operace se používá první formulář s `=>`. Druhý formulář s `->`pro funkce.
`((Qubit, Pauli) => Result)` například představuje signaturu pro možnou operaci měření s jedním qubit.

Typy funkcí jsou zcela určeny jejich signaturou.
Například funkce, která vypočítá sinus úhlu, by měla typu `(Double -> Double)`.

Operace, ale ne funkce – mají určité další _vlastnosti_ , které se vyjadřují jako součást typu operace. Tyto vlastnosti zahrnují informace o tom, co funktory operace podporuje.
Funktory jsou meta operace, které generují specializaci základní operace. viz [funktory](#functors)níže.

Typy operací jsou určeny jejich vstupním typem, typem výstupu a jejich charakteristikami.    
Aby bylo možné vyžadovat podporu `Controlled` a/nebo `Adjoint` funktor v typu operace, musíme přidat poznámku, která indikuje odpovídající vlastnosti.
`is Ctl` poznámky například označuje, že je operace ovladatelné. Pokud chceme vyžadovat, aby operace tohoto typu podporovala `Adjoint` i `Controlled` funktor, můžeme to vyjádřit jako `(Qubit => Unit is Adj + Ctl)`. Použité charakteristiky operace `Adj` a `Ctl` výhradně řečeno jsou dvě předem definované sady popisků, kde každý popisek označuje konkrétní charakteristiky operace, například podporu konkrétního funktoru.
Proto `+` slouží k označení sjednocení těchto dvou sad a `*` se používá k označení průniku, tj. popisky, které jsou pro obě sady společné.  

Například operace Pauli `X` je typu `(Qubit => Unit is Adj + Ctl)`.
Typ operace, který nepodporuje žádné funktory, je určen samotným typem vstupu a výstupu bez další poznámky.


### <a name="type-parameterized-functions-and-operations"></a>Typ – parametrizované funkce a operace

Typy, které lze volat, mohou obsahovat parametry typu.
Parametry typu jsou označeny symbolem, který je předponou jedné uvozovky. například `'A` je platným parametrem typu.

Parametr typu se může v jednom podpisu objevit více než jednou.
Například funkce, která použije jinou funkci na každý prvek pole a vrátí shromážděné výsledky, by měly `(('A[], 'A->'A) -> 'A[])`podpisu.
Podobně funkce, která vrací složení dvou operací, může mít `((('A=>'B), ('B=>'C)) -> ('A=>'C))`signatury.

Při vyvolání volání typu s parametrem typu musí být všechny argumenty, které mají stejný parametr typu, stejného typu.

Q # neposkytuje mechanismus pro omezení možných typů, které mohou být nahrazeny parametrem typu.

### <a name="type-compatibility"></a>Kompatibilita typů

Operaci s dalšími podporovanými funktory se dají použít kdekoli operace s menším počtem funktory, ale je očekáván stejný podpis.
Například operace typu `(Qubit => Unit is Adj)` může být použita kdekoli je očekávána operace typu `(Qubit => Unit)`.

Q # je kovariantní s ohledem na možné návratové typy: volat, která vrací typ `'A` je kompatibilní s typem, který je možné volat stejným vstupním typem a výsledným typem, který je `'A` kompatibilní.

Q # je kontravariantní s ohledem na typy vstupu: dá se volat, který přebírá typ `'A` jako vstup je kompatibilní s typem, který se dá volat se stejným typem výsledku a vstupním typem, který je kompatibilní s `'A`.

To znamená s ohledem na následující definice:

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

platí následující:

- Funkci `ConjugateInvertWith` lze vyvolat pomocí `inner` argumentu buď `Invert`, nebo `ApplyUnitary`.
- Funkci `ConjugateUnitaryWith` lze vyvolat pomocí argumentu `inner` `ApplyUnitary`, ale ne `Invert`.
- Z `ConjugateInvertWith`může být vrácena hodnota typu `(Qubit[] => Unit is Adj + Ctl)`.

> [!IMPORTANT]
> Q # 0,3 zavádí značný rozdíl v chování uživatelsky definovaných typů.

Uživatelsky definované typy jsou považovány za zabalenou verzi základního typu, nikoli jako podtyp.
To znamená, že hodnota uživatelsky definovaného typu není použitelná, pokud je očekávána hodnota základního typu.

### <a name="functors"></a>Funktory

Funktor v Q # je objekt pro vytváření, který definuje novou operaci z jiné operace.
Funktory má přístup k implementaci základní operace při definování implementace nové operace.
Proto může funktory provádět složitější funkce než tradiční funkce vyšší úrovně.

Funktory v systému typů Q # není reprezentace. V současné době není možné je navazovat na proměnnou nebo předat jako argumenty. 

Funktor se používá k tomu, že se použije na operaci a vrátí novou operaci.
Například operace, která je výsledkem použití `Adjoint` funktor na operaci `Y`, je zapsána jako `Adjoint Y`.
Nová operace se pak může vyvolávat jako jakákoli jiná operace.
Proto `Adjoint Y(q1)` pro vytvoření nové operace použít sousedící funktor k operaci `Y` a tuto novou operaci použije na `q1`.

Podobně `Controlled X(controls, target)` pro vygenerování nové operace použít kontrolované funktor k operaci `X` a tato nová operace se aplikuje na `controls` a `target`.

Dvě standardní funktory ve Q # jsou `Adjoint` a `Controlled`.

#### <a name="adjoint"></a>Sousednít

V případě náročných výpočetních operací je sousední operace operace složitá sdružená operace.
Pro operace, které implementují operátor s jednou jednotkou, je sousední osoba inverzní k operaci.
Pro jednoduchou operaci, která pouze vyvolá sekvenci dalších operací v rámci sady qubits, mohou být sousedníci vypočítáni použitím adjoints dílčích operací na stejném qubits v obráceném pořadí.

Při použití výrazu operace může být pomocí `Adjoint` funktor vytvořen nový výraz operace.
Například `Adjoint QFT` určí souseda operace `QFT`.
Nová operace má stejný podpis a typ jako základní operace.
Konkrétně Nová operace také umožňuje `Adjoint`a povolí `Controlled` pouze v případě, že došlo k základní operaci.

Sousední funktor je svou vlastní invertovaná; To znamená, že `Adjoint Adjoint Op` je vždy stejné jako `Op`.

#### <a name="controlled"></a>Kontrol

Řízená verze operace je nová operace, která efektivně aplikuje základní operaci pouze v případě, že všechny qubits ovládacího prvku jsou v zadaném stavu.
Pokud je qubits ovládacího prvku na pozici, pak je základní operace použita v souvislém umístění na příslušné straně.
Proto se pro generování entanglement často používají kontrolované operace.

V rámci Q # mají řízené verze vždycky převzít pole qubits ovládacího prvku a zadaný stav je vždycky pro všechny kontrolní qubits ve stavu výpočet-(`PauliZ`) `One`, $ \ket{1}$.
Řízení založené na dalších stavech lze dosáhnout použitím příslušné jednotkové operace na qubits ovládacího prvku před řízenou operací a následným použitím inverzních operací po kontrolované operaci.
Například použití operace `X` na qubit ovládacího prvku před a po kontrolované operaci způsobí, že operace bude řídit stav `Zero` ($ \ket{0}$) pro tento qubit; použití operace `H` před a poté bude řídit stav `One` `PauliX`, což je-1 eigenvalue z Pauli X, $ \ket{-} \mathrel{: =} (\ket{0}-\ket{1})/\sqrt{2}$ místo `PauliZ` `One` stavu.

Při použití výrazu operace může být pomocí `Controlled` funktor vytvořen nový výraz operace.
Signatura nové operace vychází z podpisu původní operace.
Typ výsledku je stejný, ale vstupní typ je dvě n-tice s polem qubit, které obsahuje ovládací qubit (y) ovládacího prvku jako první prvek a argumenty původní operace jako druhý prvek.
Nová operace podporuje `Controlled`a bude podporovat `Adjoint` pouze v případě, že původní operace proběhla.

V případě, že původní operace trvala pouze jeden argument, budou se sem přicházet ekvivalenty singleton řazené kolekce členů.
`Controlled X` je například řízená verze `X` operace.
`X` má `(Qubit => Unit is Adj + Ctl)`typu, takže `Controlled X` má typ `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; vzhledem k rovnosti řazené kolekce členů singleton je to stejné jako `((Qubit[], Qubit) => Unit is Adj + Ctl)`.

Pokud základní operace trvala několik argumentů, nezapomeňte do závorek uzavřít odpovídající argumenty kontrolované verze operace v závorkách, aby je bylo možné převést na řazenou kolekci členů.
`Controlled Rz` je například řízená verze `Rz` operace.
`Rz` má `((Double, Qubit) => Unit is Adj + Ctl)`typu, takže `Controlled Rz` má typ `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.
Proto by `Controlled Rz(controls, (0.1, target))` bylo platné vyvolání `Controlled Rz` (Poznačte si závorky kolem `0.1, target`).

Jako další příklad můžete `CNOT(control, target)` implementovat jako `Controlled X([control], target)`. Pokud by cíl měl být řízen 2 qubits řízení (CCNOT), můžeme použít příkaz `Controlled X([control1, control2], target)`.

### <a name="examples"></a>Příklady

Tento příklad operace Q # přichází z ukázky [měření](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) . V rámci operací můžeme přidělovat qubits a využívat operace na těchto qubits, jako jsou `H` a `X`:

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit() : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit
            set result = M(qubit);      // Measure the qubit
            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

Tento příklad funkce pochází z ukázky [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) . Obsahuje čistě klasický kód. Můžete vidět, že na rozdíl od výše uvedeného příkladu nejsou přiděleny žádné qubits a nepoužívají se žádné operace.

```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function PointwiseProduct(left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

Je také možné předat funkci qubits ke zpracování, jako v tomto příkladu z ukázky [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) . Qubits se předávají do funkce a používají se ke zpracování, i když se v žádném okamžiku nezměnily stavy qubit.

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates(
    qubits : Qubit[], 
    masks : MCMTMask[]) 
: MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```
