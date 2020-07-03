---
title: 'Operace a funkce v Q #'
description: Definování a volání operací a funkcí, jakož i specializace řízených a sousedících operací.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: 08eaf150a38afd789f8a23f567ff111d002bac07
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884214"
---
# <a name="operations-and-functions-in-q"></a>Operace a funkce v Q #

## <a name="defining-new-operations"></a>Definování nových operací

Operace jsou základem Q #.
Po deklaraci je lze volat buď z klasických aplikací .NET, například pomocí simulátoru nebo jiných operací v rámci Q #.
Každá operace definovaná v Q # může volat libovolný počet dalších operací, včetně integrovaných vnitřních operací definovaných jazykem. Konkrétní způsob, jakým Q # definuje tyto vnitřní operace, závisí na cílovém počítači.
Při kompilaci je každá operace reprezentována jako typ třídy .NET, který lze poskytnout cílovým počítačům.

Každý zdrojový soubor Q # může definovat libovolný počet operací.
Název operace musí být v rámci oboru názvů jedinečný a nemůže být v konfliktu s názvy typu nebo funkce.

Deklarace operace se skládá z klíčového slova `operation` následovaný symbolem, který představuje název operace, typ řazené kolekce členů definující argumenty operace, dvojtečku `:` , anotaci typu, která popisuje typ výsledku operace, volitelně poznámku s charakteristikou operace, levou složenou závorku a pak tělo deklarace operace uzavřené v závorkách `{ }` .

Každá operace provede vstup, vytvoří výstup a určí implementaci pro jednu nebo více specializací operace.
Možné specializace a jejich definování a volání jsou podrobně popsány v různých částech tohoto článku.
Prozatím zvažte následující operaci, která definuje jenom výchozí specializaci těla a jako svůj vstup přebírá jeden qubit, a pak na tomto vstupu zavolá vestavěnou <xref:microsoft.quantum.intrinsic.x> operaci:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

Klíčové slovo `operation` zahájí definici operace následovaný názvem; zde, `BitFlip` .
Dále je typ vstupu definován ( `Qubit` ), spolu s názvem, `target` pro odkazování na vstup v rámci nové operace.
Nakonec `Unit` definuje, že výstup operace je prázdný.
`Unit`se používá podobně `void` v jazyce C# a dalších imperativních jazycích a je ekvivalentní s jazykem `unit` F # a dalšími funkčními jazyky.

Operace mohou také vracet zajímavější typy než `Unit` .
Například <xref:microsoft.quantum.intrinsic.m> operace vrátí výstup typu `Result` , který představuje vykonání měření.  Můžete ji předat z operace do jiné operace nebo ji použít s `let` klíčovým slovem k definování nové proměnné.

Tento přístup umožňuje, aby představoval klasický výpočet, který komunikuje s provozními operacemi na nízké úrovni, jako je například v [hustém kódování](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):

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
> Více vstupů a výstupů je znázorněno pomocí *řazených kolekcí členů*, které shromažďují více hodnot dohromady do jedné hodnoty.
> V tomto případě Q # je jazyk řazené kolekce členů v řazené kolekci členů.
> Po tomto konceptu by měla být sada prázdných závorek `()` načtena jako "prázdná" řazená kolekce členů, která má typ `Unit` .

## <a name="controlled-and-adjoint-operations"></a>Řízené a sousedící operace

Pokud operace implementuje jednotnou transformaci, jako je případ mnoha operací v Q #, je možné definovat způsob, jakým operace funguje při *adjointed* nebo *řízeném*prvku. *Sousedící* specializace operace určuje způsob, jakým operace "INVERT" operace funguje, zatímco *řízená* specializace určuje, jak operace funguje, když je její aplikace podmíněně ve stavu konkrétního registru.

Adjoints operací je zásadní pro mnoho aspektů výpočetních operací. Příklad jedné takové situace popsané společně s užitečnou programovací technikou Q # najdete v tématu [conjugations](#conjugations) v tomto článku. 

