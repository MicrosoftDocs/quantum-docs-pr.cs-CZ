---
title: Kvantové okruhy
description: Naučte se vizuálně znázornit jednoduché a složité provozní operace pomocí diagramů okruhů.
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: 59c32928ddc9252009ad101a3cf3ac33f4968e28
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269605"
---
# <a name="quantum-circuits"></a><span data-ttu-id="ba955-103">Okruhy</span><span class="sxs-lookup"><span data-stu-id="ba955-103">Quantum Circuits</span></span>
<span data-ttu-id="ba955-104">Vezměte v úvahu za chvilku, že se jedná o jednotnou transformaci $ \Text { CNOT} _ {01 } (H \otimes 1) $.</span><span class="sxs-lookup"><span data-stu-id="ba955-104">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="ba955-105">Tato sekvence brány má zásadní význam pro výpočetní výkon, protože vytváří qubit stav s maximální entangled:</span><span class="sxs-lookup"><span data-stu-id="ba955-105">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="ba955-106">$ $ \mathrm{CNOT}_{01 } (H \otimes 1) \ket{00 } = \frac{1 } {\sqrt{2 } } \left (\ket{00 } + \ket{11 } \right), $ $</span><span class="sxs-lookup"><span data-stu-id="ba955-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="ba955-107">Operace s touto nebo větší složitou složitostí jsou všudypřítomný s využitím algoritmů pro provozní a přístupnosti chyb, takže by měly být skvělé, že pro svou vizualizaci se používá jednoduchá metoda, která se nazývá *diagram okruhu*.</span><span class="sxs-lookup"><span data-stu-id="ba955-107">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="ba955-108">Diagram okruhu pro přípravu tohoto maximálního entangledého stavu je:</span><span class="sxs-lookup"><span data-stu-id="ba955-108">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="ba955-109">![Diagram okruhu pro maximální entangled stav qubit](~/media/1.svg)</span><span class="sxs-lookup"><span data-stu-id="ba955-109">![Circuit diagram for a maximally entangled two-qubit state](~/media/1.svg)</span></span>

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="ba955-110">Konvence diagramu pro okruhy</span><span class="sxs-lookup"><span data-stu-id="ba955-110">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="ba955-111">Tento vizuál pro práci s více operačními operacemi může být mnohem snadno digestible než zapsání jeho ekvivalentní matrice, jakmile pochopíte konvence pro vyjádření okruhu.</span><span class="sxs-lookup"><span data-stu-id="ba955-111">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="ba955-112">Tyto konvence prověříme níže.</span><span class="sxs-lookup"><span data-stu-id="ba955-112">We review these conventions below.</span></span>

<span data-ttu-id="ba955-113">V diagramu okruhu každá plná čára znázorňuje qubit nebo více všeobecně qubit Registry.</span><span class="sxs-lookup"><span data-stu-id="ba955-113">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="ba955-114">Podle konvence je horním řádkem qubit Register $0 $ a zbytek je označený sekvenčně.</span><span class="sxs-lookup"><span data-stu-id="ba955-114">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="ba955-115">Výše uvedený příklad okruhu je znázorněný na dvou qubits (nebo ekvivalentních dvou registrech, které se skládají z jednoho qubit).</span><span class="sxs-lookup"><span data-stu-id="ba955-115">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="ba955-116">Brány fungující na jednom nebo více registrech qubit jsou označeny jako pole.</span><span class="sxs-lookup"><span data-stu-id="ba955-116">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="ba955-117">Například symbol</span><span class="sxs-lookup"><span data-stu-id="ba955-117">For example, the symbol</span></span>

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="ba955-118">![Symbol pro Hadamard operace fungující v registru s jedním qubit](~/media/2.svg)</span><span class="sxs-lookup"><span data-stu-id="ba955-118">![Symbol for a Hadamard operation acting on a single-qubit register](~/media/2.svg)</span></span>

