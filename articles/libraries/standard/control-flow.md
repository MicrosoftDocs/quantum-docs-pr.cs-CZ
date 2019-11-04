---
title: 'Q # Standard knihovny – řízení a flow | Microsoft Docs'
description: 'Q # Standard knihovny – řízení a flow'
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5e865dbb48029724b6f507ecb63b85d10d80c9a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185643"
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

Tento model můžeme vyjádřit pomocí iterací a smyčky `for`:

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

Tato funkce je vyjádřená v souvislosti s funkcemi manipulace <xref:microsoft.quantum.canon.applytoeachca> a Array, jako je například <xref:microsoft.quantum.arrays.zip>, ale to je mnohem kratší a snazší si je přečíst:

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

Ve zbývající části tohoto oddílu nabídneme několik příkladů, jak používat různé operace řízení toku a funkce poskytované Canon pro komprimaci bezplatných programů.

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a>Použití operací a funkcí nad poli a rozsahy ##

Jednou z primárních abstrakcí, které poskytuje Canon, je iterace.
Předpokládejme například, že ve formuláři $U \otimes U \otimes \cdots \otimes U $ pro každou qubit jednotkovou $U $.
V Q # můžeme použít <xref:microsoft.quantum.arrays.indexrange> k tomu, aby představovala jako `for` smyčku v rámci registru:

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation HAll(register : Qubit[]) : Unit 
is Adj + Ctl {

    for (qubit in register) {
        H(qubit);
    }
}
```

Tuto novou operaci pak můžeme použít jako `HAll(register)` k použití $H \otimes H \otimes \cdots \otimes H $.

To je nenáročné, ale zvláště ve větším algoritmu.
Tento přístup je navíc specializovaný na konkrétní operaci, kterou chceme použít na každou qubit.
Můžeme použít fakt, že tyto operace jsou prvními třídami, aby se tento algoritmus jednoznačně vyjádřil.

```qsharp
ApplyToEachCA(H, register);
```

Zde `CA` přípona indikuje, že volání `ApplyToEach` je sama o sobě sousedící a ovladatelné.
Proto pokud `U` podporuje `Adjoint` a `Controlled`, jsou následující řádky ekvivalentní:

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

Konkrétně to znamená, že volání `ApplyToEachCA` se mohou objevit v operacích, pro které se automaticky generuje specializace sousedící-.
Podobně <xref:microsoft.quantum.canon.applytoeachindex> je užitečné pro reprezentaci vzorů `U(0, targets[0]); U(1, targets[1]); ...`formuláře a nabízí verze pro každou kombinaci funktory podporovaná jejich vstupem.

> [!TIP]
> `ApplyToEach` je typ – parametrizované tak, aby ho bylo možné použít s operacemi, které přebírají jiné vstupy než `Qubit`.
> Předpokládejme například, že `codeBlocks` je pole <xref:microsoft.quantum.errorcorrection.logicalregister> hodnot, které je nutné obnovit.
> Pak `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` použije chybovou `code` kódu a funkci obnovení `recoveryFn` pro každý blok nezávisle na sobě.
> To i pro klasické vstupy: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` použije rotaci $ \pi/$2 o $X $ následovaných otočením $pi/$3 o $Y $.

