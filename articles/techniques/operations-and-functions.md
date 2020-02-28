---
title: 'Operace a funkce Q #'
description: 'Přečtěte si o operacích a funkcích Q # a o tom, jak se používají v programu pro práci za provozu.'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 43f0cf2da192a607e514d0c7de57a9bdd067faf7
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907660"
---
# <a name="q-operations-and-functions"></a>Operace a funkce Q #

Programy Q # se skládají z jednoho nebo více *operací* , které popisují vedlejší účinky. operace mohou mít data za sebou a jednu nebo více *funkcí* , které umožňují úpravy klasických dat. Na rozdíl od operací se funkce používají k popisu čistě klasického chování a nemají žádné vlivy na výpočetní výkonové hodnoty v klasickém prostředí.

Každá operace definovaná v Q # může potom zavolat libovolný počet dalších operací, včetně integrovaných vnitřních operací definovaných jazykem. Konkrétní způsob, jakým jsou tyto vnitřní operace definovány, závisí na cílovém počítači. Při kompilaci je každá operace reprezentována jako typ třídy .NET, který lze poskytnout cílovým počítačům.

## <a name="defining-new-operations"></a>Definování nových operací

Jak je popsáno výše, nejzákladnější stavební blok programového prostředí napsaného v Q # je *operace*, kterou je možné volat buď z klasických aplikací .NET, například pomocí simulátoru, nebo jinými operacemi v rámci Q #.
Každá operace provede vstup, vytvoří výstup a určí implementaci pro jednu nebo více specializací operace.
Následující operace například definuje pouze výchozí specializaci těla a jako vstup bere jeden qubit a potom na tomto vstupu zavolá integrovanou `X` operaci:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

Klíčové slovo `operation` zahájí definici operace a následuje název; zde `BitFlip`.
Dále je typ vstupu definován jako `Qubit`, společně s názvem `target` pro odkazování na vstup v rámci nové operace.
Podobně `Unit` definuje, že výstup operace je prázdný.
To se používá podobně jako `void` v C# a dalších imperativních jazycích a je ekvivalentní `unit` v F# a dalších funkčních jazycích.

> [!NOTE]
> Podrobněji prozkoumáme níže, ale každá operace v Q # přebírá přesně jeden vstup a vrátí přesně jeden výstup.
> Několik vstupů a výstupů je pak znázorněno pomocí *řazených kolekcí členů*, které shromažďují více hodnot dohromady do jedné hodnoty.
> Řekněme, že Q # je jazyk řazené kolekce členů (Tuple) v řazené kolekci členů.
> Po tomto konceptu by měl být `()` číst jako "prázdná" řazená kolekce členů, která má typ `Unit`.

V rámci nové operace lze implementaci zadat přímo v rámci deklarace, pokud je nutné explicitně zadat pouze implementaci výchozí specializace těla. Kromě toho je možné definovat implementace, například jednu nebo více `functor` operací, jak je uvedeno níže. V předchozím příkladu je jediným příkazem volání integrované operace Q # <xref:microsoft.quantum.intrinsic.x>.

Operace mohou také vracet zajímavější typy než `Unit`.
Například operace <xref:microsoft.quantum.intrinsic.m> vrátí výstup typu `Result`, který představuje vykonání měření. Můžete buď předat výstup z operace do jiné operace, nebo ho můžete použít s klíčovým slovem `let` k definování nové proměnné.
<!-- Link to UID for superdense conceptual and example documentation. -->
To umožňuje, aby představovalo klasický výpočet, který komunikuje s provozními operacemi na nízké úrovni, jako je například v hustém kódování:

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a>Funktory, sousední a řízený
Pokud operace implementuje jednotnou transformaci, je možné definovat způsob, jakým operace funguje při *adjointed* nebo *řízených*. Sousedící specializace operace určuje, jak funguje při zpětném spuštění, zatímco řízená specializace určuje, jak operace funguje, když se aplikuje v podmínkách pro stav registru.
Existence těchto specializací se dá deklarovat jako součást signatury operace: `is Adj + Ctl` v následujícím příkladu. Odpovídající implementace pro každou takovou implicitně deklarovanou specializaci je následně vygenerována kompilátorem. 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> Mnoho operací v Q # představuje jednotnou branu.
> Pokud $U $ je Jednotná brána reprezentovaná operací `U`, pak `Adjoint U` představuje jednotkovou bránu $U ^ \dagger $.