<span data-ttu-id="ba955-119">je [Hadamard](xref:microsoft.quantum.intrinsic.h) operace fungující v registru s jedním qubit.</span><span class="sxs-lookup"><span data-stu-id="ba955-119">is a [Hadamard](xref:microsoft.quantum.intrinsic.h) operation acting on a single-qubit register.</span></span>

<span data-ttu-id="ba955-120">Vyřazení z více procesorů je seřazené v chronologickém pořadí s bránou, která je nejvíce vlevo, jako brána se jako první používá pro qubits.</span><span class="sxs-lookup"><span data-stu-id="ba955-120">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="ba955-121">Jinými slovy, pokud se dráty naformátují jako držící stav, vodiče přinášejí stav u všech bran v diagramu zleva doprava.</span><span class="sxs-lookup"><span data-stu-id="ba955-121">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="ba955-122">Řekněme, že</span><span class="sxs-lookup"><span data-stu-id="ba955-122">That is to say</span></span> 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="ba955-123">![Diagram protiprocesorů používaných v zleva doprava](~/media/3.svg)</span><span class="sxs-lookup"><span data-stu-id="ba955-123">![Diagram of quantum gates being applied left-to-right](~/media/3.svg)</span></span>

<span data-ttu-id="ba955-124">je $CBA jednotnou maticí $ .</span><span class="sxs-lookup"><span data-stu-id="ba955-124">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="ba955-125">Násobení matice dodržuje opačnou konvenci: nejprve se použije matice nejvyšší výše.</span><span class="sxs-lookup"><span data-stu-id="ba955-125">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="ba955-126">V diagramech okruhu ve službě pro vytváření koncových procesorů se ale jako první používá brána vlevo.</span><span class="sxs-lookup"><span data-stu-id="ba955-126">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="ba955-127">Tento rozdíl může v některých případech vést k nejasnostem, takže je důležité si všimnout tohoto významného rozdílu mezi lineárním zápisem algebraických a diagramy okruhu.</span><span class="sxs-lookup"><span data-stu-id="ba955-127">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="ba955-128">Vstupy a výstupy okruhů</span><span class="sxs-lookup"><span data-stu-id="ba955-128">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="ba955-129">Všechny předchozí uvedené příklady mají přesně stejný počet vodičů (qubits), jako je počet vodičů v bráně pro plnění.</span><span class="sxs-lookup"><span data-stu-id="ba955-129">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="ba955-130">Je možné, že se zpočátku jeví jako přiměřená, že okruhy by mohly mít více nebo méně výstupů, než jsou vstupy obecně.</span><span class="sxs-lookup"><span data-stu-id="ba955-130">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="ba955-131">To však není možné, protože všechny provozní operace šetří měření, jsou jednotně a tedy vratné.</span><span class="sxs-lookup"><span data-stu-id="ba955-131">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="ba955-132">Pokud neobsahují stejný počet výstupů jako vstupy, které by nebyly vratné, a proto nejsou v rozporu.</span><span class="sxs-lookup"><span data-stu-id="ba955-132">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="ba955-133">Z tohoto důvodu musí mít jakékoli pole vykreslené v diagramu okruhu přesně stejný počet vodičů, kteří ho vstupují při jeho ukončení.</span><span class="sxs-lookup"><span data-stu-id="ba955-133">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="ba955-134">Diagramy okruhu s více qubit se podobají podobným konvencím pro qubit.</span><span class="sxs-lookup"><span data-stu-id="ba955-134">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="ba955-135">Jako příklad objasnění můžete definovat qubit jednotkovou $B operaci, $ která bude mít hodnotu $ (H S \otimes ×) $ a objasnit okruh stejným způsobem jako</span><span class="sxs-lookup"><span data-stu-id="ba955-135">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="ba955-136">![Diagram okruhu s qubit jednotkovou operací](~/media/4.svg)</span><span class="sxs-lookup"><span data-stu-id="ba955-136">![Circuit diagram of a two-qubit unitary operation](~/media/4.svg)</span></span>