Q # Canon také poskytuje podporu pro klasické vzory výčtů, které jsou známé pro funkční programování.
Například <xref:microsoft.quantum.arrays.fold> implementuje vzor $f (f (s\_{\Text{Initial}}, x\_0), x\_1), \dots) $ pro snížení funkce na seznam.
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
Například vzor $UVU ^ {\dagger} $ je mimořádně běžný při programování, což znamená, že Canon poskytuje operaci <xref:microsoft.quantum.canon.applywith> jako abstrakci pro tento model.
Tato abstrakce také umožňuje efektivnější compliation do okruhů, protože `Controlled` pracující na sekvenci `U(qubit); V(qubit); Adjoint U(qubit);` nemusí jednat u každého `U`.
Pokud to chcete vidět, nechť $c (U) $ být jednotkou reprezentující `Controlled U([control], target)` a nechte $c (V) $ definovat stejným způsobem.
Pak pro libovolný stav $ \ket{\psi} $, \begin{align} c (U) c (V) c (U) ^ \dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU ^ {\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c (V)) (\boldone \otimes U ^ \dagger) \ KET{1} \otimes \ket{\psi}.
\end{align} podle definice `Controlled`.
Na druhé straně \begin{align} c (U) c (V) c (U) ^ \dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU ^ \dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c ( V)) (\boldone \otimes U ^ \dagger) \ket{0} \otimes \ket{\psi}.
\end{align} podle linearity můžeme uzavřít, že tento způsob je možné pro všechny vstupní stavy $U $ out.
To znamená, $c (UVU ^ \dagger) = U c (V) U ^ \dagger $.
Vzhledem k tomu, že řízení operací může být všeobecně náročné, pomocí kontrolovaných variant, jako je například `WithC` a `WithCA` může pomoci snížit počet funktory ovládacího prvku, který je třeba použít.

> [!NOTE]
> Jednou z dalších uspořádání $U $ je, že nepotřebujeme ani na to, jak použít `Controlled` funktor na `U`.
> `ApplyWithCA` proto má slabší podpis, než se může očekávat:
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

Podobně <xref:microsoft.quantum.canon.bind> vytváří operace, které používají sekvenci dalších operací.
Například následující jsou ekvivalentní:

```qsharp
H(qubit); X(qubit);
Bind([H, X], qubit);
```

