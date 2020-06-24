---
title: 'Řízení toku ve standardu Q # libararies'
description: 'Přečtěte si o operacích a funkcích řízení toku v knihovně Microsoft Q # Standard.'
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b41b3edd7a3e3ac13dbda106a869f4cba8183600
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274618"
---
# <a name="higher-order-control-flow"></a>Tok řízení vyššího řádu #

Jednou z primárních rolí standardní knihovny je usnadnit rychlé vyjádření vysoce kvalitních nápadů, jako jsou [programy](https://en.wikipedia.org/wiki/Quantum_programming)v počtu procesorů.
Proto Q # Canon poskytuje celou řadu různých konstrukcí řízení toku, z nichž každý je implementován pomocí částečného použití funkcí a operací.
Přejít okamžitě na příklad, zvažte případ, ve kterém jeden chce vytvořit "CNOT žebřík" v registru:

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

Tento model můžeme vyjádřit pomocí iterací a `for` smyček:

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

Tato funkce je vyjádřená v souvislosti s <xref:microsoft.quantum.canon.applytoeachca> funkcemi manipulace a polem, jako je <xref:microsoft.quantum.arrays.zip> to však mnohem kratší a snazší je přečíst:

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

Ve zbývající části tohoto oddílu nabídneme několik příkladů, jak používat různé operace řízení toku a funkce poskytované Canon pro komprimaci bezplatných programů.

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a>Použití operací a funkcí nad poli a rozsahy ##

Jednou z primárních abstrakcí, které poskytuje Canon, je iterace.
Předpokládejme například, že ve formuláři $U \otimes U \otimes \cdots \otimes U $ pro každou qubit jednotkovou $U $.
V Q # můžeme použít <xref:microsoft.quantum.arrays.indexrange> k reprezentaci jako smyčky v rámci `for` registru:

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation ApplyHadamardToAll(
    register : Qubit[])
: Unit is Adj + Ctl {
    for (qubit in register) {
        H(qubit);
    }
}
```

Tuto novou operaci pak můžeme použít, pokud `HAll(register)` chcete použít $H \Otimes H \otimes \cdots \Otimes H $.

To je nenáročné, ale zvláště ve větším algoritmu.
Tento přístup je navíc specializovaný na konkrétní operaci, kterou chceme použít na každou qubit.
Můžeme použít fakt, že tyto operace jsou prvními třídami, aby se tento algoritmus jednoznačně vyjádřil.

```qsharp
ApplyToEachCA(H, register);
```

Zde je přípona `CA` indikuje, že volání `ApplyToEach` je samoně sousedící a ovladatelné.
Proto, pokud `U` podporuje `Adjoint` a `Controlled` , jsou následující řádky ekvivalentní:

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

Konkrétně to znamená, že volání se `ApplyToEachCA` mohou objevit v operacích, pro které je automaticky generována sousední specializace.
Podobně <xref:microsoft.quantum.canon.applytoeachindex> je vhodný pro reprezentaci vzorů formuláře `U(0, targets[0]); U(1, targets[1]); ...` a nabízí verze pro každou kombinaci funktory, která je podporována jeho vstupem.

> [!TIP]
> `ApplyToEach`je typ – parametr, aby jej bylo možné použít s operacemi, které přijímají jiné vstupy než `Qubit` .
> Předpokládejme například, že `codeBlocks` je pole <xref:microsoft.quantum.errorcorrection.logicalregister> hodnot, které je třeba obnovit.
> Pak `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` použije chybovou opravu kódu `code` a funkci obnovení `recoveryFn` na každý blok nezávisle.
> To i pro klasické vstupy: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` použije rotaci $ \pi/$2 o $X $ následovaný otočením $PI/$3 o $Y $.

Q # Canon také poskytuje podporu pro klasické vzory výčtů, které jsou známé pro funkční programování.
Například <xref:microsoft.quantum.arrays.fold> implementuje vzor $f (f (s \_ {\Text{Initial}}, x \_ 0), x \_ 1), \dots) $ pro snížení funkce na seznam.
Tento model se dá použít k implementaci součtů, produktů, minima, Maxim a dalších takových funkcí:

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

Podobně funkce jako <xref:microsoft.quantum.arrays.mapped> a <xref:microsoft.quantum.arrays.mappedbyindex> lze použít k vyjádření konceptů programování funkcí v Q #.

## <a name="composing-operations-and-functions"></a>Vytváření operací a funkcí ##