Řízená verze operace je nová operace, která efektivně aplikuje základní operaci pouze v případě, že všechny qubits ovládacího prvku jsou v zadaném stavu.
Pokud je qubits ovládacího prvku na pozici, pak je základní operace použita v souvislém umístění na příslušné straně.
Proto se pro generování entanglement často používají kontrolované operace.

Přirozeně by mohla existovat *řízená sousední* specializace a určení řízené aplikace sousedícího prvku operace.

> [!NOTE]
> Pokud se $U $ jedná o jednotnou transformaci implementovanou operací `U` , pak `Adjoint U` představuje jednotnou transformaci $U ^ \dagger $, což je komplexní sdružená transformace.
> Po sobě jdoucí použití operace a poté jejího souseda se stavem opustí stav beze změny, jak je znázorněno ve skutečnosti, že $UU ^ \dagger = U ^ \dagger U = \id $, matici identity.
> Jednotná reprezentace kontrolované operace je trochu větší odlišit, ale další podrobnosti najdete na stránce s přehledem [výpočetních konceptů: více qubits](xref:microsoft.quantum.concepts.multiple-qubits).

Následující část popisuje, jak volat tyto různé specializace v kódu Q # a jak definovat operace pro jejich podporu.

### <a name="calling-operation-specializations"></a>Specializace operací volání

*Funktor* v Q # je objekt pro vytváření, který definuje novou operaci z jiné operace.
Dvě standardní funktory v Q # jsou `Adjoint` a `Controlled` .

Funktory má přístup k implementaci základní operace při definování implementace nové operace.
Proto může funktory provádět složitější funkce než tradiční funkce vyšší úrovně. Funktory v systému typů Q # není reprezentace. V současné době není možné je navazovat na proměnnou nebo předat jako argumenty. 

Použijte funktor, protože ho použijete k operaci, která vrací novou operaci.
Například použití `Adjoint` funktor pro `Y` operaci vrátí novou operaci `Adjoint Y` . Novou operaci můžete vyvolat jako jakoukoli jinou operaci.
Aby operace podporovala aplikaci `Adjoint` nebo `Controlled` funktory, její návratový typ nutně musí být `Unit` . 

#### <a name="adjoint-functor"></a>`Adjoint`funktor

Proto `Adjoint Y(q1)` použije `Adjoint` funktor k `Y` operaci pro vygenerování nové operace a použije tuto novou operaci na `q1` .
Nová operace má stejný podpis a typ jako základní operace `Y` .
Konkrétně Nová operace také podporuje `Adjoint` a podporuje `Controlled` pouze v případě, že došlo k základní operaci.
`Adjoint`Funktor je vlastní Inverted; to znamená, že je `Adjoint Adjoint Op` vždy stejný jako `Op` .

#### <a name="controlled-functor"></a>`Controlled`funktor

Obdobně `Controlled X(controls, target)` aplikuje `Controlled` funktor na `X` operaci pro vygenerování nové operace a použije tuto novou operaci na `controls` a `target` .

> [!NOTE]
> V rámci Q # mají řízené verze vždycky převzít pole qubits ovládacího prvku a řízení je vždy založené na všech ovládacích qubits, které jsou ve stavu výpočtu ( `PauliZ` ) `One` , $ \ket {1} $.
> Řízení založené na dalších stavech se dosahuje tím, že se pro kontrolní qubits před kontrolovaným provozem aplikuje příslušná Jednotková operace a po kontrolované operaci se použijí inverzní funkce pro jednotnou operaci.
> Například použití `X` operace na ovládací prvek qubit před a poté, co řízená operace způsobí, že operace bude řídit `Zero` stav ($ \ket {0} $) pro tento qubit; použití `H` operace před a po ovládacích prvcích ve `PauliX` `One` stavu, to znamená-1 eigenvalue z Pauli X, $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt $, a {2} ne na `PauliZ` `One` stav.

