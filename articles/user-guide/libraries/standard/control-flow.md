---
title: Řízení toku ve Q# standardním libararies
description: Přečtěte si o operacích a funkcích řízení toku v Q# knihovně Microsoft Standard.
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1cfef50cf2bbecd2043972a662edd8120c5570ec
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835617"
---
# <a name="higher-order-control-flow"></a><span data-ttu-id="c9532-103">Tok řízení vyššího řádu</span><span class="sxs-lookup"><span data-stu-id="c9532-103">Higher-Order Control Flow</span></span> #

<span data-ttu-id="c9532-104">Jednou z primárních rolí standardní knihovny je usnadnit rychlé vyjádření vysoce kvalitních nápadů, jako jsou [programy](https://en.wikipedia.org/wiki/Quantum_programming)v počtu procesorů.</span><span class="sxs-lookup"><span data-stu-id="c9532-104">One of the primary roles of the standard library is to make it easier to express high-level algorithmic ideas as [quantum programs](https://en.wikipedia.org/wiki/Quantum_programming).</span></span>
<span data-ttu-id="c9532-105">Proto Q# Canon poskytuje celou řadu různých konstrukcí řízení toku, z nichž každý je implementován pomocí částečného použití funkcí a operací.</span><span class="sxs-lookup"><span data-stu-id="c9532-105">Thus, the Q# canon provides a variety of different flow control constructs, each implemented using partial application of functions and operations.</span></span>
<span data-ttu-id="c9532-106">Přejít okamžitě na příklad, zvažte případ, ve kterém jeden chce vytvořit "CNOT žebřík" v registru:</span><span class="sxs-lookup"><span data-stu-id="c9532-106">Jumping immediately into an example, consider the case in which one wants to construct a "CNOT ladder" on a register:</span></span>

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

<span data-ttu-id="c9532-107">Tento model můžeme vyjádřit pomocí iterací a `for` smyček:</span><span class="sxs-lookup"><span data-stu-id="c9532-107">We can express this pattern by using iteration and `for` loops:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

<span data-ttu-id="c9532-108">Tato funkce je vyjádřená v souvislosti s <xref:microsoft.quantum.canon.applytoeachca> funkcemi manipulace a polem, jako je <xref:microsoft.quantum.arrays.zip> to však mnohem kratší a snazší je přečíst:</span><span class="sxs-lookup"><span data-stu-id="c9532-108">Expressed in terms of <xref:microsoft.quantum.canon.applytoeachca> and array manipulation functions such as <xref:microsoft.quantum.arrays.zip>, however, this is much shorter and easier to read:</span></span>

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

<span data-ttu-id="c9532-109">Ve zbývající části tohoto oddílu nabídneme několik příkladů, jak používat různé operace řízení toku a funkce poskytované Canon pro komprimaci bezplatných programů.</span><span class="sxs-lookup"><span data-stu-id="c9532-109">In the rest of this section, we will provide a number of examples of how to use the various flow control operations and functions provided by the canon to compactly express quantum programs.</span></span>

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a><span data-ttu-id="c9532-110">Použití operací a funkcí nad poli a rozsahy</span><span class="sxs-lookup"><span data-stu-id="c9532-110">Applying Operations and Functions over Arrays and Ranges</span></span> ##

<span data-ttu-id="c9532-111">Jednou z primárních abstrakcí, které poskytuje Canon, je iterace.</span><span class="sxs-lookup"><span data-stu-id="c9532-111">One of the primary abstractions provided by the canon is that of iteration.</span></span>
<span data-ttu-id="c9532-112">Předpokládejme například, že ve formuláři $U \otimes U \otimes \cdots \otimes U $ pro každou qubit jednotkovou $U $.</span><span class="sxs-lookup"><span data-stu-id="c9532-112">For instance, consider a unitary of the form $U \otimes U \otimes \cdots \otimes U$ for a single-qubit unitary $U$.</span></span>
<span data-ttu-id="c9532-113">V nástroji Q# můžeme použít <xref:microsoft.quantum.arrays.indexrange> k reprezentaci jako smyčky v rámci `for` registru:</span><span class="sxs-lookup"><span data-stu-id="c9532-113">In Q#, we might use <xref:microsoft.quantum.arrays.indexrange> to represent this as as a `for` loop over a register:</span></span>

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

<span data-ttu-id="c9532-114">Tuto novou operaci pak můžeme použít, pokud `HAll(register)` chcete použít $H \Otimes H \otimes \cdots \Otimes H $.</span><span class="sxs-lookup"><span data-stu-id="c9532-114">We can then use this new operation as `HAll(register)` to apply $H \otimes H \otimes \cdots \otimes H$.</span></span>

<span data-ttu-id="c9532-115">To je nenáročné, ale zvláště ve větším algoritmu.</span><span class="sxs-lookup"><span data-stu-id="c9532-115">This is cumbersome to do, however, especially in a larger algorithm.</span></span>
<span data-ttu-id="c9532-116">Tento přístup je navíc specializovaný na konkrétní operaci, kterou chceme použít na každou qubit.</span><span class="sxs-lookup"><span data-stu-id="c9532-116">Moreover, this approach is specialized to the particular operation that we wish to apply to each qubit.</span></span>
<span data-ttu-id="c9532-117">Můžeme použít fakt, že tyto operace jsou prvními třídami, aby se tento algoritmus jednoznačně vyjádřil.</span><span class="sxs-lookup"><span data-stu-id="c9532-117">We can use the fact that operations are first-class to express this algorithmic concept more explicitly:</span></span>

```qsharp
ApplyToEachCA(H, register);
```

<span data-ttu-id="c9532-118">Zde je přípona `CA` indikuje, že volání `ApplyToEach` je samoně sousedící a ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="c9532-118">Here, the suffix `CA` indicates that the call to `ApplyToEach` is itself adjointable and controllable.</span></span>
<span data-ttu-id="c9532-119">Proto, pokud `U` podporuje `Adjoint` a `Controlled` , jsou následující řádky ekvivalentní:</span><span class="sxs-lookup"><span data-stu-id="c9532-119">Thus, if `U` supports `Adjoint` and `Controlled`, the following lines are equivalent:</span></span>

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

<span data-ttu-id="c9532-120">Konkrétně to znamená, že volání se `ApplyToEachCA` mohou objevit v operacích, pro které je automaticky generována sousední specializace.</span><span class="sxs-lookup"><span data-stu-id="c9532-120">In particular, this means that calls to `ApplyToEachCA` can appear in operations for which an adjoint specialization is auto-generated.</span></span>
<span data-ttu-id="c9532-121">Podobně <xref:microsoft.quantum.canon.applytoeachindex> je vhodný pro reprezentaci vzorů formuláře `U(0, targets[0]); U(1, targets[1]); ...` a nabízí verze pro každou kombinaci funktory, která je podporována jeho vstupem.</span><span class="sxs-lookup"><span data-stu-id="c9532-121">Similarly, <xref:microsoft.quantum.canon.applytoeachindex> is useful for representing patterns of the form `U(0, targets[0]); U(1, targets[1]); ...`, and offers versions for each combination of functors supported by its input.</span></span>

> [!TIP]
> <span data-ttu-id="c9532-122">`ApplyToEach` je typ – parametr, aby jej bylo možné použít s operacemi, které přijímají jiné vstupy než `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="c9532-122">`ApplyToEach` is type-parameterized such that it can be used with operations that take inputs other than `Qubit`.</span></span>
> <span data-ttu-id="c9532-123">Předpokládejme například, že `codeBlocks` je pole <xref:microsoft.quantum.errorcorrection.logicalregister> hodnot, které je třeba obnovit.</span><span class="sxs-lookup"><span data-stu-id="c9532-123">For example, suppose that `codeBlocks` is an array of <xref:microsoft.quantum.errorcorrection.logicalregister> values that need to be recovered.</span></span>
> <span data-ttu-id="c9532-124">Pak `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` použije chybovou opravu kódu `code` a funkci obnovení `recoveryFn` na každý blok nezávisle.</span><span class="sxs-lookup"><span data-stu-id="c9532-124">Then `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` will apply the error-correcting code `code` and recovery function `recoveryFn` to each block independently.</span></span>
> <span data-ttu-id="c9532-125">To i pro klasické vstupy: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` použije rotaci $ \pi/$2 o $X $ následovaný otočením $PI/$3 o $Y $.</span><span class="sxs-lookup"><span data-stu-id="c9532-125">This holds even for classical inputs: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` will apply a rotation of $\pi / 2$ about $X$ followed by a rotation of $pi / 3$ about $Y$.</span></span>

<span data-ttu-id="c9532-126">Q#Canon také poskytuje podporu pro klasické vzory výčtů, které jsou známé pro funkční programování.</span><span class="sxs-lookup"><span data-stu-id="c9532-126">The Q# canon also provides support for classical enumeration patterns familiar to functional programming.</span></span>
<span data-ttu-id="c9532-127">Například <xref:microsoft.quantum.arrays.fold> implementuje vzor $f (f (s \_ {\Text{Initial}}, x \_ 0), x \_ 1), \dots) $ pro snížení funkce na seznam.</span><span class="sxs-lookup"><span data-stu-id="c9532-127">For instance, <xref:microsoft.quantum.arrays.fold> implements the pattern $f(f(f(s\_{\text{initial}}, x\_0), x\_1), \dots)$ for reducing a function over a list.</span></span>
<span data-ttu-id="c9532-128">Tento model se dá použít k implementaci součtů, produktů, minima, Maxim a dalších takových funkcí:</span><span class="sxs-lookup"><span data-stu-id="c9532-128">This pattern can be used to implement sums, products, minima, maxima and other such functions:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

<span data-ttu-id="c9532-129">Podobně funkce jako <xref:microsoft.quantum.arrays.mapped> a <xref:microsoft.quantum.arrays.mappedbyindex> lze použít pro vyjádření konceptů funkčního programování v Q# .</span><span class="sxs-lookup"><span data-stu-id="c9532-129">Similarly, functions like <xref:microsoft.quantum.arrays.mapped> and <xref:microsoft.quantum.arrays.mappedbyindex> can be used to express functional programming concepts in Q#.</span></span>

## <a name="composing-operations-and-functions"></a><span data-ttu-id="c9532-130">Vytváření operací a funkcí</span><span class="sxs-lookup"><span data-stu-id="c9532-130">Composing Operations and Functions</span></span> ##

<span data-ttu-id="c9532-131">Konstrukce toku řízení nabízené službou Canon využívají operace a funguje jako jejich vstupy, takže je užitečné, aby bylo možné vytvořit několik operací nebo funkcí do jediného možného volání.</span><span class="sxs-lookup"><span data-stu-id="c9532-131">The control flow constructs offered by the canon take operations and functions as their inputs, such that it is helpful to be able to compose several operations or functions into a single callable.</span></span>
<span data-ttu-id="c9532-132">Například vzor $UVU ^ {\dagger} $ je velmi běžný při programování v provozu, aby Canon poskytoval operaci <xref:microsoft.quantum.canon.applywith> jako abstrakci pro tento model.</span><span class="sxs-lookup"><span data-stu-id="c9532-132">For instance, the pattern $UVU^{\dagger}$ is extremely common in quantum programming, such that the canon provides the operation <xref:microsoft.quantum.canon.applywith> as an abstraction for this pattern.</span></span>
<span data-ttu-id="c9532-133">Tato abstrakce také umožňuje efektivnější compliation do okruhů, protože `Controlled` v sekvenci `U(qubit); V(qubit); Adjoint U(qubit);` není nutné pracovat na každém z nich `U` .</span><span class="sxs-lookup"><span data-stu-id="c9532-133">This abstraction also allows for more efficient compliation into circuits, as `Controlled` acting on the sequence `U(qubit); V(qubit); Adjoint U(qubit);` does not need to act on each `U`.</span></span>
<span data-ttu-id="c9532-134">Pokud to chcete vidět, nechejte $c (U) $ představovat jednotnou reprezentaci `Controlled U([control], target)` a nechte $c (v) $ definovat stejným způsobem.</span><span class="sxs-lookup"><span data-stu-id="c9532-134">To see this, let $c(U)$ be the unitary representing `Controlled U([control], target)` and let $c(V)$ be defined in the same way.</span></span>
<span data-ttu-id="c9532-135">Pak pro libovolný stav $ \ket{\psi} $, \begin{align} c (U) c (V) c (U) ^ \dagger \ket {1} \otimes \ket{\psi} & = \ket {1} \OTIMES (uvu ^ {\dagger} \ket{\psi}) \\ \\ & = (\boldone \otimes u) (c (V)) (\boldone \otimes U ^ \dagger) \ket {1} \otimes \ket{\psi}.</span><span class="sxs-lookup"><span data-stu-id="c9532-135">Then for an arbitrary state $\ket{\psi}$, \begin{align} c(U) c(V) c(U)^\dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU^{\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{1} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="c9532-136">\end{align} podle definice `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="c9532-136">\end{align} by the definition of `Controlled`.</span></span>
<span data-ttu-id="c9532-137">Na druhé straně \begin{align} c (U) c (V) c (U) ^ \dagger \ket {0} \otimes \ket{\psi} & = \ket {0} \otimes \ket{\psi} \\ \\ & = \ket {0} \otimes (UU ^ \dagger \ket{\psi}) \\ \\ & = (\Boldone \otimes u) (c (V)) (\boldone \otimes U ^ \dagger) \ket {0} \otimes \ket{\psi}.</span><span class="sxs-lookup"><span data-stu-id="c9532-137">On the other hand, \begin{align} c(U) c(V) c(U)^\dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU^\dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{0} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="c9532-138">\end{align} podle linearity můžeme uzavřít, že tento způsob je možné pro všechny vstupní stavy $U $ out.</span><span class="sxs-lookup"><span data-stu-id="c9532-138">\end{align} By linearity, we can conclude that we can factor $U$ out in this way for all input states.</span></span>
<span data-ttu-id="c9532-139">To znamená, $c (UVU ^ \dagger) = U c (V) U ^ \dagger $.</span><span class="sxs-lookup"><span data-stu-id="c9532-139">That is, $c(UVU^\dagger) = U c(V) U^\dagger$.</span></span>
<span data-ttu-id="c9532-140">Vzhledem k tomu, že řízení operací může být všeobecně náročné, pomocí kontrolovaných variant, jako je, `WithC` a `WithCA` může pomoci snížit počet funktory ovládacího prvku, který je třeba použít.</span><span class="sxs-lookup"><span data-stu-id="c9532-140">Since controlling operations can be expensive in general, using controlled variants such as `WithC` and `WithCA` can help reduce the number of control functors that need to be applied.</span></span>

> [!NOTE]
> <span data-ttu-id="c9532-141">Jednou z dalších podsekvencí $U $ je, že nemusíme ani znát, jak `Controlled` funktor použít `U` .</span><span class="sxs-lookup"><span data-stu-id="c9532-141">One other consequence of factoring out $U$ is that we need not even know how to apply the `Controlled` functor to `U`.</span></span>
> <span data-ttu-id="c9532-142">`ApplyWithCA` Proto má slabší podpis, než může být očekáván:</span><span class="sxs-lookup"><span data-stu-id="c9532-142">`ApplyWithCA` therefore has a weaker signature than might be expected:</span></span>
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

<span data-ttu-id="c9532-143">Podobně <xref:microsoft.quantum.canon.bound> vytváří operace, které používají sekvenci dalších operací.</span><span class="sxs-lookup"><span data-stu-id="c9532-143">Similarly, <xref:microsoft.quantum.canon.bound> produces operations which apply a sequence of other operations in turn.</span></span>
<span data-ttu-id="c9532-144">Například následující jsou ekvivalentní:</span><span class="sxs-lookup"><span data-stu-id="c9532-144">For instance, the following are equivalent:</span></span>

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

<span data-ttu-id="c9532-145">Kombinování se vzorci iterace může udělat tento význam hlavně:</span><span class="sxs-lookup"><span data-stu-id="c9532-145">Combining with iteration patterns can make this especially useful:</span></span>

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a><span data-ttu-id="c9532-146">Kompozice časově uspořádaných</span><span class="sxs-lookup"><span data-stu-id="c9532-146">Time-Ordered Composition</span></span> ###

<span data-ttu-id="c9532-147">Dál se můžeme dál domyslet z řízení toku v souvislosti s částečnými aplikacemi a klasickými funkcemi a můžete modelovat dokonce poměrně sofistikované koncepty řízení toku v podobě klasického řízení toku.</span><span class="sxs-lookup"><span data-stu-id="c9532-147">We can go still further by thinking of flow control in terms of partial application and classical functions, and can model even fairly sophisticated quantum concepts in terms of classical flow control.</span></span>
<span data-ttu-id="c9532-148">Tato analogie je přesnější rozpoznáváním, že stejné operátory odpovídají přesně na vedlejší účinky volání operací, což znamená, že jakékoliv dekompozice smluvních operátorů v souvislosti s jinými stejnými operátory odpovídá vytváření konkrétní volací sekvence pro klasické podrutiny, které generují pokyny pro fungování jako konkrétní operátory.</span><span class="sxs-lookup"><span data-stu-id="c9532-148">This analogy is made precise by the recognition that unitary operators correspond exactly to the side effects of calling operations, such that any decomposition of unitary operators in terms of other unitary operators corresponds to constructing a particular calling sequence for classical subroutines which emit instructions to act as particular unitary operators.</span></span>
<span data-ttu-id="c9532-149">V tomto zobrazení `Bound` je přesně reprezentace maticového produktu, protože `Bound([A, B])(target)` je ekvivalentní k `A(target); B(target);` , což zase volá sekvenci, která odpovídá $ba $.</span><span class="sxs-lookup"><span data-stu-id="c9532-149">Under this view, `Bound` is precisely the representation of the matrix product, since `Bound([A, B])(target)` is equivalent to `A(target); B(target);`, which in turn is the calling sequence corresponding to $BA$.</span></span>

<span data-ttu-id="c9532-150">Propracovanější příklad je [rozšíření Trotter – Suzuki](https://arxiv.org/abs/math-ph/0506007v1).</span><span class="sxs-lookup"><span data-stu-id="c9532-150">A more sophisticated example is the [Trotter–Suzuki expansion](https://arxiv.org/abs/math-ph/0506007v1).</span></span>
<span data-ttu-id="c9532-151">Jak je popsáno v části dynamické reprezentace generátoru [datových struktur](xref:microsoft.quantum.libraries.data-structures), rozšíření Trotter – Suzuki poskytuje obzvláště užitečný způsob vyjádření exponenciálních exponenciálních čísel matic.</span><span class="sxs-lookup"><span data-stu-id="c9532-151">As discussed in the Dynamical Generator Representation section of [data structures](xref:microsoft.quantum.libraries.data-structures), the Trotter–Suzuki expansion provides a particularly useful way of expressing matrix exponentials.</span></span>
<span data-ttu-id="c9532-152">Například použití rozšíření v jeho nejnižší objednávce znamená, že pro všechny operátory $A $ a $B $ tak, aby $A = A ^ \dagger $ a $B = B ^ \dagger $, \begin{align} \tag{★} \label{EQ: Trotter-Suzuki-0} \exp (i [A + B] t) = \ lim_ {n\to\infty} \left (\exp (i t/n) \exp (i B t/n) \right) ^ n.</span><span class="sxs-lookup"><span data-stu-id="c9532-152">For instance, applying the expansion at its lowest order yields that for any operators $A$ and $B$ such that $A = A^\dagger$ and $B = B^\dagger$, \begin{align} \tag{★} \label{eq:trotter-suzuki-0} \exp(i [A + B] t) = \lim_{n\to\infty} \left(\exp(i A t / n) \exp(i B t / n)\right)^n.</span></span>
<span data-ttu-id="c9532-153">\end{align} Colloquially to říká, že můžeme přibližně vyvíjet stav v části $A + B $ střídavě vyvíjené pomocí $A $ a $B $ samostatně.</span><span class="sxs-lookup"><span data-stu-id="c9532-153">\end{align} Colloquially, this says that we can approximately evolve a state under $A + B$ by alternately evolving under $A$ and $B$ alone.</span></span>
<span data-ttu-id="c9532-154">Pokud reprezentujeme vývoj v rámci $A $ podle operace `A : (Double, Qubit[]) => Unit` , která se vztahuje $e ^ {i t A} $, pak je reprezentace rozšíření Trotter – Suzuki v souvislosti se změnou uspořádání sekvencí volání nejasná.</span><span class="sxs-lookup"><span data-stu-id="c9532-154">If we represent evolution under $A$ by an operation `A : (Double, Qubit[]) => Unit` that applies $e^{i t A}$, then the representation of the Trotter–Suzuki expansion in terms of rearranging calling sequences becomes clear.</span></span>
<span data-ttu-id="c9532-155">Konkrétní operace, jako je, `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` `A = U(0, _, _)` a `B = U(1, _, _)` , můžeme definovat novou operaci reprezentující celý celočíselný `U` čas v čase $t $ vygenerováním sekvencí formuláře.</span><span class="sxs-lookup"><span data-stu-id="c9532-155">Concretely, given an operation `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` such that `A = U(0, _, _)` and `B = U(1, _, _)`, we can define a new operation representing the integral of `U` at time $t$ by generating sequences of the form</span></span>

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

<span data-ttu-id="c9532-156">V tuto chvíli teď můžeme mít k dispozici informace o rozšíření Trotter – Suzuki *bez odkazů na veškerou část*.</span><span class="sxs-lookup"><span data-stu-id="c9532-156">At this point, we can now reason about the Trotter–Suzuki expansion *without reference to quantum mechanics at all*.</span></span>
<span data-ttu-id="c9532-157">Rozšíření je efektivně velmi konkrétní vzor iterace, který motivuje $ \eqref{EQ: Trotter-Suzuki-0} $.</span><span class="sxs-lookup"><span data-stu-id="c9532-157">The expansion is effectively a very particular iteration pattern motivated by $\eqref{eq:trotter-suzuki-0}$.</span></span>
<span data-ttu-id="c9532-158">Tento vzor iterace implementuje <xref:microsoft.quantum.canon.decomposeintotimestepsca> :</span><span class="sxs-lookup"><span data-stu-id="c9532-158">This iteration pattern is implemented by <xref:microsoft.quantum.canon.decomposeintotimestepsca>:</span></span>

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

<span data-ttu-id="c9532-159">Signatura `DecomposeIntoTimeStepsCA` následuje společný vzor v Q# , kde kolekce, které mohou být zálohovány buď pomocí polí, nebo něco, které výpočetní prvky v průběhu jsou reprezentovány řazenými kolekcemi členů, jejichž první prvky jsou `Int` hodnoty, které určují jejich délku.</span><span class="sxs-lookup"><span data-stu-id="c9532-159">The signature of `DecomposeIntoTimeStepsCA` follows a common pattern in Q#, where collections that may be backed either by arrays or by something which compute elements on the fly are represented by tuples whose first elements are `Int` values indicating their lengths.</span></span>

## <a name="putting-it-together-controlling-operations"></a><span data-ttu-id="c9532-160">Vložení dohromady: řízení operací</span><span class="sxs-lookup"><span data-stu-id="c9532-160">Putting it Together: Controlling Operations</span></span> ##

<span data-ttu-id="c9532-161">Nakonec Canon staví na `Controlled` funktor tím, že poskytuje další způsoby pro podmínění operací s více než jednou.</span><span class="sxs-lookup"><span data-stu-id="c9532-161">Finally, the canon builds on the `Controlled` functor by providing additional ways to condition quantum operations.</span></span>
<span data-ttu-id="c9532-162">Je běžné, zejména v případě aritmetických operací, pro podmínky operace výpočtu na základě jiných stavů, než je $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="c9532-162">It is common, especially in quantum arithmetic, to condition operations on computational basis states other than $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="c9532-163">Pomocí operací a funkcí ovládacího prvku, které jsou představené výše, můžeme v jednom příkazu využít obecnější podmínky.</span><span class="sxs-lookup"><span data-stu-id="c9532-163">Using the control operations and functions introduced above, we can more general quantum conditions in a single statement.</span></span>
<span data-ttu-id="c9532-164">Pojďme se pustit do toho, jak <xref:microsoft.quantum.canon.controlledonbitstring> to dělá (parametry typu sítě SAN), pak rozdělíme jednotlivé díly o jeden.</span><span class="sxs-lookup"><span data-stu-id="c9532-164">Let's jump in to how <xref:microsoft.quantum.canon.controlledonbitstring> does it (sans type parameters), then we'll break down the pieces one by one.</span></span>
<span data-ttu-id="c9532-165">První věc, kterou je potřeba udělat, je definování operace, která ve skutečnosti dělá velkou zvedací implementaci ovládacího prvku na libovolný výpočetní stav.</span><span class="sxs-lookup"><span data-stu-id="c9532-165">The first thing we'll need to do is to define an operation which actually does the heavy lifting of implementing the control on arbitrary computational basis states.</span></span>
<span data-ttu-id="c9532-166">Tuto operaci nebudeme volat přímo, ale přidáme `_` na začátek názvu, abychom zjistili, že se jedná o implementaci jiného konstruktoru jinde.</span><span class="sxs-lookup"><span data-stu-id="c9532-166">We won't call this operation directly, however, and so we add `_` to the beginning of the name to indicate that it's an implementation of another construct elsewhere.</span></span>

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

<span data-ttu-id="c9532-167">Všimněte si, že bereme řetězec bitů, který je reprezentován jako `Bool` pole, které používáme k určení podmíněného nastavování, které chceme použít pro operaci `oracle` , kterou jsme dali.</span><span class="sxs-lookup"><span data-stu-id="c9532-167">Note that we take a string of bits, represented as a `Bool` array, that we use to specify the conditioning that we want to apply to the operation `oracle` that we are given.</span></span>
<span data-ttu-id="c9532-168">Vzhledem k tomu, že tato operace ve skutečnosti přímo dělá aplikaci, musíme také pořídit i cílové Registry, jak je znázorněno zde `Qubit[]` .</span><span class="sxs-lookup"><span data-stu-id="c9532-168">Since this operation actually does the application directly, we also need to take the control and target registers, both represented here as `Qubit[]`.</span></span>

<span data-ttu-id="c9532-169">V dalším kroku Upozorňujeme, že řízení na výpočetním stavu $ \ket{\vec{s}} = \ket{s \_ 0 s \_ 1 \dots s \_ {n-1}} $ pro bitový řetězec $ \vec{s} $ se dá realizovat tak, že transformuje $ \ket{\vec{s}} $ do $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="c9532-169">Next, we note that controlling on the computational basis state $\ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n - 1}}$ for a bit string $\vec{s}$ can be realized by transforming $\ket{\vec{s}}$ into $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="c9532-170">Konkrétně $ \ket{\vec{s}} = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="c9532-170">In particular, $\ket{\vec{s}} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{0\cdots 0}$.</span></span>
<span data-ttu-id="c9532-171">Protože $X ^ {\dagger} = X $, znamená to, že $ \ket{0\dots 0} = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} \ket{\vec{s}} $.</span><span class="sxs-lookup"><span data-stu-id="c9532-171">Since $X^{\dagger} = X$, this implies that $\ket{0\dots 0} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{\vec{s}}$.</span></span>
<span data-ttu-id="c9532-172">Proto můžeme použít $P = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} $, použít `Controlled oracle` a transformovat zpátky na $ \vec{s} $.</span><span class="sxs-lookup"><span data-stu-id="c9532-172">Thus, we can apply $P = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}}$, apply `Controlled oracle`, and transform back to $\vec{s}$.</span></span>
<span data-ttu-id="c9532-173">Tato konstrukce je přesně ta `ApplyWith` , proto zapište text naší nové operace odpovídajícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="c9532-173">This construction is precisely `ApplyWith`, so we write the body of our new operation accordingly:</span></span>

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

