---
title: 'Vše dohromady – techniky Q # | Microsoft Docs'
description: 'Vše dohromady – techniky Q #'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 3605826da159757d4b321dbf4ec6acd7f4e6be05
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820160"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="252c3-103">Vše dohromady: při přenosu</span><span class="sxs-lookup"><span data-stu-id="252c3-103">Putting It All Together: Teleportation</span></span> #
<span data-ttu-id="252c3-104">Pojďme se vrátit na příklad okruhu přenosu definovaného v [okruhech](xref:microsoft.quantum.concepts.circuits).</span><span class="sxs-lookup"><span data-stu-id="252c3-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="252c3-105">Budeme k tomu využít k ilustraci konceptů, které jsme doposud dozvěděli.</span><span class="sxs-lookup"><span data-stu-id="252c3-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="252c3-106">Pro uživatele, kteří nejsou obeznámeni s teoretickou, je níže uveden výklad doby použitelnosti, za kterou následuje návod implementace kódu v Q #.</span><span class="sxs-lookup"><span data-stu-id="252c3-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="252c3-107">Vystavení za sebou: teorie</span><span class="sxs-lookup"><span data-stu-id="252c3-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="252c3-108">Jednosměrné navýšení má za následek odeslání neznámého stavového stavu (to znamená "__zpráva__") z qubit v jednom umístění do qubit v jiném umístění (na tyto qubits odkazujeme jako__na this a__v uvedeném pořadí).</span><span class="sxs-lookup"><span data-stu-id="252c3-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="252c3-109">Naši __zprávu__ můžeme znázornit jako vektor pomocí zápisu Dirac:</span><span class="sxs-lookup"><span data-stu-id="252c3-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="252c3-110">$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="252c3-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="252c3-111">Stav __zprávy__ qubit není znám, protože neznáte hodnoty $ \Alpha $ a $ \beta $.</span><span class="sxs-lookup"><span data-stu-id="252c3-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="252c3-112">Krok 1: vytvoření stavu entangled</span><span class="sxs-lookup"><span data-stu-id="252c3-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="252c3-113">Aby bylo možné poslat __zprávu__ __pro qubit,__ je třeba, aby se entangled __s qubit.__</span><span class="sxs-lookup"><span data-stu-id="252c3-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="252c3-114">Toho dosáhnete použitím brány Hadamard, následovanou bránou CNOT.</span><span class="sxs-lookup"><span data-stu-id="252c3-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="252c3-115">Pojďme se podívat na matematiku za těmito operacemi s bránou.</span><span class="sxs-lookup"><span data-stu-id="252c3-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="252c3-116">Zahájíme __vám qubits a__ ve stavu $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="252c3-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="252c3-117">Po Entangling těchto qubits jsou ve stavu:</span><span class="sxs-lookup"><span data-stu-id="252c3-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="252c3-118">$ $ \ket{\phi ^ +} = \frac{1}{\sqrt{2}} (\ket{00} + \ket{11}) $ $</span><span class="sxs-lookup"><span data-stu-id="252c3-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="252c3-119">Krok 2: odeslání zprávy</span><span class="sxs-lookup"><span data-stu-id="252c3-119">Step 2: Send the message</span></span>
<span data-ttu-id="252c3-120">Pokud chcete poslat __zprávu__ , nejdřív použijte bránu CNOT se __zprávou__ qubit a __tady__ qubit jako vstupy ( __zpráva__ qubit je ovládací prvek a __tady__ qubit v této instanci je cílová qubit).</span><span class="sxs-lookup"><span data-stu-id="252c3-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="252c3-121">Tento stav vstupu lze zapsat:</span><span class="sxs-lookup"><span data-stu-id="252c3-121">This input state can be written:</span></span>

<span data-ttu-id="252c3-122">$ $ \ket{\psi}\ket{\phi ^ +} = (\alpha\ket{0} + \beta\ket{1}) (\frac{1}{\sqrt{2}} (\ket{00} + \ket{11})) $ $</span><span class="sxs-lookup"><span data-stu-id="252c3-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="252c3-123">Rozšiřuje se na:</span><span class="sxs-lookup"><span data-stu-id="252c3-123">This expands to:</span></span>

