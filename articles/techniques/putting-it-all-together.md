---
title: Q# techniky - Uvedení to všechno dohromady
description: Projděte si základní q# program, který demonstruje kvantovou teleportaci.
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030561"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="8fcf1-103">Uvedení to všechno dohromady: Teleportace</span><span class="sxs-lookup"><span data-stu-id="8fcf1-103">Putting It All Together: Teleportation</span></span> #
<span data-ttu-id="8fcf1-104">Vraťme se k příkladu teleportačního obvodu definovaného v [kvantových obvodech](xref:microsoft.quantum.concepts.circuits).</span><span class="sxs-lookup"><span data-stu-id="8fcf1-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="8fcf1-105">Použijeme to k ilustraci konceptů, které jsme se zatím naučili.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="8fcf1-106">Vysvětlení kvantové teleportace je k dispozici níže pro ty, kteří nejsou obeznámeni s teorií, následuje návod implementace kódu v Q#.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="8fcf1-107">Kvantová teleportace: Teorie</span><span class="sxs-lookup"><span data-stu-id="8fcf1-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="8fcf1-108">Kvantová teleportace je technika pro odesílání neznámého kvantového stavu (který budeme označovat jako '__zpráva__') z qubit u jednoho místa na qubit na jiném místě (budeme odkazovat na tyto qubity jako '__zde__' a '__tam__', resp.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="8fcf1-109">Můžeme reprezentovat naše __poselství__ jako vektor pomocí Dirac notace:</span><span class="sxs-lookup"><span data-stu-id="8fcf1-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="8fcf1-110">$$ \ket{\psi} = \alfa\ket{0} +{1} \beta\ket $$</span><span class="sxs-lookup"><span data-stu-id="8fcf1-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="8fcf1-111">Stav __zprávy__ qubit je neznámý pro nás, protože nevíme hodnoty $\alpha$ a $\beta$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="8fcf1-112">Krok 1: Vytvoření zamotaný stav</span><span class="sxs-lookup"><span data-stu-id="8fcf1-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="8fcf1-113">Aby bylo možné poslat __zprávu,__ musíme pro qubit __zde__ být zapletený s qubit __tam__.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="8fcf1-114">Toho je dosaženo použitím hadamardské brány, následovanou bránou CNOT.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="8fcf1-115">Podívejme se na matematiku za těmito operacemi brány.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="8fcf1-116">Začneme s qubity __tu__ a __tam__ jak ve{0}stavu $\ket $.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="8fcf1-117">Po zamotání těchto qubitů jsou ve stavu:</span><span class="sxs-lookup"><span data-stu-id="8fcf1-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="8fcf1-118">$$ \ket{\phi^+} ={1}\frac{2}{\sqrt{00} }(\ket + \ket{11}) $$</span><span class="sxs-lookup"><span data-stu-id="8fcf1-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="8fcf1-119">Krok 2: Odeslání zprávy</span><span class="sxs-lookup"><span data-stu-id="8fcf1-119">Step 2: Send the message</span></span>
<span data-ttu-id="8fcf1-120">Chcete-li poslat __zprávu__ jsme nejprve použít Brána CNOT se __zprávou__ qubit a __zde__ qubit jako vstupy __(zpráva__ qubit je ovládací prvek a __zde__ qubit je cíl qubit, v tomto případě).</span><span class="sxs-lookup"><span data-stu-id="8fcf1-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="8fcf1-121">Tento vstupní stav lze zapsat:</span><span class="sxs-lookup"><span data-stu-id="8fcf1-121">This input state can be written:</span></span>

<span data-ttu-id="8fcf1-122">$${0} \ket{\psi}\ket{\phi^+} = (\alpha\ket +{1}\beta\ket{1})(\frac {\sqrt{2}}(\ket{00} + \ket{11})) $$</span><span class="sxs-lookup"><span data-stu-id="8fcf1-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="8fcf1-123">Tím se zvětšujete na:</span><span class="sxs-lookup"><span data-stu-id="8fcf1-123">This expands to:</span></span>

<span data-ttu-id="8fcf1-124">$$ \ket{\psi}\ket{\phi^+} ={2}\frac{\alpha}{\sqrt{000} }\ket +{2}\frac{\alpha}{\sqrt{011} {2}{100} {2}{111} }\ket + \frac{\beta}{\sqrt }\ket }\</span><span class="sxs-lookup"><span data-stu-id="8fcf1-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="8fcf1-125">Připomínáme, že brána CNOT převrátí cílový qubit, když je kontrolní qubit 1.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="8fcf1-126">Takže například vstup $\ket{000}$ bude mít za následek žádnou změnu jako první qubit (ovládací prvek) je 0.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="8fcf1-127">Vezměte však případ, kdy první qubit je 1 - například vstup $\ket{100}$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="8fcf1-128">V tomto případě je výstup $\ket{110}$ jako druhý qubit (cíl) je převrácený bránou CNOT.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="8fcf1-129">Podívejme se nyní na náš výstup, jakmile brána CNOT jednala na našem vstupu výše.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="8fcf1-130">Výsledkem je:</span><span class="sxs-lookup"><span data-stu-id="8fcf1-130">The result is:</span></span>