Konstrukce toku řízení nabízené službou Canon využívají operace a funguje jako jejich vstupy, takže je užitečné, aby bylo možné vytvořit několik operací nebo funkcí do jediného možného volání.
Například vzor $UVU ^ {\dagger} $ je velmi běžný při programování v provozu, aby Canon poskytoval operaci <xref:microsoft.quantum.canon.applywith> jako abstrakci pro tento model.
Tato abstrakce také umožňuje efektivnější compliation do okruhů, protože `Controlled` v sekvenci `U(qubit); V(qubit); Adjoint U(qubit);` není nutné pracovat na každém z nich `U` .
Pokud to chcete vidět, nechejte $c (U) $ představovat jednotnou reprezentaci `Controlled U([control], target)` a nechte $c (v) $ definovat stejným způsobem.
Pak pro libovolný stav $ \ket{\psi} $, \begin{align} c (U) c (V) c (U) ^ \dagger \ket {1} \otimes \ket{\psi} & = \ket {1} \OTIMES (uvu ^ {\dagger} \ket{\psi}) \\ \\ & = (\boldone \otimes u) (c (V)) (\boldone \otimes U ^ \dagger) \ket {1} \otimes \ket{\psi}.
\end{align} podle definice `Controlled` .
Na druhé straně \begin{align} c (U) c (V) c (U) ^ \dagger \ket {0} \otimes \ket{\psi} & = \ket {0} \otimes \ket{\psi} \\ \\ & = \ket {0} \otimes (UU ^ \dagger \ket{\psi}) \\ \\ & = (\Boldone \otimes u) (c (V)) (\boldone \otimes U ^ \dagger) \ket {0} \otimes \ket{\psi}.
\end{align} podle linearity můžeme uzavřít, že tento způsob je možné pro všechny vstupní stavy $U $ out.
To znamená, $c (UVU ^ \dagger) = U c (V) U ^ \dagger $.
Vzhledem k tomu, že řízení operací může být všeobecně náročné, pomocí kontrolovaných variant, jako je, `WithC` a `WithCA` může pomoci snížit počet funktory ovládacího prvku, který je třeba použít.

> [!NOTE]
> Jednou z dalších podsekvencí $U $ je, že nemusíme ani znát, jak `Controlled` funktor použít `U` .
> `ApplyWithCA`Proto má slabší podpis, než může být očekáván:
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

Podobně <xref:microsoft.quantum.canon.bound> vytváří operace, které používají sekvenci dalších operací.
Například následující jsou ekvivalentní:

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

Kombinování se vzorci iterace může udělat tento význam hlavně:

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a>Kompozice časově uspořádaných ###

Dál se můžeme dál domyslet z řízení toku v souvislosti s částečnými aplikacemi a klasickými funkcemi a můžete modelovat dokonce poměrně sofistikované koncepty řízení toku v podobě klasického řízení toku.
Tato analogie je přesnější rozpoznáváním, že stejné operátory odpovídají přesně na vedlejší účinky volání operací, což znamená, že jakékoliv dekompozice smluvních operátorů v souvislosti s jinými stejnými operátory odpovídá vytváření konkrétní volací sekvence pro klasické podrutiny, které generují pokyny pro fungování jako konkrétní operátory.
V tomto zobrazení `Bound` je přesně reprezentace maticového produktu, protože `Bound([A, B])(target)` je ekvivalentní k `A(target); B(target);` , což zase volá sekvenci, která odpovídá $ba $.