<span data-ttu-id="252c3-124">$ $ \ket{\psi}\ket{\phi ^ +} = \frac{\Alpha}{\sqrt{2}} \ket{000} + \frac{\Alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{100} + \frac{\beta}{\sqrt{2}} \ket{111} $ $</span><span class="sxs-lookup"><span data-stu-id="252c3-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="252c3-125">V rámci připomenutí CNOT brána Překlopí cílovou qubit, když je ovládací prvek qubit 1.</span><span class="sxs-lookup"><span data-stu-id="252c3-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="252c3-126">Například vstup $ \ket{000}$ nebude mít za následek změnu jako první qubit (ovládací prvek) je 0.</span><span class="sxs-lookup"><span data-stu-id="252c3-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="252c3-127">Nicméně si povezměte případ, kde první qubit je 1 – například vstup typu $ \ket{100}$.</span><span class="sxs-lookup"><span data-stu-id="252c3-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="252c3-128">V tomto případě je výstupem $ \ket{110}$ jako druhý qubit (cíl) převrácenou bránou CNOT.</span><span class="sxs-lookup"><span data-stu-id="252c3-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="252c3-129">Pojďme teď považovat výstup, jakmile se CNOT brána na náš vstup výše.</span><span class="sxs-lookup"><span data-stu-id="252c3-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="252c3-130">Výsledek je následující:</span><span class="sxs-lookup"><span data-stu-id="252c3-130">The result is:</span></span>

<span data-ttu-id="252c3-131">$ $ \frac{\Alpha}{\sqrt{2}} \ket{000} + \frac{\Alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{110} + \frac{\beta}{\sqrt{2}} \ket{101} $ $</span><span class="sxs-lookup"><span data-stu-id="252c3-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="252c3-132">Dalším krokem k odeslání __zprávy__ je použití brány Hadamard pro qubit __zprávy__ (to je první qubit každé podmínky).</span><span class="sxs-lookup"><span data-stu-id="252c3-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="252c3-133">Brána Hadamard má jako připomenutí následující:</span><span class="sxs-lookup"><span data-stu-id="252c3-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="252c3-134">Vstup</span><span class="sxs-lookup"><span data-stu-id="252c3-134">Input</span></span> | <span data-ttu-id="252c3-135">Výstup</span><span class="sxs-lookup"><span data-stu-id="252c3-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="252c3-136">$ \ket{0}$</span><span class="sxs-lookup"><span data-stu-id="252c3-136">$\ket{0}$</span></span>  | <span data-ttu-id="252c3-137">$ \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}) $</span><span class="sxs-lookup"><span data-stu-id="252c3-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="252c3-138">$ \ket{1}$</span><span class="sxs-lookup"><span data-stu-id="252c3-138">$\ket{1}$</span></span>  | <span data-ttu-id="252c3-139">$ \frac{1}{\sqrt{2}} (\ket{0}-\ket{1}) $</span><span class="sxs-lookup"><span data-stu-id="252c3-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="252c3-140">Pokud použijeme bránu Hadamard na první qubit každého předplatného našeho výstupu, získáme následující výsledek:</span><span class="sxs-lookup"><span data-stu-id="252c3-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="252c3-141">$ $ \frac{\Alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{00} + \frac{\Alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{11} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{10} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{01} $ $</span><span class="sxs-lookup"><span data-stu-id="252c3-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="252c3-142">Všimněte si, že každý výraz má $2 \frac{1}{\sqrt{2}} $ faktorů.</span><span class="sxs-lookup"><span data-stu-id="252c3-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="252c3-143">Tyto výsledky můžeme vynásobit následujícím výsledkům:</span><span class="sxs-lookup"><span data-stu-id="252c3-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="252c3-144">$ $ \frac{\Alpha}{2}(\ket{0} + \ket{1}) \ket{00} + \frac{\Alpha}{2}(\ket{0} + \ket{1}) \ket{11} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{10} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{01} $ $</span><span class="sxs-lookup"><span data-stu-id="252c3-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="252c3-145">Výraz $ \frac{1}{2}$ Factor je společný pro každý termín, takže ho teď můžeme vzít mimo hranaté závorky:</span><span class="sxs-lookup"><span data-stu-id="252c3-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="252c3-146">$ $ \frac{1}{2}\big [\Alpha (\ket{0} + \ket{1}) \ket{00} + \Alpha (\ket{0} + \ket{1}) \ket{11} + \beta (\ket{0}-\ket{1}) \ket{10} + \beta (\ket{0}-\ket{1}) \ket{01}\big] $ $</span><span class="sxs-lookup"><span data-stu-id="252c3-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="252c3-147">Pak můžeme vynásobit hranaté závorky pro každý termín, který poskytuje:</span><span class="sxs-lookup"><span data-stu-id="252c3-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="252c3-148">$ $ \frac{1}{2}\big [\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010}-\beta\ket{110} + \beta\ket{001}-\beta\ket{101}\big] $ $</span><span class="sxs-lookup"><span data-stu-id="252c3-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="252c3-149">Krok 3: měření výsledku</span><span class="sxs-lookup"><span data-stu-id="252c3-149">Step 3: Measure the result</span></span>