<span data-ttu-id="8fcf1-131">{2}$$ \frac{\alpha}{\sqrt }\ket{000} + \frac{\alpha}{\sqrt{011} {2}{110} {2}{101} {2}}\ket + \frac{\beta}{\sqrt }\ket + \frac{\beta}{\sqrt }\ket $$</span><span class="sxs-lookup"><span data-stu-id="8fcf1-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="8fcf1-132">Dalším krokem k odeslání __zprávy__ je použít hadamard bránu na __zprávu__ qubit (to je první qubit každého termínu).</span><span class="sxs-lookup"><span data-stu-id="8fcf1-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="8fcf1-133">Připomínáme, že hadamardova brána dělá následující:</span><span class="sxs-lookup"><span data-stu-id="8fcf1-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="8fcf1-134">Vstup</span><span class="sxs-lookup"><span data-stu-id="8fcf1-134">Input</span></span> | <span data-ttu-id="8fcf1-135">Výstup</span><span class="sxs-lookup"><span data-stu-id="8fcf1-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="8fcf1-136">$\ket{0}$</span><span class="sxs-lookup"><span data-stu-id="8fcf1-136">$\ket{0}$</span></span>  | <span data-ttu-id="8fcf1-137">$\frac{1}{\sqrt{2}}(\ket{0} +{1}\ket )$</span><span class="sxs-lookup"><span data-stu-id="8fcf1-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="8fcf1-138">$\ket{1}$</span><span class="sxs-lookup"><span data-stu-id="8fcf1-138">$\ket{1}$</span></span>  | <span data-ttu-id="8fcf1-139">$\frac{1}{\sqrt{2}}(\ket{0} -{1}\ket )$</span><span class="sxs-lookup"><span data-stu-id="8fcf1-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="8fcf1-140">Pokud použijeme hadamardovou bránu na první qubit každého termínu našeho výstupu výše, získáme následující výsledek:</span><span class="sxs-lookup"><span data-stu-id="8fcf1-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="8fcf1-141">$${2}\frac{\alpha}{\sqrt }(\frac{1}{\sqrt{2}}(\ket{1}{00} {2}{1}{2}{0} {1}{11} {2}{1}{2}{0} {1}{10} {2}{1}{2}{0} {1}{01} {0} + \ket))\ket + \frac{\alpha}{\sqrt }(\frac {\sqrt }(\ket + \ket))\ket + \frac{\beta}{\sqrt }(\frac {\sqrt }(\ket - \ket))\ket + \frac{\beta}{\sqrt }(\frac {\sqrt }(\ket - \ket))\ket $$</span><span class="sxs-lookup"><span data-stu-id="8fcf1-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="8fcf1-142">Všimněte si, že každý{1}termín má dva{2}faktory $\frac {\sqrt }$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="8fcf1-143">Můžeme je znásobit a dát takto:</span><span class="sxs-lookup"><span data-stu-id="8fcf1-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="8fcf1-144">$$ \frac{\alpha}{2}(\ket{0} +{1}\ket{00} )\ket +{2}\frac{\alpha} (\ket{0} + \ket{1}{11} )\ket + \frac{\beta}{2}(\ket{0} - \ket{0} {1}{01} {1})\ket )\ket{10} +\beta}{2}</span><span class="sxs-lookup"><span data-stu-id="8fcf1-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="8fcf1-145">$\frac{1}{2}$ faktor je společný pro každý termín, takže nyní můžeme vzít mimo závorky:</span><span class="sxs-lookup"><span data-stu-id="8fcf1-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="8fcf1-146">{1}{2}$$ \frac \big[\alpha(\ket{0} +{1}\ket{00} )\ket +{0} \alpha(\ket + \ket{1})\ket + \ket{11} + \ket - \ket{0} )\ket )\ket )\ket{1}{10} {0} {1}{01})\ket</span><span class="sxs-lookup"><span data-stu-id="8fcf1-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="8fcf1-147">Pak můžeme vynásobit závorky pro každý termín dávat:</span><span class="sxs-lookup"><span data-stu-id="8fcf1-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="8fcf1-148">{1}{2}$$ \frac \big[\alpha\ket{000} + \alpha\ket{100} +{011} \alpha\ket{111} + \alpha\ket{010} + \beta\ket -{001} \beta\ket{101}{110} + \beta\ket - \beta\ket \big] $$</span><span class="sxs-lookup"><span data-stu-id="8fcf1-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="8fcf1-149">Krok 3: Měření výsledku</span><span class="sxs-lookup"><span data-stu-id="8fcf1-149">Step 3: Measure the result</span></span>