<span data-ttu-id="ba955-137">V $ závislosti na kontextu, ve kterém se okruh používá, můžeme také zobrazit $B jako akce v jednom qubit registru, a ne 2 1-qubit Registry.</span><span class="sxs-lookup"><span data-stu-id="ba955-137">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="ba955-138">Nejužitečnější vlastností takových diagramů s abstraktním okruhem je pravděpodobně to, že umožňují složitosti složitých algoritmů na vysoké úrovni, aniž by bylo nutné je kompilovat na základní brány.</span><span class="sxs-lookup"><span data-stu-id="ba955-138">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="ba955-139">To znamená, že můžete získat Intuition o toku dat pro velký algoritmus, aniž byste museli porozumět všem podrobnostem o tom, jak jednotlivé podrutiny v rámci algoritmu fungují.</span><span class="sxs-lookup"><span data-stu-id="ba955-139">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="ba955-140">Řízené brány</span><span class="sxs-lookup"><span data-stu-id="ba955-140">Controlled gates</span></span>
<span data-ttu-id="ba955-141">Druhá konstrukce, která je integrovaná do qubitch okruhů, je řídicích diagramů.</span><span class="sxs-lookup"><span data-stu-id="ba955-141">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="ba955-142">Akce u jednorázových jader, označených příznakem $ \Lambda (G) $, kde jedna hodnota qubit řídí aplikaci $G $ , se dá pochopit tak, že se podíváme na následující příklad vstupu stavu produktu $ \Lambda (G) (\Alpha \ket{0 } + \beta \ket{1 } ) \ket { \psi } = \Alpha \ket{0 \Ket \psi } { } + \beta \ket{1 } G \ket { \psi } $.</span><span class="sxs-lookup"><span data-stu-id="ba955-142">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$.</span></span>
<span data-ttu-id="ba955-143">To znamená, že řízená brána se vztahuje $G $ do registru obsahujícího $ \psi $ , pokud a pouze v případě, že qubit ovládacího prvku převezme hodnotu $1 $ .</span><span class="sxs-lookup"><span data-stu-id="ba955-143">That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="ba955-144">Obecně popisujeme tyto řízené operace v diagramech okruhů jako</span><span class="sxs-lookup"><span data-stu-id="ba955-144">In general, we describe such controlled operations in circuit diagrams as</span></span>

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="ba955-145">![Diagram okruhu samostatně kontrolované brány](~/media/5.svg)</span><span class="sxs-lookup"><span data-stu-id="ba955-145">![Circuit diagram of a singly controlled gate](~/media/5.svg)</span></span>

<span data-ttu-id="ba955-146">Tady černý kroužek označuje bit, na kterém je brána řízená, a vertikální kabel označuje jednotnou, která se použije, když qubit ovládacího prvku převezme hodnotu $1 $ .</span><span class="sxs-lookup"><span data-stu-id="ba955-146">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="ba955-147">Pro speciální případy, kdy $G = X $ a $G = Z, $ zavádíme následující zápis, který popíše řízená verze bran (Všimněte si, že brána řízená-X je [ $ bránou $CNOT](xref:microsoft.quantum.intrinsic.cnot)):</span><span class="sxs-lookup"><span data-stu-id="ba955-147">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.intrinsic.cnot)):</span></span>

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="ba955-148">![Diagram okruhu pro speciální případy řízených bran](~/media/6.svg)</span><span class="sxs-lookup"><span data-stu-id="ba955-148">![Circuit diagram for special cases of controlled gates](~/media/6.svg)</span></span>