V případě, že se implementace nemůže generovat kompilátorem, je možné ji explicitně zadat. Tyto explicitní deklarace specializace můžou sestávat z vhodné direktivy generace nebo uživatelsky definované implementace. Kód v `PrepareEntangledPair` výše je například ekvivalentní následujícímu kódu, který obsahuje explicitní deklarace specializace: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
Klíčové slovo `auto` označuje, že kompilátor by měl určit, jak se má vygenerovat implementace specializace.
Pokud kompilátor nemůže vygenerovat implementaci pro určitou specializaci automaticky, nebo pokud lze zadat účinnější implementaci, pak může být implementace také ručně definována.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
Ve výše uvedeném příkladu `adjoint invert;` označuje, že specializace sousedící-by měla být vygenerována vrácením implementace těla a `controlled adjoint invert;` označuje, že řízená specializace, která je řízena, je vygenerována obrácením dané implementace řízené specializace.

V [toku řízení v horním řádu](xref:microsoft.quantum.concepts.control-flow)se zobrazí další příklady.

Chcete-li volat specializaci operace, použijte klíčová slova `Adjoint` nebo `Controlled`.
Například příklad výše uvedeného ukázkového kódu lze zapsat kompaktnější pomocí přiléhajícího prvku `PrepareEntangledPair` k transformaci stavu entangled zpět na pár unentangled qubits:

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

Při navrhování operací pro použití s funktory je potřeba vzít v úvahu několik důležitých omezení.
Nejdůležitější specializace pro operaci, která používá výstupní hodnotu jakékoli jiné operace, nelze automaticky generovat kompilátorem, protože je nejednoznačná, jak změnit pořadí příkazů v takové operaci pro získání stejného efektu.


## <a name="defining-new-functions"></a>Definování nových funkcí

Q # také umožňuje definovat *funkce*, které se liší od operací v tom, že nesmí mít žádné účinky přesahující výpočet výstupní hodnoty.
Konkrétně funkce nemohou volat operace, pracovat na qubits, vzorkovat náhodná čísla nebo jinak závisí na stavu mimo vstupní hodnotu funkce.
V důsledku toho jsou funkce Q # *čisté*, v tom, že vždycky mapují stejné vstupní hodnoty na stejné výstupní hodnoty.
Kompilátor Q # umožňuje bezpečně změnit pořadí, jak a kdy jsou funkce volány při generování specializací operace.

Definování funkce funguje podobně jako při definování operace s tím rozdílem, že pro funkci nelze definovat žádné sousedící a řízené specializace.
Příklad:

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
Pokaždé, když je to možné, je vhodné napsat klasický Logic z pojmu Functions namísto operací, aby bylo možné snadněji použít v rámci operací.
Pokud jsme napsali `Square` jako operaci, například, kompilátor by nedokázal zaručit, že volání stejného vstupu by konzistentně vytvořilo stejné výstupy.

Pro podtržení rozdílu mezi funkcemi a operacemi zvažte problém klasického vzorkování náhodného čísla v rámci operace Q #:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Pokaždé, když se zavolá `U`, bude mít při `target`jinou akci.
Konkrétně kompilátor nemůže zaručit, že pokud jsme do `U`přidali deklaraci specializace `adjoint auto`, pak `U(target); Adjoint U(target);` fungovat jako identita (to znamená No-OP).
To je v rozporu s definicí sousedícího, které jsme viděli v [vektorech a maticích](xref:microsoft.quantum.concepts.vectors), což umožňuje automatické generování sousední specializace v rámci operace, kde jsme volali operaci <xref:microsoft.quantum.math.randomreal> by se přerušily záruky poskytované kompilátorem. <xref:microsoft.quantum.math.randomreal> je operace, pro kterou neexistuje žádná sousední nebo řízená verze.

Na druhé straně, povolení volání funkcí, jako je například `Square`, je bezpečné, v tom, že kompilátor může mít jistotu, že musí zachovávat vstup pouze pro `Square`, aby bylo možné zachovat stabilní výstup.
Proto izolování co nejvíc klasických logických funkcí do funkcí umožňuje snadno znovu použít tuto logiku v jiných funkcích a operacích.

## <a name="control-flow"></a>Tok řízení

V rámci operace nebo funkce se každý příkaz provede v uvedeném pořadí, podobně jako u nejběžnějších imperativních klasických jazyků.
Tento tok řízení lze změnit, ale třemi různými způsoby:

- Příkazy `if`
- `for` smyčky
- `repeat`-`until` smyčky

