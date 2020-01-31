---
title: Okruhy za sebou | Microsoft Docs
description: Kvantové okruhy
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: fe845aa0dde7c780ea6721dfe2559119e90b4aa5
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820789"
---
# <a name="quantum-circuits"></a><span data-ttu-id="53882-103">Okruhy</span><span class="sxs-lookup"><span data-stu-id="53882-103">Quantum Circuits</span></span>
<span data-ttu-id="53882-104">Vezměte v úvahu za chvilku, že se jedná o jednotnou transformaci $ \Text{CNOT} _{01}(H\otimes 1) $.</span><span class="sxs-lookup"><span data-stu-id="53882-104">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="53882-105">Tato sekvence brány má zásadní význam pro výpočetní výkon, protože vytváří qubit stav s maximální entangled:</span><span class="sxs-lookup"><span data-stu-id="53882-105">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="53882-106">$ $ \mathrm{CNOT}_{01}(H\otimes 1) \ket{00} = \frac{1}{\sqrt{2}} \left (\ket{00} + \ket{11} \right), $ $</span><span class="sxs-lookup"><span data-stu-id="53882-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="53882-107">Operace s touto nebo větší složitou složitostí jsou všudypřítomný s využitím algoritmů pro provozní a přístupnosti chyb, takže by měly být skvělé, že pro svou vizualizaci se používá jednoduchá metoda, která se nazývá *diagram okruhu*.</span><span class="sxs-lookup"><span data-stu-id="53882-107">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="53882-108">Diagram okruhu pro přípravu tohoto maximálního entangledého stavu je:</span><span class="sxs-lookup"><span data-stu-id="53882-108">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/Concepts1.png)

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="53882-109">Konvence diagramu pro okruhy</span><span class="sxs-lookup"><span data-stu-id="53882-109">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="53882-110">Tento vizuál pro práci s více operačními operacemi může být mnohem snadno digestible než zapsání jeho ekvivalentní matrice, jakmile pochopíte konvence pro vyjádření okruhu.</span><span class="sxs-lookup"><span data-stu-id="53882-110">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="53882-111">Tyto konvence prověříme níže.</span><span class="sxs-lookup"><span data-stu-id="53882-111">We review these conventions below.</span></span>

<span data-ttu-id="53882-112">V diagramu okruhu každá plná čára znázorňuje qubit nebo více všeobecně qubit Registry.</span><span class="sxs-lookup"><span data-stu-id="53882-112">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="53882-113">Podle konvence je horním řádkem qubit Register $0 $ a zbytek je označený sekvenčně.</span><span class="sxs-lookup"><span data-stu-id="53882-113">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="53882-114">Výše uvedený příklad okruhu je znázorněný na dvou qubits (nebo ekvivalentních dvou registrech, které se skládají z jednoho qubit).</span><span class="sxs-lookup"><span data-stu-id="53882-114">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="53882-115">Brány fungující na jednom nebo více registrech qubit jsou označeny jako pole.</span><span class="sxs-lookup"><span data-stu-id="53882-115">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="53882-116">Například symbol</span><span class="sxs-lookup"><span data-stu-id="53882-116">For example, the symbol</span></span>

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_2.png)

<span data-ttu-id="53882-117">je [Hadamard](xref:microsoft.quantum.intrinsic.h) brána, která funguje v registru s jedním qubit.</span><span class="sxs-lookup"><span data-stu-id="53882-117">is the [Hadamard](xref:microsoft.quantum.intrinsic.h) gate acting on a single-qubit register.</span></span>

<span data-ttu-id="53882-118">Vyřazení z více procesorů je seřazené v chronologickém pořadí s bránou, která je nejvíce vlevo, jako brána se jako první používá pro qubits.</span><span class="sxs-lookup"><span data-stu-id="53882-118">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="53882-119">Jinými slovy, pokud se dráty naformátují jako držící stav, vodiče přinášejí stav u všech bran v diagramu zleva doprava.</span><span class="sxs-lookup"><span data-stu-id="53882-119">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="53882-120">Řekněme, že</span><span class="sxs-lookup"><span data-stu-id="53882-120">That is to say</span></span> 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_3.png)