S ohledem na výraz operace můžete vytvořit nový výraz operace pomocí `Controlled` funktor.
Signatura nové operace vychází z podpisu původní operace.
Typ výsledku je stejný, ale vstupní typ je dvě n-tice s polem qubit, které obsahuje ovládací qubit (y) ovládacího prvku jako první prvek a argumenty původní operace jako druhý prvek.
Nová operace podporuje `Controlled` a bude podporovat `Adjoint` pouze v případě, že původní operace proběhla.

V případě, že původní operace trvala pouze jeden argument, přichází v úvahu [rovnocennost řazené kolekce členů](xref:microsoft.quantum.guide.types) do hry.
Například `Controlled X` je řízená verze `X` operace. 
`X`má typ `(Qubit => Unit is Adj + Ctl)` , takže je `Controlled X` typu `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; vzhledem k rovnosti v řazené kolekci členů, je to stejné jako `((Qubit[], Qubit) => Unit is Adj + Ctl)` .

Pokud základní operace trvala několik argumentů, nezapomeňte do závorek uzavřít odpovídající argumenty kontrolované verze operace v závorkách, aby je bylo možné převést na řazenou kolekci členů.
Například `Controlled Rz` je řízená verze `Rz` operace. 
`Rz`má typ `((Double, Qubit) => Unit is Adj + Ctl)` , takže `Controlled Rz` je typu `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .
Proto `Controlled Rz(controls, (0.1, target))` by bylo platné vyvolání `Controlled Rz` (Poznamenejte si závorky kolem `0.1, target` ).

Jako další příklad `CNOT(control, target)` lze implementovat jako `Controlled X([control], target)` . Pokud má cíl být řízen dvěma ovládacími qubits (CCNOT), použijte `Controlled X([control1, control2], target)` příkaz.

#### `Controlled Adjoint` 

`Controlled`Funktory a dokončí `Adjoint` dojíždění, takže není rozdíl mezi použitím `Controlled Adjoint Op` nebo `Adjoint Controlled Op` .


## <a name="defining-controlled-and-adjoint-implementations"></a>Definování řízených a sousedících implementací

V deklaraci první operace v předchozích příkladech operace `BitFlip` a `DecodeSuperdense` byly definovány s podpisy a v `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` uvedeném pořadí.
Jak `DecodeSuperdense` zahrnuje měření, nejedná se o jednotkovou operaci, a proto by nemohly nastavovat žádné specializace nesousedících a (vrátit související požadavek, který taková operace vrátí `Unit` ).
Jak ale `BitFlip` jednoduše provede jednotnou <xref:microsoft.quantum.intrinsic.x> operaci, můžete ji definovat s oběma specializacemi.