Podíváme se na to, dokud se nebudeme rozmluvit, [dokud neproběhne úspěšně (ru)](xref:microsoft.quantum.techniques.qubits#measurements) okruhy.
`if` a `for` konstrukce toku řízení, ale pokračujte známým smyslem většiny klasických programovacích jazyků.
Konkrétně příkaz `if` může podniknout určitou podmínku, za kterou může následovat jeden nebo více příkazů `elif` a může končit `else`:

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

Podobně `for` smyčky označují iteraci v rozsahu celých čísel nebo nad prvky pole:

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

Důležité je, `for` smyčky a příkazy `if` mohou být použity i v operacích, pro které jsou automaticky generovány specializace. V takovém případě sousedící smyčka smyčky `for` obrátí směr a převezme sousedícího typu každé iterace.
Tento postup se řídí principem "obuv-a-SOCKS": Pokud chcete vrátit zpět vložení do aplikace SOCKS a pak provést operaci, je nutné vrátit zpět na obuv a pak zrušit uvedení na SOCKS.
V takovém případě stále ještě méně se nedaří vyzkoušet a pořídit si své služby SOCKS, dokud budete mít pořád na svou obuv.

## <a name="operations-and-functions-as-first-class-values"></a>Operace a funkce jako hodnoty první třídy

Jednou z kritických postupů pro rozhodnutí o toku řízení a klasické logice pomocí funkcí místo operací je využití těchto operací a funkcí v Q # jsou *prvními třídami*.
To znamená, že jsou všechny hodnoty v jazyce v pravém.
Například následující je naprosto platný kód Q #, pokud je trochu nepřímá:

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

Hodnota proměnné `ourH` ve výše uvedeném fragmentu kódu je pak <xref:microsoft.quantum.intrinsic.h>operace, například tuto hodnotu můžeme zavolat jako jakoukoli jinou operaci.
To nám umožňuje psát operace, které jako součást svého vstupu přijímají operace, které vytvářejí koncepty toku řízení vyššího řádu.
Můžeme si například představit, že se má "čtvercová" operace aplikovat dvakrát na stejný cílový qubit.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

V tomto příkladu se šipka `=>`, která se zobrazí v typu `(Qubit => Unit)`, označuje, že vstupní pole `op` je operace, která přebírá jako svůj vstup typ `Qubit` a vytváří prázdnou řazenou kolekci členů jako svůj výstup.
Dále určíme vlastnosti tohoto typu operace, které obsahují informace o tom, které funktory jsou podporovány.
Operace typu `(Qubit => Unit)` nepodporuje ani `Adjoint` ani `Controlled` funktor. Pokud chceme indikovat, že operace tohoto typu musí podporovat například `Adjoint` funktor, je nutné ji deklarovat jako sousední. K tomu je potřeba použít anotaci `is Adj` k typu. Podobně `(Qubit => Unit is Ctl)` označuje, že operace tohoto typu podporuje `Controlled` funktor. Podíváme se, až budeme projednávat [typy v Q #](xref:microsoft.quantum.language.type-model) obecněji.

Teď zdůrazňujeme, že můžeme také vracet operace jako součást výstupů, takže můžeme izolovat některé druhy klasických podmíněných logických funkcí jako klasických funkcí, které v podobě operace vrátí popis programového množství.
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

Tato nová funkce je ve skutečnosti funkcí, v tom, že pokud ji zavoláte se stejnými hodnotami `hereBit` a `thereBit`, vrátíme vždycky stejnou operaci.
Proto lze dekodér bezpečně spustit uvnitř operací, aniž byste museli mít důvod na to, jak logika dekódování komunikuje s definicemi různých specializací operace.
To znamená, že jsme izolaci klasické logiky uvnitř funkce a zaručili kompilátor, že volání funkce může být přeobjednáno pomocí impunity, pokud je zachován vstup.

Funkce můžeme také považovat za hodnoty první třídy, protože se vám podíváme podrobněji na [operace a typy funkcí](#operations-and-functions-as-first-class-values).

## <a name="partially-applying-operations-and-functions"></a>Částečně se aplikují operace a funkce.

Díky funkcím, které vracejí operace, můžeme použít *částečnou aplikaci*, ve které můžeme zadat jednu nebo více částí vstupu do funkce nebo operace, aniž byste je skutečně volali. Například opakované volání `ApplyTwice` výše můžeme indikovat, že nechcete zadat hned, na které qubit by měla vstupní operace platit:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

V takovém případě místní proměnná `twiceOp` obsahuje částečně aplikované operace `ApplyTwice(op, _)`, kde jsou části vstupu, které ještě nebyly určeny, označeny `_`.
Když ve skutečnosti voláme `twiceOp` v dalším řádku, předáte jako vstup do částečně použité operace všechny zbývající části vstupu do původní operace.
Proto je výše uvedený fragment kódu prakticky shodný s tím, že se `ApplyTwice(op, target)` přímo, uložte pro to, že jsme zavedli novou místní proměnnou, která nám umožní zpoždění volání při poskytování některých částí vstupu.

Vzhledem k tomu, že operace, která byla částečně použita, není ve skutečnosti volána, dokud není poskytnut celý vstup, můžeme částečně použít operace i v rámci funkcí.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

V zásadě byla klasická logika v rámci `SquareOperation` mnohem více zapojena, ale je stále izolovaná od zbytku operace zárukami, které kompilátor může nabízet o funkcích.
Tento přístup se bude používat v rámci celé knihovny Q # pro vyjádření toku klasického řízení způsobem, který se dá snadno použít v rámci programu pro překročení úrovně.