<span data-ttu-id="53882-121">je jednotná matice $CBA $.</span><span class="sxs-lookup"><span data-stu-id="53882-121">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="53882-122">Násobení matice dodržuje opačnou konvenci: nejprve se použije matice nejvyšší výše.</span><span class="sxs-lookup"><span data-stu-id="53882-122">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="53882-123">V diagramech okruhu ve službě pro vytváření koncových procesorů se ale jako první používá brána vlevo.</span><span class="sxs-lookup"><span data-stu-id="53882-123">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="53882-124">Tento rozdíl může v některých případech vést k nejasnostem, takže je důležité si všimnout tohoto významného rozdílu mezi lineárním zápisem algebraických a diagramy okruhu.</span><span class="sxs-lookup"><span data-stu-id="53882-124">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="53882-125">Vstupy a výstupy okruhů</span><span class="sxs-lookup"><span data-stu-id="53882-125">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="53882-126">Všechny předchozí uvedené příklady mají přesně stejný počet vodičů (qubits), jako je počet vodičů v bráně pro plnění.</span><span class="sxs-lookup"><span data-stu-id="53882-126">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="53882-127">Je možné, že se zpočátku jeví jako přiměřená, že okruhy by mohly mít více nebo méně výstupů, než jsou vstupy obecně.</span><span class="sxs-lookup"><span data-stu-id="53882-127">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="53882-128">To však není možné, protože všechny provozní operace šetří měření, jsou jednotně a tedy vratné.</span><span class="sxs-lookup"><span data-stu-id="53882-128">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="53882-129">Pokud neobsahují stejný počet výstupů jako vstupy, které by nebyly vratné, a proto nejsou v rozporu.</span><span class="sxs-lookup"><span data-stu-id="53882-129">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="53882-130">Z tohoto důvodu musí mít jakékoli pole vykreslené v diagramu okruhu přesně stejný počet vodičů, kteří ho vstupují při jeho ukončení.</span><span class="sxs-lookup"><span data-stu-id="53882-130">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="53882-131">Diagramy okruhu s více qubit se podobají podobným konvencím pro qubit.</span><span class="sxs-lookup"><span data-stu-id="53882-131">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="53882-132">Jako objasnění příkladu můžeme definovat qubit jednotkovou $B operaci $ (H S\otimes X) $ a objasnit okruh stejným způsobem jako</span><span class="sxs-lookup"><span data-stu-id="53882-132">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_4.png)

<span data-ttu-id="53882-133">V závislosti na kontextu, ve kterém se okruh používá, můžeme také zobrazit $B $ jako akce v jednom qubit registru, nikoli 2 1-qubit Registry.</span><span class="sxs-lookup"><span data-stu-id="53882-133">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="53882-134">Nejužitečnější vlastností takových diagramů s abstraktním okruhem je pravděpodobně to, že umožňují složitosti složitých algoritmů na vysoké úrovni, aniž by bylo nutné je kompilovat na základní brány.</span><span class="sxs-lookup"><span data-stu-id="53882-134">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="53882-135">To znamená, že můžete získat Intuition o toku dat pro velký algoritmus, aniž byste museli porozumět všem podrobnostem o tom, jak jednotlivé podrutiny v rámci algoritmu fungují.</span><span class="sxs-lookup"><span data-stu-id="53882-135">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="53882-136">Řízené brány</span><span class="sxs-lookup"><span data-stu-id="53882-136">Controlled gates</span></span>
<span data-ttu-id="53882-137">Druhá konstrukce, která je integrovaná do qubitch okruhů, je řídicích diagramů.</span><span class="sxs-lookup"><span data-stu-id="53882-137">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="53882-138">Akce u jednorázového počtu jader, označených jako $ \Lambda (G) $, kde hodnota jednoho qubit řídí aplikaci $G $, se dá pochopit tak, že se podíváme na následující příklad vstupu stavu produktu $ \Lambda (G) (\Alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \Alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket {\ psí} $.</span><span class="sxs-lookup"><span data-stu-id="53882-138">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$.</span></span>
<span data-ttu-id="53882-139">To znamená, že řízená brána se vztahuje $G $ na registr obsahující $ \psi $ if a jenom v případě, že qubit ovládacího prvku převezme hodnotu $1 $.</span><span class="sxs-lookup"><span data-stu-id="53882-139">That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="53882-140">Obecně popisujeme tyto řízené operace v diagramech okruhů jako</span><span class="sxs-lookup"><span data-stu-id="53882-140">In general, we describe such controlled operations in circuit diagrams as</span></span>

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_5.png)