<span data-ttu-id="8fcf1-150">Vzhledem k tomu, __tu__ a __tam__ je zapletený, jakékoli měření na __zde__ bude mít vliv na stav __tam__.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="8fcf1-151">Pokud změříme první a druhý qubit (__zpráva__ a __zde__), můžeme se dozvědět, v jakém __stavu__ je, kvůli této vlastnosti zapletení.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="8fcf1-152">Pokud změříme a získáme výsledek 00, superpozice se zhroutí a ponecháme pouze podmínky, které jsou v souladu s tímto výsledkem.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="8fcf1-153">To je $\alpha\ket{000} +\beta\ket{001}$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="8fcf1-154">To může být refaktorováno{00}na $\ket{0} (\alpha\ket +\beta\ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="8fcf1-155">Proto pokud měříme první a druhý qubit být 00, víme, že třetí qubit, __tam__,{0} je ve stavu{1}$(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="8fcf1-156">Pokud změříme a získáme výsledek 01, superpozice se zhroutí a ponecháme pouze podmínky, které jsou v souladu s tímto výsledkem.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="8fcf1-157">To je $\alpha\ket{011} +\beta\ket{010}$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="8fcf1-158">To může být refaktorováno{01}na $\ket{1} (\alpha\ket +\beta\ket{0})$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="8fcf1-159">Proto pokud měříme první a druhý qubit být 01, víme, že třetí qubit, __tam__,{1} je ve stavu{0}$(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="8fcf1-160">Pokud změříme a získáme výsledek 10, superpozice se zhroutí a ponecháme pouze podmínky, které jsou v souladu s tímto výsledkem.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="8fcf1-161">To je $\alpha\ket{100} -\beta\ket{101}$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="8fcf1-162">To může být refaktorováno{10}na $\ket{0} (\alpha\ket -\beta\ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="8fcf1-163">Proto pokud měříme první a druhý qubit na 10, víme, že třetí qubit, __tam__,{0} je ve stavu{1}$(\alpha\ket -\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="8fcf1-164">Pokud změříme a získáme výsledek 11, superpozice se zhroutí a ponecháme pouze podmínky, které jsou v souladu s tímto výsledkem.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="8fcf1-165">To je $\alpha\ket{111} -\beta\ket{110}$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="8fcf1-166">To může být refaktorováno{11}na $\ket{1} (\alpha\ket -\beta\ket{0})$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="8fcf1-167">Proto pokud měříme první a druhý qubit na 11, víme, že třetí qubit, __tam__,{1} je ve stavu{0}$(\alpha\ket -\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="8fcf1-168">Krok 4: Interpretace výsledku</span><span class="sxs-lookup"><span data-stu-id="8fcf1-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="8fcf1-169">Připomínáme, že původní __zpráva,__ kterou jsme chtěli poslat, byla:</span><span class="sxs-lookup"><span data-stu-id="8fcf1-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="8fcf1-170">$$ \ket{\psi} = \alfa\ket{0} +{1} \beta\ket $$</span><span class="sxs-lookup"><span data-stu-id="8fcf1-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="8fcf1-171">Musíme se __dostat tam__ qubit do tohoto stavu, takže přijatý stav je ten, který byl určen.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="8fcf1-172">Pokud jsme změřili a dostali výsledek 00, pak třetí qubit, __tam__,{0} je ve stavu{1}$(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="8fcf1-173">Vzhledem k tomu, že se jedná o zamýšlenou __zprávu__, není nutná žádná změna.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="8fcf1-174">Pokud jsme změřili a dostali výsledek 01, pak třetí qubit, __tam__,{1} je ve stavu{0}$(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="8fcf1-175">To se liší od zamýšlené __zprávy__, ale použití NOT gate nám dává{0} požadovaný stav $(\alpha\ket +\beta\ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="8fcf1-176">Pokud jsme změřili a dostali výsledek 10, pak třetí qubit, __tam__,{0} je ve stavu{1}$(\alpha\ket -\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="8fcf1-177">To se liší od zamýšlené __zprávy__, ale použití brány Z nám dává{0} požadovaný stav $(\alpha\ket +\beta\ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="8fcf1-178">Pokud jsme změřili a dostali výsledek 11, pak třetí qubit, __tam__,{1} je ve stavu{0}$(\alpha\ket -\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="8fcf1-179">To se liší od zamýšlené __zprávy__, ale použití not brány následované bránou Z{0} nám dává požadovaný{1}stav $(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="8fcf1-180">Abychom to shrnuli, pokud měříme a první qubit je 1, použije se brána Z.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="8fcf1-181">Pokud měříme a druhý qubit je 1, použije se brána NOT.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="8fcf1-182">Souhrn</span><span class="sxs-lookup"><span data-stu-id="8fcf1-182">Summary</span></span>
<span data-ttu-id="8fcf1-183">Níže je uveden kvantový obvod, který implementuje teleportaci.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="8fcf1-184">Pohybující se zleva doprava můžete vidět:</span><span class="sxs-lookup"><span data-stu-id="8fcf1-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="8fcf1-185">Krok 1: Zamotání __tu__ a __tam__ použitím Hadamard brány a CNOT brány.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="8fcf1-186">Krok 2: Odeslání __zprávy__ pomocí brány CNOT a brány Hadamard.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="8fcf1-187">Krok 3: Měření prvního a druhého qubits, __zprávy__ a __zde__.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="8fcf1-188">Krok 4: Použití brány NOT nebo brány Z, v závislosti na výsledku měření v kroku 3.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

!["Teleport(msg : Qubit, tam : Qubit) : Jednotka"](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="8fcf1-190">Kvantová teleportace: Kód</span><span class="sxs-lookup"><span data-stu-id="8fcf1-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="8fcf1-191">Máme náš obvod pro kvantovou teleportaci:</span><span class="sxs-lookup"><span data-stu-id="8fcf1-191">We have our circuit for quantum teleportation:</span></span>

!["Teleport(msg : Qubit, tam : Qubit) : Jednotka"](~/media/teleportation.svg)

<span data-ttu-id="8fcf1-193">Nyní můžeme přeložit každý z kroků v tomto kvantovém obvodu do Q#.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="8fcf1-194">Krok 0: Definice</span><span class="sxs-lookup"><span data-stu-id="8fcf1-194">Step 0: Definition</span></span>
<span data-ttu-id="8fcf1-195">Když provádíme teleportaci, musíme znát __zprávu,__ kterou chceme poslat, a kam ji chceme poslat __(tam).__</span><span class="sxs-lookup"><span data-stu-id="8fcf1-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="8fcf1-196">Z tohoto důvodu začneme definováním nové operace Teleport, která je dána `msg` `there`dva qubity jako argumenty a :</span><span class="sxs-lookup"><span data-stu-id="8fcf1-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="8fcf1-197">Musíme také přidělit `here` qubit, kterého `using` dosáhneme s blokem:</span><span class="sxs-lookup"><span data-stu-id="8fcf1-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="8fcf1-198">Krok 1: Vytvoření zamotaný stav</span><span class="sxs-lookup"><span data-stu-id="8fcf1-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="8fcf1-199">Pak můžeme vytvořit zamotaný `there` pár @"microsoft.quantum.intrinsic.h" mezi @"microsoft.quantum.intrinsic.cnot" `here` a pomocí a operace:</span><span class="sxs-lookup"><span data-stu-id="8fcf1-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.intrinsic.h" and @"microsoft.quantum.intrinsic.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="8fcf1-200">Krok 2: Odeslání zprávy</span><span class="sxs-lookup"><span data-stu-id="8fcf1-200">Step 2: Send the message</span></span>
<span data-ttu-id="8fcf1-201">Potom použijeme další brány $\operatorname{CNOT}$ a $H$ k přesunutí naší zprávy qubit:</span><span class="sxs-lookup"><span data-stu-id="8fcf1-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="8fcf1-202">Krok 3 & 4: Měření a interpretace výsledku</span><span class="sxs-lookup"><span data-stu-id="8fcf1-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="8fcf1-203">Nakonec používáme @"microsoft.quantum.intrinsic.m" k provedení měření a provedení nezbytných operací brány, abychom `if` získali požadovaný stav, jak je uvedeno v příkazech:</span><span class="sxs-lookup"><span data-stu-id="8fcf1-203">Finally, we use @"microsoft.quantum.intrinsic.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a><span data-ttu-id="8fcf1-204">Krok 5: Restartování registru qubit</span><span class="sxs-lookup"><span data-stu-id="8fcf1-204">Step 5: Restarting the qubit register</span></span>

<span data-ttu-id="8fcf1-205">Na konci každé operace Q# musíme nechat qubits ve stavu{0}$\ket $.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-205">At the end of every Q# operation we need to let the qubits in the state $\ket{0}$.</span></span> <span data-ttu-id="8fcf1-206">Můžeme použít @"microsoft.quantum.intrinsic.reset" k restartování všech qubitů do nulového stavu a tím dokončíme naši operaci.</span><span class="sxs-lookup"><span data-stu-id="8fcf1-206">We can use @"microsoft.quantum.intrinsic.reset" to restart all the qubits to the zero state and this will finish our operation.</span></span>

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


