---
title: 'Operace a funkce v Q #'
description: Definování a volání operací a funkcí, jakož i specializace řízených a sousedících operací.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: 6cfc1b14d86e86a1cbf0109d5e81dfe50c3a80bf
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630219"
---
# <a name="operations-and-functions-in-q"></a>Operace a funkce v Q #

## <a name="defining-new-operations"></a>Definování nových operací

Operace jsou základem Q #.
Po deklaraci je lze volat buď z klasických aplikací .NET, například pomocí simulátoru, nebo jinými operacemi v rámci Q #.
Každá operace definovaná v Q # může potom zavolat libovolný počet dalších operací, včetně integrovaných vnitřních operací definovaných jazykem. Konkrétní způsob, jakým jsou tyto vnitřní operace definovány, závisí na cílovém počítači.
Při kompilaci je každá operace reprezentována jako typ třídy .NET, který lze poskytnout cílovým počítačům.

Každý zdrojový soubor Q # může definovat libovolný počet operací.
Názvy operací musí být v rámci oboru názvů jedinečné a nemusí být v konfliktu s názvy typu nebo funkce.

Deklarace operace se skládá z klíčového slova `operation` následovaný symbolem, který představuje název operace, typ řazené kolekce členů definující argumenty operace, dvojtečku `:` , anotaci typu, která popisuje typ výsledku operace, volitelně poznámku s charakteristikou operace, levou složenou závorku `{` , tělo deklarace operace a konečnou pravou závorku `}` .

Každá operace provede vstup, vytvoří výstup a určí implementaci pro jednu nebo více specializací operace.
Možné specializace a jejich definování nebo volání jsou podrobněji popsané níže.
Prozatím zvažte následující operaci, která definuje jenom výchozí specializaci těla a jako svůj vstup přebírá jeden qubit, a pak na tomto vstupu zavolá vestavěnou <xref:microsoft.quantum.intrinsic.x> operaci:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

Klíčové slovo `operation` zahájí definici operace a následuje název; zde, `BitFlip` .
Dále je typ vstupu definován jako `Qubit` , společně s názvem `target` pro odkazování na vstup v rámci nové operace.
Podobně `Unit` definuje, že výstup operace je prázdný.
To se používá podobně `void` v jazyce C# a dalších imperativních jazycích a je ekvivalentem `unit` v F # a dalších funkčních jazycích.

Operace mohou také vracet zajímavější typy než `Unit` .
Například <xref:microsoft.quantum.intrinsic.m> operace vrátí výstup typu `Result` , který představuje vykonání měření. Můžete buď předat výstup z operace do jiné operace, nebo ho můžete použít s `let` klíčovým slovem k definování nové proměnné.