Kombinování se vzorci iterace může udělat tento význam hlavně:

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bind([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a>Kompozice časově uspořádaných ###

Dál se můžeme dál domyslet z řízení toku v souvislosti s částečnými aplikacemi a klasickými funkcemi a můžete modelovat dokonce poměrně sofistikované koncepty řízení toku v podobě klasického řízení toku.
Tato analogie je přesnější rozpoznáváním, že jednotní operátoři odpovídají přesně vedlejším účinkům operací volání, což znamená, že jakékoliv dekompozice operátorů s jednou jednotkou, která je v souladu s jinými stejnými operátory, odpovídá vytvoření konkrétního sekvence volání pro klasické podrutiny, které generují pokyny, aby fungovaly jako konkrétní jednotkové operátory.
V tomto zobrazení je `Bind` přesně reprezentace maticového produktu, protože `Bind([A, B])(target)` je ekvivalentem `A(target); B(target);`, což zase volá sekvenci, která odpovídá $BA $.

Propracovanější příklad je [rozšíření Trotter – Suzuki](https://arxiv.org/abs/math-ph/0506007v1).
Jak je popsáno v části dynamické reprezentace generátoru [datových struktur](xref:microsoft.quantum.libraries.data-structures), rozšíření Trotter – Suzuki poskytuje obzvláště užitečný způsob vyjádření exponenciálních exponenciálních čísel matic.
Například použití rozšíření v jeho nejnižší objednávce znamená, že pro všechny operátory $A $ a $B $, například $A = ^ \dagger $ a $B = B ^ \dagger $, \begin{align} \tag{★} \label{EQ: Trotter-Suzuki-0} \exp (i [A + B] t) = \lim_{n\to\infty} \left (\exp (i t/n) \exp (i B t/n ) \right) ^ n.
\end{align} Colloquially to říká, že můžeme přibližně vyvíjet stav v části $A + B $ střídavě vyvíjené pomocí $A $ a $B $ samostatně.
Pokud reprezentujeme vývoj v rámci $A $ podle operace `A : (Double, Qubit[]) => Unit`, která platí $e ^ {i t A} $, pak je reprezentace rozšíření Trotter – Suzuki v souvislosti se změnou uspořádání volacích sekvencí jasné.
V důsledku konkrétní operace `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` tak, že `A = U(0, _, _)` a `B = U(1, _, _)`můžeme definovat novou operaci reprezentující celočíselnou `U` v čase $t $ vygenerováním sekvencí formuláře.

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

V tuto chvíli teď můžeme mít k dispozici informace o rozšíření Trotter – Suzuki *bez odkazů na veškerou část*.
Rozšíření je efektivně velmi konkrétní vzor iterace, který motivuje $ \eqref{EQ: Trotter-Suzuki-0} $.
Tento vzor iterace je implementován pomocí <xref:microsoft.quantum.canon.decomposeintotimestepsca>:

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

Podpis `DecomposeIntoTimeStepsCA` následuje za běžným vzorem v Q #, kde kolekce, které mohou být zálohovány buď pomocí polí, nebo něco, které výpočetní prvky v průběhu jsou reprezentovány řazenými kolekcemi členů, jejichž první prvky jsou `Int` hodnoty, které určují jejich délku.

## <a name="putting-it-together-controlling-operations"></a>Vložení dohromady: řízení operací ##

Nakonec se Canon staví na `Controlled` funktor tím, že poskytuje další způsoby pro podmínění operací s více než jednou.
Je běžné, zejména v případě aritmetických operací, pro podmínky operace výpočtu na základě jiných stavů, než je $ \ket{0\cdots 0} $.
Pomocí operací a funkcí ovládacího prvku, které jsou představené výše, můžeme v jednom příkazu využít obecnější podmínky.
Pojďme se pustit do toho, jak <xref:microsoft.quantum.canon.controlledonbitstring> to dělá (parametry typu San), pak rozdělíme jeden o jeden.
První věc, kterou je potřeba udělat, je definování operace, která ve skutečnosti dělá velkou zvedací implementaci ovládacího prvku na libovolný výpočetní stav.
Tuto operaci nebudeme volat přímo, ale přidáme `_` na začátek názvu, abychom zjistili, že se jedná o implementaci jiného konstruktoru jinde.

```qsharp
operation _ControlledOnBitString(
        bits : Bool[],
        oracle: (Qubit[] => Unit is Adj + Ctl),
        controlRegister : Qubit[],
        targetRegister: Qubit[]) 
: Unit 
is Adj + Ctl {
```

Všimněte si, že bereme řetězec bitů, který je reprezentován jako `Bool` pole, které používáme k určení podmíněného nastavování, které chceme použít pro danou operaci `oracle`.
Vzhledem k tomu, že tato operace ve skutečnosti přímo dělá aplikaci, musíme také přebírat kontrolní a cílové Registry, jak je znázorněno zde `Qubit[]`.

V dalším kroku si všimněte, že řízení na základě stavu výpočtu $ \ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n-1}} $ pro bitový řetězec $ \vec{s} $ se dá realizovat tak, že transformuje $ \ket{\vec{s}} $ na $ \ket{0\cdots 0} $.
Konkrétně $ \ket{\vec{s}} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{0\cdots 0} $.
Protože $X ^ {\dagger} = X $, znamená to, že $ \ket{0\dots 0} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{\vec{s}} $.
Proto můžeme použít $P = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} $, použít `Controlled oracle`a transformovat zpátky na $ \vec{s} $.
Tato konstrukce je přesně `ApplyWith`, proto zapište text naší nové operace odpovídajícím způsobem:

```qsharp
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

V tomto případě jsme použili <xref:microsoft.quantum.canon.applypaulifrombitstring> pro použití $P $, částečně se používá u svého cíle pro použití s `ApplyWith`.
Upozorňujeme však, že potřebujeme transformovat registraci *ovládacího prvku* do našeho formuláře, takže částečně použijeme `(Controlled oracle)` vnitřní operace na *cíli*.
To ponechá `ApplyWith` v závorkách registraci ovládacího prvku s $P $, přesně podle potřeby.

V tuto chvíli jsme se mohli udělat, ale nevyhovuje tomu, že se naše nová operace neshoduje s tím, jako je použití `Controlled` funktor.
Proto jsme dokončili definování našeho nového konceptu toku řízení vytvořením funkce, která bude mít pod kontrolou Oracle a který vrátí novou operaci.
Díky tomu naše nová funkce vypadá a je příliš velká, jako `Controlled`, což ilustruje, že můžeme snadno definovat výkonné nové konstrukce toku ovládacích prvků pomocí Q # a Canon spolu s těmito možnostmi:

```qsharp
function ControlledOnBitString(
        bits : Bool[],
        oracle: (Qubit[] => Unit is Adj + Ctl)) 
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