<span data-ttu-id="53882-141">Tady černý kroužek označuje bit, na kterém je brána řízená, a vertikální kabel označuje jednotnou, která se použije, když qubit ovládacího prvku převezme hodnotu $1 $.</span><span class="sxs-lookup"><span data-stu-id="53882-141">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="53882-142">Pro zvláštní případy, kdy $G = X $ a $G = Z $ zavádíme následující zápis, který popíše řízenou verzi bran (Všimněte si, že brána řízená-X je rozhraní [$CNOT $](xref:microsoft.quantum.intrinsic.cnot)):</span><span class="sxs-lookup"><span data-stu-id="53882-142">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.intrinsic.cnot)):</span></span>

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_6.png)

<span data-ttu-id="53882-143">Q # poskytuje metody pro automatické generování řízené verze operace, která bude ukládat programátora z nutnosti kódování těchto operací.</span><span class="sxs-lookup"><span data-stu-id="53882-143">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="53882-144">Příklad najdete tady:</span><span class="sxs-lookup"><span data-stu-id="53882-144">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="53882-145">Operátor měření</span><span class="sxs-lookup"><span data-stu-id="53882-145">Measurement operator</span></span>
<span data-ttu-id="53882-146">Zbývající operace vizualizace v diagramech okruhů je měření.</span><span class="sxs-lookup"><span data-stu-id="53882-146">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="53882-147">Měření bere v qubit registraci, měří ho a výsledek vyprodukuje jako klasické informace.</span><span class="sxs-lookup"><span data-stu-id="53882-147">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="53882-148">Operace měření je označená symbolem měřiče a vždycky přebírá jako vstup qubit registr (označený plnou čárou) a výstupem klasických informací (označených dvojitou čárou).</span><span class="sxs-lookup"><span data-stu-id="53882-148">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="53882-149">Konkrétně takový okruh vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="53882-149">Specifically, such a subcircuit looks like:</span></span>

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="53882-150">okruh měření ![](~/media/concepts_7.png)</span><span class="sxs-lookup"><span data-stu-id="53882-150">![Measurement circuit](~/media/concepts_7.png)</span></span>

<span data-ttu-id="53882-151">Q # implementuje pro tento účel [operátor míry](xref:microsoft.quantum.intrinsic.measure) .</span><span class="sxs-lookup"><span data-stu-id="53882-151">Q# implements a [Measure operator](xref:microsoft.quantum.intrinsic.measure) for this purpose.</span></span>
<span data-ttu-id="53882-152">Další informace najdete v [části o měřeních](xref:microsoft.quantum.libraries.standard.prelude#measurements) .</span><span class="sxs-lookup"><span data-stu-id="53882-152">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="53882-153">Podobně, předaný okruh</span><span class="sxs-lookup"><span data-stu-id="53882-153">Similarly, the subcircuit</span></span>

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_8.png)

<span data-ttu-id="53882-154">poskytuje klasický monitorovanou bránu, kde $G $ se aplikuje v případě, že je pro klasický řídicí bit nastavená hodnota $1 $.</span><span class="sxs-lookup"><span data-stu-id="53882-154">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="53882-155">Diagram okruhu přenosu</span><span class="sxs-lookup"><span data-stu-id="53882-155">Teleportation circuit diagram</span></span>
<span data-ttu-id="53882-156">Pro ilustraci těchto [komponent je možná](xref:microsoft.quantum.techniques.puttingittogether) nejlepší výkon</span><span class="sxs-lookup"><span data-stu-id="53882-156">[Quantum teleportation](xref:microsoft.quantum.techniques.puttingittogether) is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="53882-157">Navýšení doby provozu je metoda pro přesouvání dat v rámci počítače s přístavou (nebo dokonce i mezi vzdálenými počítači v přístavu) pomocí entanglement a měření.</span><span class="sxs-lookup"><span data-stu-id="53882-157">Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="53882-158">Vzhledem k tomu, že je to v podstatě schopné přesunovat stav, který je v daném qubit, je z jednoho qubit na jiný, bez ohledu na to, jaká hodnota qubit je!</span><span class="sxs-lookup"><span data-stu-id="53882-158">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="53882-159">To je nezbytné, aby protokol fungoval v souladu s zákony na mechanismy plnění.</span><span class="sxs-lookup"><span data-stu-id="53882-159">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="53882-160">Okruh pro stavovou dopravu je uveden níže. Poskytujeme také verzi okruhu s poznámkou, která ukazuje, jak číst okruh.</span><span class="sxs-lookup"><span data-stu-id="53882-160">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<!--- ![](.\media\tp2.svg){ width=50% } --->
![](~/media/concepts_tp2.png)