To umožňuje, aby představovalo klasický výpočet, který komunikuje s provozními operacemi na nízké úrovni, jako je například v [hustém kódování](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> Každá operace v Q # přebírá přesně jeden vstup a vrátí přesně jeden výstup.
> Několik vstupů a výstupů je pak znázorněno pomocí *řazených kolekcí členů*, které shromažďují více hodnot dohromady do jedné hodnoty.
> Řekněme, že Q # je jazyk řazené kolekce členů (Tuple) v řazené kolekci členů.
> Po tomto konceptu `()` by se měla číst jako "prázdná" řazená kolekce členů, která má typ `Unit` .


## <a name="controlled-and-adjoint-operations"></a>Řízené a sousedící operace

Pokud operace implementuje jednotnou transformaci, jako je případ mnoha operací v Q #, je možné definovat způsob, jakým operace funguje při *adjointed* nebo *řízeném*prvku. *Sousedící* specializace operace určuje způsob, jakým operace "INVERT" operace funguje, zatímco *řízená* specializace určuje, jak operace funguje, když je její aplikace podmíněně ve stavu konkrétního registru.

Adjoints operací je zásadní pro mnoho aspektů výpočetních operací. Níže najdete v části [conjugations](#conjugations) jednu takovou situaci popsanou společně s užitečnou programovací technikou Q #.

Řízená verze operace je nová operace, která efektivně aplikuje základní operaci pouze v případě, že všechny qubits ovládacího prvku jsou v zadaném stavu.
Pokud je qubits ovládacího prvku na pozici, pak je základní operace použita v souvislém umístění na příslušné straně.
Proto se pro generování entanglement často používají kontrolované operace.

Přirozeně by mohla existovat *řízená sousední* specializace a určení řízené aplikace sousedícího prvku operace.

> [!NOTE]
> Pokud se $U $ jedná o jednotnou transformaci implementovanou operací `U` , pak `Adjoint U` představuje jednotnou transformaci $U ^ \dagger $, což je komplexní sdružená transformace.
> Po sobě jdoucí použití operace a poté jejího souseda se stavem opustí stav beze změny, jak je znázorněno ve skutečnosti, že $UU ^ \dagger = U ^ \dagger U = \id $, matici identity.
> Jednotná reprezentace kontrolované operace je trochu větší odlišit, ale další podrobnosti najdete na stránce s přehledem [výpočetních konceptů: více qubits](xref:microsoft.quantum.concepts.multiple-qubits).

Následující část popisuje, jak volat tyto různé specializace v kódu Q #.
Níže najdete podrobné informace o tom, jak definovat operace pro jejich podporu.

### <a name="calling-operation-specializations"></a>Specializace operací volání

*Funktor* v Q # je objekt pro vytváření, který definuje novou operaci z jiné operace.
Dvě standardní funktory v Q # jsou `Adjoint` a `Controlled` .

Funktory má přístup k implementaci základní operace při definování implementace nové operace.
Proto může funktory provádět složitější funkce než tradiční funkce vyšší úrovně. Funktory v systému typů Q # není reprezentace. V současné době není možné je navazovat na proměnnou nebo předat jako argumenty. 

Funktor se používá k tomu, že se použije na operaci a vrátí novou operaci.
Například operace, která je výsledkem použití `Adjoint` funktor pro `Y` operaci, je zapsána jako `Adjoint Y` .
Nová operace se pak může vyvolávat jako jakákoli jiná operace.
Aby operace podporovala aplikace `Adjoint` a/nebo `Controlled` funktory, její návratový typ nutně musí být `Unit` . 

#### <a name="adjoint-functor"></a>`Adjoint`funktor

Proto `Adjoint Y(q1)` používá sousední funktor k `Y` operaci pro vygenerování nové operace a použije tuto novou operaci na `q1` .
Nová operace má stejný podpis a typ jako základní operace `Y` .
Konkrétně Nová operace také povoluje `Adjoint` a povolí `Controlled` pouze v případě základní operace.
Sousední funktor je svou vlastní invertovaná; To znamená, že `Adjoint Adjoint Op` je vždy stejné jako `Op` .

#### <a name="controlled-functor"></a>`Controlled`funktor

Obdobně `Controlled X(controls, target)` aplikuje řízený funktor na `X` operaci pro vygenerování nové operace a použije tuto novou operaci na `controls` a `target` .

> [!NOTE]
> V rámci Q # mají řízené verze vždycky převzít pole qubits ovládacího prvku a zadaný stav je vždycky pro všechny qubitsy ovládacího prvku ve stavu výpočty ( `PauliZ` ) `One` , $ \ket {1} $.
> Řízení založené na dalších stavech lze dosáhnout použitím příslušné jednotkové operace na qubits ovládacího prvku před řízenou operací a následným použitím inverzních operací po kontrolované operaci.
> Například použití `X` operace na qubit ovládacího prvku před a po kontrolované operaci způsobí, že operace bude řídit `Zero` stav ($ \ket {0} $) pro tento qubit; použití `H` operace před a poté bude řídit `PauliX` `One` stav, tj. 1 eigenvalue z Pauli X, $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt {2} $, nikoli `PauliZ` `One` stav.

S ohledem na výraz operace může být pomocí funktor vytvořen nový výraz operace `Controlled` .
Signatura nové operace vychází z podpisu původní operace.
Typ výsledku je stejný, ale vstupní typ je dvě n-tice s polem qubit, které obsahuje ovládací qubit (y) ovládacího prvku jako první prvek a argumenty původní operace jako druhý prvek.
Nová operace podporuje `Controlled` a bude podporovat `Adjoint` pouze v případě, že původní operace proběhla.

V případě, že původní operace trvala pouze jeden argument, budou se sem přicházet ekvivalenty singleton řazené kolekce členů.
Například `Controlled X` je řízená verze `X` operace. 
`X`má typ `(Qubit => Unit is Adj + Ctl)` , takže je `Controlled X` typu `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; vzhledem k rovnosti v řazené kolekci členů, je to stejné jako `((Qubit[], Qubit) => Unit is Adj + Ctl)` .

Pokud základní operace trvala několik argumentů, nezapomeňte do závorek uzavřít odpovídající argumenty kontrolované verze operace v závorkách, aby je bylo možné převést na řazenou kolekci členů.
Například `Controlled Rz` je řízená verze `Rz` operace. 
`Rz`má typ `((Double, Qubit) => Unit is Adj + Ctl)` , takže `Controlled Rz` je typu `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .
Proto `Controlled Rz(controls, (0.1, target))` by bylo platné vyvolání `Controlled Rz` (Poznamenejte si závorky kolem `0.1, target` ).

Jako další příklad `CNOT(control, target)` lze implementovat jako `Controlled X([control], target)` . Pokud by cíl měl být řízen 2 Control qubits (CCNOT), můžeme použít `Controlled X([control1, control2], target)` příkaz.

#### `Controlled Adjoint` 

`Controlled`Funktory a dokončí `Adjoint` dojíždění, takže není rozdíl mezi použitím `Controlled Adjoint Op` nebo `Adjoint Controlled Op` .


## <a name="defining-controlled-and-adjoint-implementations"></a>Definování řízených a sousedících implementací

V předchozích příkladech deklarace operace jsou operace `BitFlip` a `DecodeSuperdense` byly definovány s podpisy a v `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` uvedeném pořadí.
Jak `DecodeSuperdense` zahrnuje měření, nejedná se o jednotkovou operaci, a proto by nemohly nastavovat žádné specializace nesousedících a (vrátit související požadavek, který taková operace vrátí `Unit` ).
Jak ale `BitFlip` jednoduše provede jednotnou <xref:microsoft.quantum.intrinsic.x> operaci, můžeme ji definovat s oběma specializacemi.

Zde uvádíme podrobné informace o tom, jak zahrnout existenci specializací do deklarací operací Q #, čímž jim umožníte, aby je mohli volat ve spojení s `Adjoint` funktory a/nebo `Controlled` .
[Níže](#circumstances-for-validly-defining-specializations)uvádíme některé z situací, ve kterých je buď platná, nebo není platná, aby bylo možné deklarovat určité specializace.

Charakteristiky operace definují, jaké druhy funktory lze použít pro deklarovanou operaci a jaký má vliv. Existence těchto specializací se dá deklarovat jako součást signatury operace, konkrétně prostřednictvím poznámky s charakteristikou operace: buď `is Adj` , `is Ctl` nebo `is Adj + Ctl` .
Vlastní implementace každé specializace může být *implicitně* nebo *explicitně* definovaná.

### <a name="implicitly-specifying-implementations"></a>Implicitní určení implementací

V tomto případě se tělo deklarace operace skládá výhradně z výchozí implementace. Například:

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
V tomto případě se odpovídající implementace pro každou z těchto implicitně deklarované specializace automaticky vygeneruje kompilátorem, aby se provedla, pokud se `Adjoint` `Controlled` používají nebo funktory.

Volání by tedy způsobilo, `Adjoint PrepareEntangledPair` že kompilátor implementuje sousední metodu `CNOT` a poté sousední `H` .
Tyto jednotlivé operace jsou samostatně sousedící, takže výsledná `Adjoint PrepareEntangledPair` operace by se jednoduše použila k použití `CNOT(here, there)` a pak `H(here)` .
Proto to můžeme použít k zapsání `DecodeSuperdense` příkladu v kompaktním formátu pomocí sousedícího prvku `PrepareEntangledPair` pro transformaci stavu entangled zpět na dvojici unentangled qubits:

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

Poznámka s charakteristikami operace v deklaraci je užitečná pro zajištění, že kompilátor automaticky generuje další specializace na základě výchozí implementace. 

Při navrhování operací pro použití s funktory je potřeba vzít v úvahu několik důležitých omezení.
Nejdůležitější specializace pro operaci, která používá výstupní hodnotu jakékoli jiné operace, *nelze* automaticky generovat kompilátorem, protože je nejednoznačná, jak změnit pořadí příkazů v takové operaci pro získání stejného efektu.

Proto je často vhodné explicitně zadat různé implementace.

### <a name="explicitly-specifying-implementations"></a>Explicitní určení implementací

V případě, že se implementace nemůže generovat kompilátorem, je možné ji explicitně zadat. Tyto explicitní deklarace specializace můžou sestávat z vhodné *direktivy generace* nebo uživatelsky definované implementace.
Poskytujeme celou řadu možností s příklady níže.


#### <a name="explicit-specialization-declarations"></a>Explicitní deklarace specializace

Operace Q # můžou obsahovat následující explicitní deklarace specializace:

- `body`Specializace určuje implementaci operace bez použití funktory.
- `adjoint`Specializace určuje implementaci operace s `Adjoint` použitým funktor.
- `controlled`Specializace určuje implementaci operace s `Controlled` použitým funktor.
- `controlled adjoint`Specializace určuje implementaci operace s `Adjoint` `Controlled` použitým funktory a.
  Tato specializace může mít také název `adjoint controlled` , protože dvě funktory dojíždění.


Specializace operace se skládá z tagu specializace (např. `body` nebo `adjoint` atd.) následovaných jedním z těchto:

- Explicitní deklarace, jak je popsáno níže.
- *Direktiva* , která instruuje kompilátor, *jak* vygenerovat specializaci, jedna z těchto:
  - `intrinsic`, což znamená, že specializace je poskytována cílovým počítačem.
  - `distribute`, které lze použít s `controlled` `controlled adjoint` specializacemi a.
    Při použití s se `controlled` označuje, že kompilátor má vypočítat specializaci použitím `Controlled` pro všechny operace v `body` .
    Při použití s se `controlled adjoint` označuje, že kompilátor má vypočítat specializaci použitím `Controlled` pro všechny operace v `adjoint` specializaci.
  - `invert`, což označuje, že má kompilátor vypočítat `adjoint` specializaci `body` vrácením, tj. zrušením pořadí operací a aplikováním sousedního na každé z nich.
    Při použití s se `adjoint controlled` označuje, že kompilátor má vypočítat specializaci vrácením `controlled` specializace.
  - `self`, abyste označili, že specializace sousedícít je stejná jako `body` specializace.
    To je platné pro `adjoint` `adjoint controlled` specializace a.
    Pro `adjoint controlled` `self` znamená, že `adjoint controlled` specializace je stejná jako `controlled` specializace.
  - `auto`, abyste označili, že má kompilátor vybrat vhodnou direktivu, která se má použít.
    `auto`nemůže být použit pro `body` specializaci.

Direktivy a `auto` všechny vyžadují uzavírací středník `;` .
`auto`Direktiva se přeloží na následující direktivu generace, pokud je k `body` dispozici explicitní deklarace:

- `adjoint`Specializace je vygenerována podle direktivy `invert` .
- `controlled`Specializace je vygenerována podle direktivy `distribute` .
- `adjoint controlled`Specializace je generována podle direktivy `invert` `controlled` , pokud je zadána explicitní deklarace, ale nikoli jedna pro `adjoint` a `distribute` jinak.

> [!TIP]   
> Pokud je operace samostatně sousedící, explicitně určete buď sousední, nebo řízená sousední specializace pomocí direktivy generace, `self` aby kompilátor mohl používat tyto informace pro účely optimalizace.

Deklarace specializace obsahující uživatelsky definovanou implementaci se skládá z argumentů řazené kolekce členů následovaný blokem příkazu Q #, který implementuje specializaci.
V seznamu argumentů `...` se používá k reprezentaci argumentů deklarovaných pro operaci jako celku.
Pro `body` a `adjoint` by měl seznam argumentů vždy být `(...)` ; pro `controlled` a by `adjoint controlled` měl být seznam argumentů symbol reprezentující pole qubits ovládacího prvku následovaný znakem `...` uzavřeným v závorkách, například `(controls,...)` .

### <a name="examples"></a>Příklady

Deklarace operace může být jednoduchá, jak je uvedeno níže, což definuje primitivní operaci Pauli X:

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
Všimněte si, že sousední funkce operace Pauli X je definována s direktivou, `self` protože podle definice `X` je její vlastní inverzní.

Výše uvedený kód `PrepareEntangledPair` je podobný kódu jako v následujícím příkladu, který obsahuje explicitní deklarace specializace: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
Klíčové slovo `auto` označuje, že by měl kompilátor určit, jak se má vygenerovat implementace specializace.

#### <a name="user-defined-specialization-implementation"></a>Uživatelsky definovaná implementace specializace

Pokud kompilátor nemůže vygenerovat implementaci pro určitou specializaci automaticky, nebo pokud lze zadat účinnější implementaci, pak může být implementace také ručně definována.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user-defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
V předchozím příkladu označuje, `adjoint invert;` že specializace sousedící-je vygenerována invertující implementaci těla a `controlled adjoint invert;` označuje, že řízená sousední specializace je generována obrácenou implementací řízené specializace.

Pokud je nutné explicitně deklarovat jednu nebo více specializací, než je výchozí tělo, musí být implementace pro výchozí tělo zabalena do vhodné deklarace specializace:

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="circumstances-for-validly-defining-specializations"></a>Okolnosti pro platné definování specializací

#### <a name="operation-declarations-with-adjointcontrolled"></a>Deklarace operací s přiléhajícím/řízeným

Je možné zadat operaci bez sousedících nebo řízených verzí. Například operace měření nemají ani, protože nejsou inverzi nebo ovladatelné.

Operace podporuje rozhraní `Adjoint` a/nebo `Controlled` funktory, pokud jeho deklarace obsahuje implicitní nebo explicitní deklaraci příslušných specializací.

Explicitně deklarovaná sousední a řízená specializace implikuje existenci sousední specializace/řízené specializace. 

Pro operaci, jejíž tělo obsahuje smyčky opakování až po úspěšné, nastavte příkazy, měření, návratové příkazy nebo volání jiných operací, které nepodporují `Adjoint` funktor, automatické generování sousední specializace přiléhající podle `invert` `auto` direktivy or není možné.

Pro operaci, jejíž tělo obsahuje volání do jiných operací, které nepodporují `Controlled` funktor, není možné automaticky generovat řízená specializaci následující po `distribute` `auto` direktivě or.

#### <a name="controlled-adjoint"></a>Řízený sousedící

Řízená verze inřízených operací operace určuje, jak je implementována verze sousedících operací s řízenou počátečními událostmi.
Je právní určení operace bez řízené sousední verze; například operace měření nemají řízenou sousední verzi, protože nejsou ani ovladatelné ani inverzi.

Řízená sousední specializace pro operaci musí existovat, pokud je a jenom v případě, že existují sousední i řízená specializace. V takovém případě je existence řízené specializace instalovaná a příslušná specializace je vygenerována kompilátorem, pokud nebyla explicitně definována žádná implementace. 

Pro operaci, jejíž tělo obsahuje volání na jiné operace, které nemají řízenou nekontrolovanou verzi, automatické generování sousední specializace na základě `invert` `distribute` `auto` direktivy nebo není možné.


### <a name="type-compatibility"></a>Kompatibilita typů

Operaci s dalšími podporovanými funktory se dají použít kdekoli operace s menším počtem funktory, ale je očekáván stejný podpis.
Například operaci typu `(Qubit => Unit is Adj)` lze použít všude, kde `(Qubit => Unit)` je očekávána operace typu.

Q # je *kovariantní* s ohledem na možné návratové typy: volat, která vrací typ, `'A` je kompatibilní s typem volat se stejným vstupním typem a typem výsledku, který `'A` je kompatibilní s.

Q # je *kontravariantní* s ohledem na typy vstupu: dá se volat, který přebírá typ `'A` jako vstup je kompatibilní s typem, který se dá volat se stejným typem výsledku a vstupním typem, který je kompatibilní s `'A` .

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

- Funkci `ConjugateInvertWith` lze vyvolat pomocí `inner` argumentu buď `Invert` nebo `ApplyUnitary` .
- Funkce `ConjugateUnitaryWith` může být vyvolána s `inner` argumentem `ApplyUnitary` , ale ne `Invert` .
- Hodnota typu `(Qubit[] => Unit is Adj + Ctl)` může být vrácena z `ConjugateInvertWith` .

> [!IMPORTANT]
> Otázka č. 0,3 představila značný rozdíl v chování uživatelsky definovaných typů.

Uživatelsky definované typy jsou považovány za zabalenou verzi základního typu, nikoli jako podtyp.
To znamená, že hodnota uživatelsky definovaného typu není použitelná, pokud je očekávána hodnota základního typu.


### <a name="conjugations"></a>Conjugations

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

Od naší verze 0,9 podporujeme příkaz conjugation, který implementuje transformaci uvedenou výše. Pomocí tohoto příkazu `ApplyWith` může být operace implementována následujícím způsobem:

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

Inverzní transformace pro příkazy definované v rámci bloku je automaticky generována kompilátorem a provedena po dokončení bloku Apply.
Vzhledem k tomu, že jakékoli proměnlivé proměnné použité jako součást bloku nelze znovu svázat v bloku Apply, je vygenerovaná transformace zaručena jako sousední v výpočtu v bloku. 


## <a name="defining-new-functions"></a>Definování nových funkcí

Funkce jsou čistě deterministické, klasické rutiny v Q #, které se liší od operací v tom, že nemají dovoleno mít žádné účinky přesahující výpočet výstupní hodnoty.
Konkrétně funkce nemohou volat operace; působit na, přidělit nebo vypůjčit qubits; Ukázka náhodných čísel; nebo jinak závisí na stavu nad rámec vstupní hodnoty s funkcí.
V důsledku toho jsou funkce Q # *čisté*, v tom, že vždycky mapují stejné vstupní hodnoty na stejné výstupní hodnoty.
Kompilátor Q # umožňuje bezpečně změnit pořadí, jak a kdy jsou funkce volány při generování specializací operace.

Každý zdrojový soubor Q # může definovat libovolný počet funkcí.
Názvy funkcí musí být v rámci oboru názvů jedinečné a nemusí být v konfliktu s názvy operace nebo typu.

Definování funkce funguje podobně jako při definování operace s tím rozdílem, že pro funkci nelze definovat žádné sousedící a řízené specializace.
Například:

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

nebo 

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```

### <a name="classical-logic-in-functions--good"></a>Klasická logika v Functions = = dobrá

Pokaždé, když je to možné, je vhodné napsat klasický Logic z pojmu Functions namísto operací, aby bylo možné snadněji použít v rámci operací.
Pokud jsme například napsali `Square` deklaraci uvedenou výše jako *operaci*, kompilátor by nedokázal zaručit, že volání stejného vstupu by konzistentně vytvořilo stejné výstupy.

Pro podtržení rozdílu mezi funkcemi a operacemi zvažte problém klasického vzorkování náhodného čísla v rámci operace Q #:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Pokaždé, když se `U` zavolá, bude mít jinou akci `target` .
Konkrétně kompilátor nemůže zaručit, že pokud jsme přidali `adjoint auto` deklaraci specializace do `U` , pak `U(target); Adjoint U(target);` funguje jako identita (tj. jako No-OP).
To je v rozporu s definicí sousedícího, které jsme viděli v [vektorech a maticích](xref:microsoft.quantum.concepts.vectors), jako je povolení automatického generování sousední specializace v operaci, kde byla volána operace, <xref:microsoft.quantum.math.randomreal> by narušila záruky poskytované kompilátorem <xref:microsoft.quantum.math.randomreal> . Jedná se o operaci, pro kterou neexistuje žádná sousední nebo řízená verze.

Na druhé straně, povolení volání funkcí jako `Square` je bezpečné, v tom, že kompilátor může zajistit, že musí zachovávat pouze vstup, aby bylo možné `Square` zachovat stabilní výstup.
Proto izolování co nejvíc klasických logických funkcí do funkcí umožňuje snadno znovu použít tuto logiku v jiných funkcích a operacích.


## <a name="generic-type-parameterized-callables"></a>Obecné (typ – parametrizované) – volatelné

Mnoho funkcí a operací, které můžeme chtít definovat, se ve skutečnosti nespoléhá na typy jejich vstupů, ale místo toho pouze implicitně používají jejich typy prostřednictvím jiné funkce nebo operace.
Představte si třeba koncept *mapy* společný pro mnoho funkčních jazyků. po předané funkci $f (x) $ a kolekci hodnot $ \{ x_1, x_2, \dots, x_n \} $, map vrátí novou kolekci $ \{ f (x_1), f (x_2), \dots, f (x_n) \} $.
K implementaci tohoto v Q # můžeme využít výhod těchto funkcí jako první třídy.
Pojďme si napsat rychlý příklad `Map` , při použití ★ jako zástupného symbolu, a přitom zjistíme, jaké typy potřebujeme.

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

V podstatě jsme mohli napsat verzi `Map` pro každou dvojici typů, ke kterým došlo, ale to přináší řadu potíží.
Pokud například v nástroji zjistíte chybu, je `Map` nutné zajistit, aby se oprava používala jednotně napříč všemi verzemi nástroje `Map` .
Kromě toho, Pokud vytvoříme nové řazené kolekce členů nebo UDT, je teď také potřeba vytvořit nový `Map` pro přechod k novému typu.
I když se jedná o malý počet takových funkcí, protože shromažďujeme více a více funkcí stejné formy jako `Map` , náklady na zavedení nových typů se v poměrně krátkém pořadí stávají nepřiměřeně velkým.

Mnohé z těchto potíží se ale nedostaly do tohoto kompilátoru informace, které potřebuje k tomu, abyste zjistili, jak různé verze nástroje `Map` souvisejí.
Chceme, aby kompilátor považoval `Map` jako nějaký druh matematické funkce z *typů* q # do funkce q #.

Tento pojem je formální tím, že povoluje funkce a operace pro *parametry typu*a také jejich běžné parametry řazené kolekce členů.
V předchozích příkladech si chceme představit `Map` jako parametry typu `Int, Pauli` v prvním a `Double, String` druhém případě.
Ve většině případů lze tyto parametry typu použít, jako by se jednalo o běžné typy: používáme hodnoty parametrů typu k vytváření polí a řazených kolekcí členů, volání funkcí a operací a přiřazení k běžným nebo proměnlivým proměnným.

> [!NOTE]
> Největší případ nepřímých závislostí je qubits, kde program Q # nemůže přímo spoléhat na strukturu `Qubit` typu, ale **musí** předat takové typy jiným operacím a funkcím.

Po návratu do výše uvedeného příkladu vidíte, že potřebujeme `Map` mít parametry typu, jeden pro reprezentaci vstupu `fn` a druhý, který představuje výstup z `fn` .
V Q # se to zapisuje přidáním lomených závorek (to znamená `<>` Not brakets $ \braket {} $!) za názvem funkce nebo operace v deklaraci a výpisem každého parametru typu.
Název každého parametru typu musí začínat značkou `'` , která značí, že se jedná o parametr typu a ne běžný typ (označovaný také jako *konkrétní* typ).
Pro `Map` zapisujeme:

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
Jediným rozdílem je, že explicitně uvědomili kompilátor, který `Map` přímo nezávisí na tom `'Input` , co a `'Output` jsou, ale funguje pro všechny dva typy pomocí nepřímo prostřednictvím `fn` .
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
> Vzhledem k tomu, že každá funkce používá přesně jeden vstup a vrátí přesně jeden výstup, vstup typu `'T -> 'U` odpovídá *libovolné* funkci Q #.
> Podobně lze každou operaci předat do vstupu typu `'T => 'U` .

V druhém příkladu zvažte, jak napsat funkci, která vrací kompozici dvou dalších funkcí:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Tady je nutné přesně určit, co `A` , `B` a `C` jsou, a proto silně omezit nástroj naší nové `Compose` funkce.
Po všech případech `Compose` závisí pouze na `A` , a `B` a `C` *pomocí* `innerFn` a `outerFn` .
Alternativně můžeme přidat parametry typu k tomu, aby `Compose` označovali, že funguje pro *všechny* `A` , `B` a `C` , pokud se tyto parametry shodují s hodnotami, které očekává `innerFn` a `outerFn` :

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


## <a name="callables-as-first-class-values"></a>Se bude volat jako hodnoty první třídy.

Jednou z kritických postupů pro rozhodnutí o toku řízení a klasické logice pomocí funkcí místo operací je využití těchto operací a funkcí v Q # jsou *prvními třídami*.
To znamená, že jsou všechny hodnoty v jazyce v pravém.
Například následující je naprosto platný kód Q #, pokud je trochu nepřímá:

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

Hodnota proměnné `ourH` ve výše uvedeném fragmentu kódu je pak operace <xref:microsoft.quantum.intrinsic.h> , například, můžeme zavolat tuto hodnotu jako jakoukoli jinou operaci.
To nám umožňuje psát operace, které jako součást svého vstupu přijímají operace, které vytvářejí koncepty toku řízení vyššího řádu.
Můžeme si například představit, že se má "čtvercová" operace aplikovat dvakrát na stejný cílový qubit.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a>Vrácení operací z funkce

Zdůrazňujeme, že můžeme také vracet operace jako součást výstupů, takže můžeme izolovat některé druhy klasických podmíněných logiky jako klasických funkcí, které v podobě operace vrátí popis programu pro práci s poli.
Jednoduchým příkladem je zvážit příklad přenosu, ve kterém strana, která obdrží 16bitovou klasický zprávu, musí zprávu použít k dekódování jejich qubit do správného portu.
Můžeme to napsat s ohledem na funkci, která přebírá tyto dvě klasické bity a vrátí správnou operaci dekódování.

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

Tato nová funkce je ve skutečnosti funkcí, v takovém případě je volána se stejnými hodnotami `hereBit` a a vrátíme `thereBit` vždy stejnou operaci.
Proto lze dekodér bezpečně spustit uvnitř operací, aniž byste museli mít důvod na to, jak logika dekódování komunikuje s definicemi různých specializací operace.
To znamená, že jsme izolaci klasické logiky uvnitř funkce a zaručili kompilátor, že volání funkce může být přeobjednáno pomocí impunity, pokud je zachován vstup.


## <a name="partial-application"></a>Částečná aplikace

Díky funkcím, které vracejí operace, můžeme použít *částečnou aplikaci*, ve které můžeme zadat jednu nebo více částí vstupu do funkce nebo operace, aniž byste je skutečně volali. Například `ApplyTwice` opakované volání výše uvedeného příkladu můžeme označit, že nechcete zadat hned, na které qubit by měla vstupní operace platit:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

V tomto případě místní proměnná `twiceOp` obsahuje částečně použitou operaci `ApplyTwice(op, _)` , kde jsou části vstupu, které ještě nebyly určeny, označeny `_` .
Když ve skutečnosti voláme na `twiceOp` Další řádek, předáte jako vstup do částečně použité operace všechny zbývající části vstupu do původní operace.
Proto je výše uvedený fragment kódu prakticky stejný jako při `ApplyTwice(op, target)` přímém volání, Uložit pro, že jsme zavedli novou místní proměnnou, která nám umožní zpoždění volání při poskytování některých částí vstupu.

Vzhledem k tomu, že operace, která byla částečně použita, není ve skutečnosti volána, dokud není poskytnut celý vstup, můžeme částečně použít operace i v rámci funkcí.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

V zásadě byla klasická logika v rámci `SquareOperation` může být mnohem více zapojena, ale je stále izolovaná od zbytku operace zárukami, které může kompilátor nabízet o funkcích.
Tento přístup se bude používat v rámci celé knihovny Q # pro vyjádření toku klasického řízení způsobem, který se dá snadno použít v rámci programu pro překročení úrovně.


## <a name="recursion"></a>Rekurze

Je možné, že volat v Q # můžou být přímo nebo nepřímo rekurzivní.
To znamená, že operace nebo funkce může volat sám sebe nebo může volat jinou metodu, kterou přímo nebo nepřímo volá operaci, kterou lze volat.

Existují dva důležité komentáře k použití rekurze, ale:

- Použití rekurze v operacích může být v konfliktu s některými optimalizacemi.
  To může mít zásadní vliv na dobu provádění algoritmu.
- Při provádění na skutečném zařízení ve formátu paměti může být prostor zásobníku omezený a důkladná rekurze může vést k chybě za běhu.
  Konkrétně kompilátor Q # a modul runtime neidentifikují a optimalizují koncovou rekurzi.

## <a name="next-steps"></a>Další kroky

Přečtěte si o [proměnných](xref:microsoft.quantum.guide.variables) v Q #.