<span data-ttu-id="252c3-150">V důsledku toho se __tady__ __a entangled__ všechna měření, která __zde__ ovlivní __stav.__</span><span class="sxs-lookup"><span data-stu-id="252c3-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="252c3-151">Pokud si vyměříme první a druhý qubit (__zpráva__ a __tady__), můžeme zjistit, v čem se __nachází stav z__ důvodu této vlastnosti entanglement.</span><span class="sxs-lookup"><span data-stu-id="252c3-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="252c3-152">Pokud budeme měřit a získat výsledek 00, nadměrná pozice se sbalí a zachová pouze ty výrazy, které jsou v souladu s tímto výsledkem.</span><span class="sxs-lookup"><span data-stu-id="252c3-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="252c3-153">To je $ \alpha\ket{000} + \beta\ket{001}$.</span><span class="sxs-lookup"><span data-stu-id="252c3-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="252c3-154">Dá se Refaktorovat na $ \ket{00}(\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="252c3-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="252c3-155">Proto v __případě, že__je třeba změřit první a druhý qubit jako 00, víme, že třetí qubit je ve stavu $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="252c3-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="252c3-156">Pokud měříme a získáte výsledek 01, nadměrná pozice se sbalí a zachová jenom ty výrazy, které jsou v souladu s tímto výsledkem.</span><span class="sxs-lookup"><span data-stu-id="252c3-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="252c3-157">To je $ \alpha\ket{011} + \beta\ket{010}$.</span><span class="sxs-lookup"><span data-stu-id="252c3-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="252c3-158">Dá se Refaktorovat na $ \ket{01}(\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="252c3-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="252c3-159">Proto v __případě, že__je třeba změřit první a druhý qubit na hodnotu 01, víme, že třetí qubit je ve stavu \ (\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="252c3-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="252c3-160">Pokud provedeme měření a získáte výsledek 10, pozice se sbalí a zachová jenom ty výrazy, které jsou v souladu s tímto výsledkem.</span><span class="sxs-lookup"><span data-stu-id="252c3-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="252c3-161">To je $ \alpha\ket{100}-\beta\ket{101}$.</span><span class="sxs-lookup"><span data-stu-id="252c3-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="252c3-162">To lze Refaktorovat na $ \ket{10}(\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="252c3-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="252c3-163">Proto v případě, že měříme první a druhý qubit na 10, ví, že třetí qubit, je __tam__ve stavu $ (\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="252c3-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="252c3-164">Pokud provedeme měření a dostanete výsledek 11, pozice se sbalí a ponechává se jenom ty, které jsou v souladu s tímto výsledkem.</span><span class="sxs-lookup"><span data-stu-id="252c3-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="252c3-165">To je $ \alpha\ket{111}-\beta\ket{110}$.</span><span class="sxs-lookup"><span data-stu-id="252c3-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="252c3-166">To lze Refaktorovat na $ \ket{11}(\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="252c3-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="252c3-167">Proto v __případě, že__je třeba změřit první a druhý qubit na hodnotu 11, víme, že třetí qubit je ve stavu $ (\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="252c3-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="252c3-168">Krok 4: interpretace výsledku</span><span class="sxs-lookup"><span data-stu-id="252c3-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="252c3-169">V rámci připomenutí byla původní __zpráva__ , kterou jsme chtěli poslat,:</span><span class="sxs-lookup"><span data-stu-id="252c3-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="252c3-170">$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="252c3-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="252c3-171">Musíme do tohoto stavu dostat __qubit,__ aby byl přijatý stav ten, který byl určen.</span><span class="sxs-lookup"><span data-stu-id="252c3-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="252c3-172">Pokud jsme zjistili a získali výsledek 00, pak je třetí qubit ve stavu $(\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="252c3-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="252c3-173">Vzhledem k tomu, že se jedná o zamýšlenou __zprávu__, není nutná žádná změna.</span><span class="sxs-lookup"><span data-stu-id="252c3-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="252c3-174">Pokud jsme zjistili a získali výsledek __01, pak__je třetí qubit ve stavu $ (\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="252c3-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="252c3-175">To se liší od zamýšlené __zprávy__, ale použití nebrány nám poskytuje požadovaný stav $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="252c3-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="252c3-176">Pokud jsme nahodnotili a získali výsledek 10, je třetí qubit ve stavu$ (\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="252c3-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="252c3-177">To se liší od zamýšlené __zprávy__, ale použití brány z nám poskytuje požadovaný stav $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="252c3-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="252c3-178">Pokud jsme nahodnotili a získali výsledek __11, je__třetí qubit ve stavu $ (\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="252c3-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="252c3-179">To se liší od zamýšlené __zprávy__, ale použití nebrány následované bránou Z nám poskytuje požadovaný stav $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="252c3-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="252c3-180">V případě, že se jedná o míru a první qubit je 1, je použita Brána Z.</span><span class="sxs-lookup"><span data-stu-id="252c3-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="252c3-181">Pokud budeme měřit a druhý qubit je 1, nepoužije se žádná brána.</span><span class="sxs-lookup"><span data-stu-id="252c3-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="252c3-182">Souhrn</span><span class="sxs-lookup"><span data-stu-id="252c3-182">Summary</span></span>
<span data-ttu-id="252c3-183">Níže je uvedený okruh, který je v textovém poli okruh, který implementuje přenos.</span><span class="sxs-lookup"><span data-stu-id="252c3-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="252c3-184">Přesunutí zleva doprava můžete zobrazit:</span><span class="sxs-lookup"><span data-stu-id="252c3-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="252c3-185">Krok 1: Entangling __sem__ a __tam__ , kde použijete bránu HADAMARD a bránu CNOT.</span><span class="sxs-lookup"><span data-stu-id="252c3-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="252c3-186">Krok 2: odeslání __zprávy__ pomocí brány CNOT a brány Hadamard</span><span class="sxs-lookup"><span data-stu-id="252c3-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="252c3-187">Krok 3: pořízení měření první a druhé qubits, __zprávy__ a __sem__</span><span class="sxs-lookup"><span data-stu-id="252c3-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="252c3-188">Krok 4: použití brány, která není typu hradlo nebo Z, v závislosti na výsledku měření v kroku 3.</span><span class="sxs-lookup"><span data-stu-id="252c3-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

![' Teleport (MSG: qubit; zde: qubit): jednotka '](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="252c3-190">Vystavení za sebou: kód</span><span class="sxs-lookup"><span data-stu-id="252c3-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="252c3-191">Náš okruh máme pro naši službu pro vystavování.</span><span class="sxs-lookup"><span data-stu-id="252c3-191">We have our circuit for quantum teleportation:</span></span>

![' Teleport (MSG: qubit; zde: qubit): jednotka '](~/media/teleportation.svg)

<span data-ttu-id="252c3-193">Nyní můžeme přeložit každý z kroků v tomto okruhu do Q #.</span><span class="sxs-lookup"><span data-stu-id="252c3-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="252c3-194">Krok 0: definice</span><span class="sxs-lookup"><span data-stu-id="252c3-194">Step 0: Definition</span></span>
<span data-ttu-id="252c3-195">Když provedeme vystavování, musíme nám sdělit __zprávu__ , kterou chceme odeslat, a tam, kde si ji přejeme poslat (__tam__).</span><span class="sxs-lookup"><span data-stu-id="252c3-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="252c3-196">Z tohoto důvodu Začínáme definováním nové operace teleport, která je předána dvěma qubits jako argumentům, `msg` a `there`:</span><span class="sxs-lookup"><span data-stu-id="252c3-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="252c3-197">Také je potřeba přidělit qubit `here`, které máme `using` blok:</span><span class="sxs-lookup"><span data-stu-id="252c3-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="252c3-198">Krok 1: vytvoření stavu entangled</span><span class="sxs-lookup"><span data-stu-id="252c3-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="252c3-199">Pak můžeme vytvořit pár entangled mezi `here` a `there` pomocí operací @"microsoft.quantum.intrinsic.h" a @"microsoft.quantum.intrinsic.cnot":</span><span class="sxs-lookup"><span data-stu-id="252c3-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.intrinsic.h" and @"microsoft.quantum.intrinsic.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="252c3-200">Krok 2: odeslání zprávy</span><span class="sxs-lookup"><span data-stu-id="252c3-200">Step 2: Send the message</span></span>
<span data-ttu-id="252c3-201">Pak použijeme další brány $ \operatorname{CNOT} $ a $H $ k přesunutí našeho qubitu zpráv:</span><span class="sxs-lookup"><span data-stu-id="252c3-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="252c3-202">Krok 3 & 4: měření a interpretace výsledku</span><span class="sxs-lookup"><span data-stu-id="252c3-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="252c3-203">Nakonec používáme @"microsoft.quantum.intrinsic.m" k provádění měření a k provedení potřebných operací brány k získání požadovaného stavu, jak je označený `if` příkazy:</span><span class="sxs-lookup"><span data-stu-id="252c3-203">Finally, we use @"microsoft.quantum.intrinsic.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

<span data-ttu-id="252c3-204">Tím se dokončí definice našeho operátoru přenosu, takže můžeme navrátit `here`, ukončit text a ukončit operaci.</span><span class="sxs-lookup"><span data-stu-id="252c3-204">This finishes the definition of our teleportation operator, so we can deallocate `here`, end the body, and end the operation.</span></span>

```qsharp
    }
}
```