Propracovanější příklad je [rozšíření Trotter – Suzuki](https://arxiv.org/abs/math-ph/0506007v1).
Jak je popsáno v části dynamické reprezentace generátoru [datových struktur](xref:microsoft.quantum.libraries.data-structures), rozšíření Trotter – Suzuki poskytuje obzvláště užitečný způsob vyjádření exponenciálních exponenciálních čísel matic.
Například použití rozšíření v jeho nejnižší objednávce znamená, že pro všechny operátory $A $ a $B $ tak, aby $A = A ^ \dagger $ a $B = B ^ \dagger $, \begin{align} \tag{★} \label{EQ: Trotter-Suzuki-0} \exp (i [A + B] t) = \ lim_ {n\to\infty} \left (\exp (i t/n) \exp (i B t/n) \right) ^ n.
\end{align} Colloquially to říká, že můžeme přibližně vyvíjet stav v části $A + B $ střídavě vyvíjené pomocí $A $ a $B $ samostatně.
Pokud reprezentujeme vývoj v rámci $A $ podle operace `A : (Double, Qubit[]) => Unit` , která se vztahuje $e ^ {i t A} $, pak je reprezentace rozšíření Trotter – Suzuki v souvislosti se změnou uspořádání sekvencí volání nejasná.
Konkrétní operace, jako je, `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` `A = U(0, _, _)` a `B = U(1, _, _)` , můžeme definovat novou operaci reprezentující celý celočíselný `U` čas v čase $t $ vygenerováním sekvencí formuláře.

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

V tuto chvíli teď můžeme mít k dispozici informace o rozšíření Trotter – Suzuki *bez odkazů na veškerou část*.
Rozšíření je efektivně velmi konkrétní vzor iterace, který motivuje $ \eqref{EQ: Trotter-Suzuki-0} $.
Tento vzor iterace implementuje <xref:microsoft.quantum.canon.decomposeintotimestepsca> :

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

Signatura `DecomposeIntoTimeStepsCA` následuje společný vzor v Q #, kde kolekce, které mohou být zálohovány buď pomocí polí, nebo něco, které výpočetní prvky za běhu jsou reprezentovány řazenými kolekcemi členů, jejichž první prvky jsou hodnoty, které `Int` určují jejich délku.

## <a name="putting-it-together-controlling-operations"></a>Vložení dohromady: řízení operací ##

Nakonec Canon staví na `Controlled` funktor tím, že poskytuje další způsoby pro podmínění operací s více než jednou.
Je běžné, zejména v případě aritmetických operací, pro podmínky operace výpočtu na základě jiných stavů, než je $ \ket{0\cdots 0} $.
Pomocí operací a funkcí ovládacího prvku, které jsou představené výše, můžeme v jednom příkazu využít obecnější podmínky.
Pojďme se pustit do toho, jak <xref:microsoft.quantum.canon.controlledonbitstring> to dělá (parametry typu sítě SAN), pak rozdělíme jednotlivé díly o jeden.
První věc, kterou je potřeba udělat, je definování operace, která ve skutečnosti dělá velkou zvedací implementaci ovládacího prvku na libovolný výpočetní stav.
Tuto operaci nebudeme volat přímo, ale přidáme `_` na začátek názvu, abychom zjistili, že se jedná o implementaci jiného konstruktoru jinde.

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

Všimněte si, že bereme řetězec bitů, který je reprezentován jako `Bool` pole, které používáme k určení podmíněného nastavování, které chceme použít pro operaci `oracle` , kterou jsme dali.
Vzhledem k tomu, že tato operace ve skutečnosti přímo dělá aplikaci, musíme také pořídit i cílové Registry, jak je znázorněno zde `Qubit[]` .

V dalším kroku Upozorňujeme, že řízení na výpočetním stavu $ \ket{\vec{s}} = \ket{s \_ 0 s \_ 1 \dots s \_ {n-1}} $ pro bitový řetězec $ \vec{s} $ se dá realizovat tak, že transformuje $ \ket{\vec{s}} $ do $ \ket{0\cdots 0} $.
Konkrétně $ \ket{\vec{s}} = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} \ket{0\cdots 0} $.
Protože $X ^ {\dagger} = X $, znamená to, že $ \ket{0\dots 0} = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} \ket{\vec{s}} $.
Proto můžeme použít $P = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} $, použít `Controlled oracle` a transformovat zpátky na $ \vec{s} $.
Tato konstrukce je přesně ta `ApplyWith` , proto zapište text naší nové operace odpovídajícím způsobem:

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

Tady jsme použili <xref:microsoft.quantum.canon.applypaulifrombitstring> pro použití s nástrojem $P $, částečně aplikované na jeho cíl `ApplyWith` .
Všimněte si ale, že potřebujeme transformovat registraci *ovládacího prvku* do našeho formuláře, takže částečně použijeme interní operaci `(Controlled oracle)` na *cíli*.
Tato činnost ponechá `ApplyWith` v závorce řídicího registru pomocí $P $, přesně podle potřeby.

V tuto chvíli jsme se mohli udělat, ale nevyhovuje tomu, že se naše nová operace neshoduje s tím, jako když použijete `Controlled` funktor.
Proto jsme dokončili definování našeho nového konceptu toku řízení vytvořením funkce, která bude mít pod kontrolou Oracle a který vrátí novou operaci.
Díky tomu by naše nová funkce vypadala a vypadala velmi dobře `Controlled` , což ilustruje, že můžeme snadno definovat výkonné nové konstrukce toku ovládacích prvků pomocí Q # a Canon společně:

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