<span data-ttu-id="ba955-149">Q # poskytuje metody pro automatické generování řízené verze operace, která bude ukládat programátora z nutnosti kódování těchto operací.</span><span class="sxs-lookup"><span data-stu-id="ba955-149">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="ba955-150">Příklad najdete tady:</span><span class="sxs-lookup"><span data-stu-id="ba955-150">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="ba955-151">Operátor měření</span><span class="sxs-lookup"><span data-stu-id="ba955-151">Measurement operator</span></span>
<span data-ttu-id="ba955-152">Zbývající operace vizualizace v diagramech okruhů je měření.</span><span class="sxs-lookup"><span data-stu-id="ba955-152">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="ba955-153">Měření bere v qubit registraci, měří ho a výsledek vyprodukuje jako klasické informace.</span><span class="sxs-lookup"><span data-stu-id="ba955-153">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="ba955-154">Operace měření je označená symbolem měřiče a vždycky přebírá jako vstup qubit registr (označený plnou čárou) a výstupem klasických informací (označených dvojitou čárou).</span><span class="sxs-lookup"><span data-stu-id="ba955-154">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="ba955-155">Konkrétně takový okruh vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="ba955-155">Specifically, such a subcircuit looks like:</span></span>

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="ba955-156">![Symbol reprezentující operaci měření](~/media/7.svg)</span><span class="sxs-lookup"><span data-stu-id="ba955-156">![Symbol representing a measurement operation](~/media/7.svg)</span></span>

<span data-ttu-id="ba955-157">Q # implementuje pro tento účel [operátor míry](xref:microsoft.quantum.intrinsic.measure) .</span><span class="sxs-lookup"><span data-stu-id="ba955-157">Q# implements a [Measure operator](xref:microsoft.quantum.intrinsic.measure) for this purpose.</span></span>
<span data-ttu-id="ba955-158">Další informace najdete v [části o měřeních](xref:microsoft.quantum.libraries.standard.prelude#measurements) .</span><span class="sxs-lookup"><span data-stu-id="ba955-158">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="ba955-159">Podobně, předaný okruh</span><span class="sxs-lookup"><span data-stu-id="ba955-159">Similarly, the subcircuit</span></span>

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="ba955-160">![Diagram okruhu reprezentující kontrolovanou operaci](~/media/8.svg)</span><span class="sxs-lookup"><span data-stu-id="ba955-160">![Circuit diagram representing a controlled operation](~/media/8.svg)</span></span>

<span data-ttu-id="ba955-161">poskytuje klasickou bránu, kde $G $ se aplikuje na bit klasického ovládacího prvku, který má hodnotu $1 $ .</span><span class="sxs-lookup"><span data-stu-id="ba955-161">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="ba955-162">Diagram okruhu přenosu</span><span class="sxs-lookup"><span data-stu-id="ba955-162">Teleportation circuit diagram</span></span>
<span data-ttu-id="ba955-163">Pro ilustraci těchto komponent je možná nejlepší výkon</span><span class="sxs-lookup"><span data-stu-id="ba955-163">Quantum teleportation is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="ba955-164">Pomocí entanglement a měření se můžete seznámit s odpovídajícím [Kataem](xref:microsoft.quantum.overview.katas) provozu za provozu, který bude sloužit jako způsob přesunu dat v rámci počítače s procesorem na více procesorech (nebo dokonce mezi vzdálenými počítači s více procesory).</span><span class="sxs-lookup"><span data-stu-id="ba955-164">You can learn hands-on with the corresponding [Quantum Kata](xref:microsoft.quantum.overview.katas) Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="ba955-165">Vzhledem k tomu, že je to v podstatě schopné přesunovat stav, který je v daném qubit, je z jednoho qubit na jiný, bez ohledu na to, jaká hodnota qubit je!</span><span class="sxs-lookup"><span data-stu-id="ba955-165">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="ba955-166">To je nezbytné, aby protokol fungoval v souladu s zákony na mechanismy plnění.</span><span class="sxs-lookup"><span data-stu-id="ba955-166">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="ba955-167">Okruh pro stavovou dopravu je uveden níže. Poskytujeme také verzi okruhu s poznámkou, která ukazuje, jak číst okruh.</span><span class="sxs-lookup"><span data-stu-id="ba955-167">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<!--- ![](.\media\tp2.svg){ width=50% } --->
<span data-ttu-id="ba955-168">![Okruh vystavování](~/media/tp2.svg)</span><span class="sxs-lookup"><span data-stu-id="ba955-168">![Quantum teleportation circuit](~/media/tp2.svg)</span></span>