Tato část podrobně popisuje, jak zahrnout existenci specializace v deklaracích operací Q #, takže jim umožní volat ve spojení s `Adjoint` nebo `Controlled` funktory.
Další informace o některých situacích, ve kterých je buď platný, nebo není platný pro deklaraci určitých specializací, naleznete v tématu [okolnosti pro platné definování specializací](#circumstances-for-validly-defining-specializations) v tomto článku.

Charakteristiky operace definují, jaké druhy funktory můžete použít pro deklarovanou operaci a jaký má vliv. Existence těchto specializací se dá deklarovat jako součást signatury operace, konkrétně prostřednictvím poznámky s charakteristikou operace: buď `is Adj` , `is Ctl` nebo `is Adj + Ctl` .
Vlastní implementace každé specializace může být *implicitně* nebo *explicitně* definovaná.

### <a name="implicitly-specifying-implementations"></a>Implicitní určení implementací

V tomto případě se tělo deklarace operace skládá výhradně z výchozí implementace. Příklad:

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
Proto můžete použít tuto možnost k zapsání `DecodeSuperdense` v předchozím příkladu, a to tak, že pomocí sousedícího prvku `PrepareEntangledPair` vrátíte stav entangled zpět na pár unentangled qubits:

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

V případě, že kompilátor nemůže vygenerovat implementaci, můžete ji zadat explicitně. Tyto explicitní deklarace specializace můžou sestávat z vhodné *direktivy generace* nebo uživatelsky definované implementace.
Následující seznam uvádí celou řadu možností s některými příklady explicitní specializace. 


#### <a name="explicit-specialization-declarations"></a>Explicitní deklarace specializace

Operace Q # můžou obsahovat následující explicitní deklarace specializace:

- `body`Specializace určuje implementaci operace bez použití funktory.
- `adjoint`Specializace určuje implementaci operace s `Adjoint` použitým funktor.
- `controlled`Specializace určuje implementaci operace s `Controlled` použitým funktor.
- `controlled adjoint`Specializace určuje implementaci operace s `Adjoint` `Controlled` použitým funktory a.
  Tato specializace může mít také název `adjoint controlled` , protože dvě funktory dojíždění.


Specializace operace se skládá z tagu specializace (například `body` nebo `adjoint` ) následovaného jedním z těchto:

- Explicitní deklarace, jak je popsáno v následujícím tématu.
- *Direktiva* , která instruuje kompilátor, *jak* vygenerovat specializaci, jedna z těchto:
  - `intrinsic`, což znamená, že cílový počítač poskytuje specializaci.
  - `distribute`, používá se v `controlled` rámci `controlled adjoint` specializace a.
    Při použití s se `controlled` označuje, že kompilátor má vypočítat specializaci použitím `Controlled` pro všechny operace v `body` .
    Při použití s se `controlled adjoint` označuje, že kompilátor má vypočítat specializaci použitím `Controlled` pro všechny operace v `adjoint` specializaci.
  - `invert`, což znamená, že by kompilátor měl vypočítat `adjoint` specializaci tím, že se obrátí `body` , například převrácení pořadí operací a použití sousedícího na každý z nich.
    Při použití s se `adjoint controlled` označuje, že kompilátor má vypočítat specializaci vrácením `controlled` specializace.
  - `self`, abyste označili, že specializace sousedícít je stejná jako `body` specializace.
    Použití `self` je platné pro `adjoint` `adjoint controlled` specializace a.
    Pro `adjoint controlled` `self` znamená, že `adjoint controlled` specializace je stejná jako `controlled` specializace.
  - `auto`, abyste označili, že má kompilátor vybrat vhodnou direktivu, která se má použít.
    `auto`Pro specializaci nelze použít `body` .

Direktivy a `auto` všechny vyžadují uzavírací středník `;` .
`auto`Direktiva se přeloží na následující generovanou direktivu, pokud `body` je zadána explicitní deklarace:

- `adjoint`Specializace generuje podle direktivy `invert` .
- `controlled`Specializace generuje podle direktivy `distribute` .
- `adjoint controlled`Specializace generuje podle direktivy `invert` , pokud je zadána explicitní deklarace `controlled` , ale ne jedna pro `adjoint` a `distribute` jinak.

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

V předchozím `PrepareEntangledPair` příkladu je kód ekvivalentní následujícímu kódu, který obsahuje explicitní deklarace specializace: 

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

Pokud kompilátor nemůže vygenerovat implementaci pro určitou specializaci automaticky, nebo pokud je možné zadat účinnější implementaci, můžete implementovat implementaci ručně.

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
V předchozím příkladu označuje, `adjoint invert;` že specializace sousední, má být vygenerována invertující implementaci těla a `controlled adjoint invert;` označuje, že řízená sousední specializace s je vygenerována obrácením dané implementace řízené specializace.

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

Je možné zadat operaci bez sousedících nebo řízených verzí. Například operace měření nemají ani proto, že nejsou inverzi nebo ovladatelné.

Operace podporuje rozhraní `Adjoint` a `Controlled` funktory, pokud jeho deklarace obsahuje implicitní nebo explicitní deklaraci příslušných specializací.

Explicitně deklarovaná sousední a řízená specializace implikuje existenci sousední specializace/řízené specializace. 

Pro operaci, jejíž tělo obsahuje smyčky opakování až po úspěšné, nastavte příkazy, měření, návratové příkazy nebo volání jiných operací, které nepodporují `Adjoint` funktor, automatické generování sousední specializace přiléhající podle `invert` `auto` direktivy or není možné.

Pro operaci, jejíž tělo obsahuje volání do jiných operací, které nepodporují `Controlled` funktor, není možné automaticky generovat řízená specializaci podle `distribute` `auto` direktivy or.

#### <a name="controlled-adjoint"></a>Řízený sousedící

Řízená sousední verze operace určuje, jak implementovat verzi sousedícího prvku se správou počtu procesorů.
Je právní určení operace bez řízené sousední verze; například operace měření nemají řízenou sousední verzi, protože nejsou ani ovladatelné ani inverzi.

Řízená sousední specializace pro operaci musí existovat, pokud je a jenom v případě, že existují sousední i řízená specializace. V takovém případě je odvozená existence řízené specializace. Pokud není explicitně definována žádná implementace, zkompiluje vygeneruje příslušnou specializaci.

Pro operaci, jejíž tělo obsahuje volání na jiné operace, které nemají řízenou nekontrolovanou verzi, automatické generování sousední specializace přiléhající za `invert` `distribute` direktivou, nebo není `auto` možné.


### <a name="type-compatibility"></a>Kompatibilita typů

Použijte operaci s dalšími funktory podporovanými kdekoli, kde použijete operaci s méně funktory, ale stejnou signaturou. Například použijte operaci typu kdekoli, kde používáte `(Qubit => Unit is Adj)` operaci typu `(Qubit => Unit)` .

Q # je *kovariantní* s ohledem na možné návratové typy: volat, která vrací typ, `'A` je kompatibilní s typem volat se stejným vstupním typem a typem výsledku, který je kompatibilní s `'A` .

Q # je *kontravariantní* s ohledem na typy vstupu: dá se volat, který přebírá typ `'A` jako vstup je kompatibilní s typem, který se dá volat se stejným typem výsledku a vstupním typem, který je kompatibilní s `'A` .

To znamená, že s ohledem na následující definice

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

Můžeš

- Vyvolejte funkci `ConjugateInvertWith` s `inner` argumentem buď `Invert` nebo `ApplyUnitary` .
- Vyvolejte funkci `ConjugateUnitaryWith` s `inner` argumentem `ApplyUnitary` , ale ne `Invert` .
- Vrátí hodnotu typu `(Qubit[] => Unit is Adj + Ctl)` z `ConjugateInvertWith` .

> [!IMPORTANT]
> Otázka č. 0,3 představila značný rozdíl v chování uživatelsky definovaných typů.

Uživatelsky definované typy jsou považovány za zabalenou verzi základního typu, nikoli jako podtyp.
To znamená, že hodnota uživatelsky definovaného typu není použitelná, pokud očekáváte hodnotu základního typu.


### <a name="conjugations"></a>Conjugations

Na rozdíl od klasických bitů, uvolňování paměti je trochu více zapojeno, protože nevidomé resetující qubits může mít nežádoucí důsledky zbývajícího výpočtu, pokud qubits stále entangled. Tyto účinky je možné vyhnout tím, že před uvolněním paměti vykonává správné "rušení" prováděných výpočtů. Běžným vzorem pro výpočetní výkon je následující: 

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

Počínaje verzí 0,9 verze Q # podporuje příkaz conjugation, který implementuje předchozí transformaci. Pomocí tohoto příkazu `ApplyWith` může být operace implementována následujícím způsobem:

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
Takový příkaz conjugation je mnohem užitečnější, pokud vnější a vnitřní transformace nejsou okamžitě k dispozici jako operace, ale místo toho jsou vhodnější pro popis pomocí bloku skládajícího se z několika příkazů. 

Inverzní transformace pro příkazy definované v rámci bloku je automaticky generována kompilátorem a spuštěna po dokončení bloku Apply.
Vzhledem k tomu, že jakékoli proměnlivé proměnné použité jako součást bloku nelze znovu svázat v bloku Apply, je vygenerovaná transformace zaručena jako sousední v výpočtu v bloku. 


## <a name="defining-new-functions"></a>Definování nových funkcí

Funkce jsou čistě deterministické, klasické rutiny v Q #, které se liší od operací v tom, že nemají dovoleno mít žádné účinky přesahující výpočet výstupní hodnoty.
Konkrétně funkce nemohou volat operace; působit na, přidělit nebo vypůjčit qubits; Ukázka náhodných čísel; nebo jinak závisí na stavu nad rámec vstupní hodnoty s funkcí.
V důsledku toho jsou funkce Q # *čisté*, v tom, že vždycky mapují stejné vstupní hodnoty na stejné výstupní hodnoty.
Toto chování umožňuje kompilátoru Q # bezpečně změnit pořadí, jak a kdy volat funkce při generování specializací operace.

Každý zdrojový soubor Q # může definovat libovolný počet funkcí.
Názvy funkcí musí být jedinečné v rámci oboru názvů a nemohou být v konfliktu s názvy operací nebo typů.

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

Kdykoli je to možné, je vhodné napsat klasický Logic z pojmu Functions namísto operací, aby je mohl snadněji použít. Například pokud jste napsali předchozí `Square` deklaraci jako *operaci*, kompilátor by nedokázal zaručit, že volání stejného vstupu by konzistentně vytvořilo stejné výstupy.

Pro podtržení rozdílu mezi funkcemi a operacemi zvažte problém klasického vzorkování náhodného čísla v rámci operace Q #:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Pokaždé, když `U` se zavolá, má jinou akci `target` .
Konkrétně kompilátor nemůže zaručit, že pokud přidáte `adjoint auto` deklaraci specializace do `U` , `U(target); Adjoint U(target);` funguje jako identita (tj. jako No-OP).
To je v rozporu s definicí sousedícího prvku definovaného v [vektorech a maticích](xref:microsoft.quantum.concepts.vectors), což umožňuje kompilátoru automaticky generovat sousední specializaci objektu v operaci, při které volání operace <xref:microsoft.quantum.math.randomreal> způsobí přerušení záruk poskytnutých kompilátorem <xref:microsoft.quantum.math.randomreal> . Jedná se o operaci, pro kterou neexistuje žádná sousední nebo řízená verze.

Na druhé straně, povolení volání funkcí, jako `Square` je bezpečná, a zaručuje kompilátor, že musí pouze zachovávat vstup pro `Square` zajištění stabilního výstupu.
Proto izolování co nejvíc klasických logických funkcí do funkcí umožňuje snadno znovu použít tuto logiku v jiných funkcích a operacích.


## <a name="generic-type-parameterized-callables"></a>Obecné (typ – parametrizované) – volatelné

Mnoho funkcí a operací, které můžete chtít definovat, se ve skutečnosti nespoléhá na typy jejich vstupů, ale místo toho pouze implicitně používají jejich typy prostřednictvím jiné funkce nebo operace.
Představte si třeba koncept *mapy* společný pro mnoho funkčních jazyků. po předané funkci $f (x) $ a kolekci hodnot $ \{ x_1, x_2, \dots, x_n \} $, map vrátí novou kolekci $ \{ f (x_1), f (x_2), \dots, f (x_n) \} $.
Chcete-li implementovat tento postup ve verzi Q #, využijte fakt, že funkce jsou první třídy.
Tady je rychlý příklad, který `Map` se používá `T` jako zástupný symbol při zjištění, jaké typy potřebujete.

```qsharp
function Map(fn : (T -> T), values : T[]) : T[] {
    mutable mappedValues = new T[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Všimněte si, že tato funkce vypadá velmi stejně bez ohledu na to, jaké skutečné typy nahradíte.
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

V zásadě můžete napsat verzi `Map` pro každou dvojici typů, ke kterým dojde, ale to přináší několik problémů.
Pokud například v nástroji narazíte na chybu `Map` , je nutné zajistit, aby se oprava používala jednotně napříč všemi verzemi nástroje `Map` .
Kromě toho, pokud vytváříte nové řazené kolekce členů nebo UDT, musíte nyní také vytvořit nový, aby bylo možné `Map` Přejít k novému typu.
I když je to pro malý počet takových funkcí rušivý, když shromáždíte více a více funkcí stejného formuláře jako `Map` , náklady na zavedení nových typů se v poměrně krátkém pořadí změní na nepřiměřeně velké.

Mnohé z těchto potíží však jsou výsledkem faktu, že jste kompilátor neudělili informace, které potřebuje k tomu, abyste rozpoznali, jak různé verze nástroje `Map` souvisejí.
Efektivně budete chtít, aby kompilátor považoval `Map` jako nějaký druh matematické funkce z q # Functions *types* do funkce q #.

Q # formalizes tento pojem tím, že povoluje funkce a operace pro *parametry typu*a také jejich běžné parametry řazené kolekce členů.
V předchozích příkladech si přejete si představit `Map` jako parametry typu `Int, Pauli` v prvním a `Double, String` druhém případě.
Ve většině případů použijte tyto parametry typu, jako by se jednalo o běžné typy. Použijte hodnoty parametrů typu pro vytvoření polí a řazených kolekcí členů, volání funkcí a operací a přiřazení k běžným nebo proměnlivým proměnným.

> [!NOTE]
> Největším případem nepřímé závislosti je to, že qubits, kde se program Q # nemůže přímo spoléhat na strukturu `Qubit` typu, ale **musí** předat takové typy jiným operacím a funkcím.

Návrat k předchozímu příkladu, vidíte, že `Map` musí mít parametry typu, jeden pro reprezentaci vstupu a druhý, který `fn` představuje výstup z `fn` .
V Q # se to zapisuje přidáním lomených závorek (to znamená `<>` Not brakets $ \braket {} $!) za názvem funkce nebo operace v deklaraci a výpisem každého parametru typu.
Název každého parametru typu musí začínat značkou `'` , která značí, že se jedná o parametr typu a ne běžný typ (označovaný také jako *konkrétní* typ).
Proto `Map` je zapsána:

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Všimněte si, že definice `Map<'Input, 'Output>` vypadá velmi podobně jako verze previoius.
Jediným rozdílem je, že jste explicitně informovali o kompilátoru, který `Map` přímo nezávisí na tom `'Input` , co a `'Output` jsou, ale funguje pro všechny dva typy pomocí nepřímo prostřednictvím `fn` .
Po definování `Map<'Input, 'Output>` tímto způsobem ho můžete zavolat, jako by to byla běžná funkce:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> Zápis obecných funkcí a operací je jedním z míst, kde "řazená kolekce členů" v řazené kolekci členů "je velmi užitečným způsobem, jak se zamyslet na funkce a operace Q #.
> Vzhledem k tomu, že každá funkce používá přesně jeden vstup a vrátí přesně jeden výstup, vstup typu `'T -> 'U` odpovídá *libovolné* funkci Q #.
> Podobně můžete předat jakoukoli operaci do vstupu typu `'T => 'U` .

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
Alternativně můžete přidat parametry typu k tomu, aby `Compose` označovali, že funguje pro *jakékoli* `A` , `B` , a `C` , pokud tyto parametry odpovídají očekávaným parametrům `innerFn` a `outerFn` :

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

Hodnota proměnné `ourH` v předchozím fragmentu kódu je pak operace <xref:microsoft.quantum.intrinsic.h> , například, kterou můžete zavolat jako jakoukoli jinou operaci.
Díky této funkci můžete zapisovat operace, které jako součást svého vstupu přijímají operace, a vytvořit tak vyšší koncepty toku řízení.
Například můžete si představit, že se má "čtvercová" operace aplikovat dvakrát na stejný cílový qubit.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a>Vrácení operací z funkce

Je důležité zdůraznit, že můžete také vracet operace jako součást výstupů, takže můžete izolovat některé druhy klasických podmíněných logických funkcí jako klasických funkcí, které v podobě operace vrátí popis programového množství.
Jednoduchým příkladem je zvážit příklad přenosu, ve kterém strana, která obdrží 16bitovou klasický zprávu, musí zprávu použít k dekódování jejich qubit do správného portu.
To můžete napsat z podmínek funkce, která přebírá tyto dvě klasické bity a vrátí správnou operaci dekódování.

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

Tato nová funkce je ve skutečnosti funkcí, v tom, že pokud ji zavoláte se stejnými hodnotami `hereBit` a `thereBit` , vždy se vrátí stejná operace.
Proto lze dekodér bezpečně spustit uvnitř operací, aniž byste museli mít důvod na to, jak logika dekódování komunikuje s definicemi různých specializací operace.
To znamená, že klasická logika uvnitř funkce je izolovaná a zaručuje kompilátor, že volání funkce může být přeobjednáno pomocí impunity, pokud je zachováno zadání.


## <a name="partial-application"></a>Částečná aplikace

Díky funkcím, které vracejí operace, můžete s využitím *částečné aplikace*, ve které zadáváte jednu nebo více částí vstupu do funkce nebo operace, provést mnohem více, aniž byste je skutečně volali. V předchozím `ApplyTwice` příkladu můžete určit, že nechcete zadat hned, na které qubit by měla vstupní operace platit:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

V tomto případě místní proměnná `twiceOp` obsahuje částečně aplikovanou operaci `ApplyTwice(op, _)` , kde `_` označuje části vstupu, které ještě nebyly určeny.
Při volání na `twiceOp` Další řádek předáte jako vstup do částečně použité operace všechny zbývající části vstupu do původní operace.
Proto předchozí fragment kódu je prakticky stejný jako při `ApplyTwice(op, target)` přímém volání, uložte pro to, že jste zavedli novou místní proměnnou, abyste mohli zpoždění volání při poskytování některých částí vstupu.

Vzhledem k tomu, že operace, která je částečně aplikována, není ve skutečnosti volána, dokud není poskytnut celý vstup, můžete bezpečně použít operace, i když jsou v rámci funkcí.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

V zásadě byla klasická logika v rámci `SquareOperation` může být mnohem více zapojena, ale je stále izolovaná od zbytku operace zárukami, které může kompilátor nabízet o funkcích. Standardní knihovna Q # používá tento přístup v celém pro účely exprese klasického toku řízení způsobem, který mohou programy snadno použít.


## <a name="recursion"></a>Rekurze

Je možné, že volat v Q # můžou být přímo nebo nepřímo rekurzivní.
To znamená, že operace nebo funkce může volat sám sebe nebo může zavolat jinou metodu, kterou přímo nebo nepřímo volá operaci, kterou lze volat.

Existují dva důležité komentáře k použití rekurze, ale:

- Použití rekurze v operacích může být v konfliktu s některými optimalizacemi.
  Toto rušení může mít zásadní vliv na dobu provádění algoritmu.
- Při spuštění na skutečném zařízení ve formátu paměti může být velikost zásobníku omezená, takže hluboká rekurze může vést k chybě za běhu.
  Konkrétně kompilátor Q # a modul runtime neidentifikují a optimalizují koncovou rekurzi.

## <a name="next-steps"></a>Další kroky

Přečtěte si o [proměnných](xref:microsoft.quantum.guide.variables) v Q #.