<span data-ttu-id="c9532-174">Tady jsme použili <xref:microsoft.quantum.canon.applypaulifrombitstring> pro použití s nástrojem $P $, částečně aplikované na jeho cíl `ApplyWith` .</span><span class="sxs-lookup"><span data-stu-id="c9532-174">Here, we have used <xref:microsoft.quantum.canon.applypaulifrombitstring> to apply $P$, partially applying over its target for use with `ApplyWith`.</span></span>
<span data-ttu-id="c9532-175">Všimněte si ale, že potřebujeme transformovat registraci *ovládacího prvku* do našeho formuláře, takže částečně použijeme interní operaci `(Controlled oracle)` na *cíli*.</span><span class="sxs-lookup"><span data-stu-id="c9532-175">Note, however, that we need to transform the *control* register to our desired form, so we partially apply the inner operation `(Controlled oracle)` on the *target*.</span></span>
<span data-ttu-id="c9532-176">Tato činnost ponechá `ApplyWith` v závorce řídicího registru pomocí $P $, přesně podle potřeby.</span><span class="sxs-lookup"><span data-stu-id="c9532-176">This leaves `ApplyWith` acting to bracket the control register with $P$, exactly as we desired.</span></span>

<span data-ttu-id="c9532-177">V tuto chvíli jsme se mohli udělat, ale nevyhovuje tomu, že se naše nová operace neshoduje s tím, jako když použijete `Controlled` funktor.</span><span class="sxs-lookup"><span data-stu-id="c9532-177">At this point, we could be done, but it is somehow unsatisfying that our new operation does not "feel" like applying the `Controlled` functor.</span></span>
<span data-ttu-id="c9532-178">Proto jsme dokončili definování našeho nového konceptu toku řízení vytvořením funkce, která bude mít pod kontrolou Oracle a který vrátí novou operaci.</span><span class="sxs-lookup"><span data-stu-id="c9532-178">Thus, we finish defining our new control flow concept by writing a function that takes the oracle to be controlled and that returns a new operation.</span></span>
<span data-ttu-id="c9532-179">Díky tomu naše nová funkce vypadá a je příliš velká `Controlled` , což ilustruje, že můžeme snadno definovat výkonné nové konstrukce toku ovládacích prvků pomocí Q# a Canon společně:</span><span class="sxs-lookup"><span data-stu-id="c9532-179">In this way, our new function looks and feels very much like `Controlled`, illustrating that we can easily define powerful new control flow constructs using Q# and the canon together:</span></span>

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
