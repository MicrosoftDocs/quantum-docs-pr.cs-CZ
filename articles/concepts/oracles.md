---
title: Kvantová orákula
description: Přečtěte si, jak pracovat s a definovat i ty Oracle, operace s černým polem, které se používají jako vstup pro jiný algoritmus.
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
ms.openlocfilehash: 1d1d0b0903db8e994166c3e8a5798f70742a1c7e
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904923"
---
# <a name="quantum-oracles"></a><span data-ttu-id="1b422-103">Nejenom Oracle</span><span class="sxs-lookup"><span data-stu-id="1b422-103">Quantum Oracles</span></span>

<span data-ttu-id="1b422-104">Oracle $O $ je operace "Black Box", která se používá jako vstup pro jiný algoritmus.</span><span class="sxs-lookup"><span data-stu-id="1b422-104">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="1b422-105">Tyto operace se často definují pomocí klasické funkce $f: \\{0, 1\\} ^ n \to \\{0, 1\\} ^ m $, který přebírá $n $-bit binárního vstupu a vytváří $m $ bitový binární výstup.</span><span class="sxs-lookup"><span data-stu-id="1b422-105">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="1b422-106">Provedete to tak, že zaberete konkrétní binární vstup $x = (x_{0}, x_{1}, \dots, x_ {n-1}).</span><span class="sxs-lookup"><span data-stu-id="1b422-106">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="1b422-107">Můžeme označit qubit stavy jako $ \ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_ {n-1}} $.</span><span class="sxs-lookup"><span data-stu-id="1b422-107">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="1b422-108">Můžeme se nejdřív pokusit o definování $O $ tak, že $O \ket{x} = \ket{f (x)} $, ale má několik problémů.</span><span class="sxs-lookup"><span data-stu-id="1b422-108">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="1b422-109">První, $f $ může mít jinou velikost vstupu a výstupu ($n \Ne m $), což použití $O $ by změnilo počet qubits v registru.</span><span class="sxs-lookup"><span data-stu-id="1b422-109">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="1b422-110">Za druhé, i když $n = m $, funkce nemusí být inverzi: Pokud $f (x) = f (y) $ pro některé $x \Ne y $, pak $O \ket{x} = O\ket {y} $, ale $O ^ \dagger O\ket {x} \Ne O ^ \dagger O\ket {y} $.</span><span class="sxs-lookup"><span data-stu-id="1b422-110">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="1b422-111">To znamená, že nebudeme moct vytvořit sousedící operaci $O ^ \dagger $ a Oracle musí mít pro ně definované sousedící.</span><span class="sxs-lookup"><span data-stu-id="1b422-111">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="1b422-112">Definování systému Oracle jeho účinkem na výpočetní bázi – stavy</span><span class="sxs-lookup"><span data-stu-id="1b422-112">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="1b422-113">S oběma uvedenými problémy se můžeme zabývat tím, že zavedete druhý registr $m $ qubits a podržíte naši odpověď.</span><span class="sxs-lookup"><span data-stu-id="1b422-113">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="1b422-114">Pak nadefinujeme účinek Oracle na všechny stavy výpočtů na bázi: pro všechny $x \in \\{0, 1\\} ^ n $ a $y \in \\{0, 1\\} ^ m $,</span><span class="sxs-lookup"><span data-stu-id="1b422-114">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

<span data-ttu-id="1b422-115">$ $ \begin{align} O (\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f (x)}.</span><span class="sxs-lookup"><span data-stu-id="1b422-115">$$ \begin{align} O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="1b422-116">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="1b422-116">\end{align} $$</span></span>

<span data-ttu-id="1b422-117">Nyní $O = O ^ \dagger $ podle konstrukce, proto jsme vyřešili obě předchozí problémy.</span><span class="sxs-lookup"><span data-stu-id="1b422-117">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
> <span data-ttu-id="1b422-118">Pokud chcete vidět, že $O = O ^ {\dagger} $, Všimněte si, že $O ^ 2 = \boldone $, protože $a \oplus b \oplus b = a $ for All $a, b \in \{0, 1\}$.</span><span class="sxs-lookup"><span data-stu-id="1b422-118">To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
> <span data-ttu-id="1b422-119">V důsledku toho $O \ket{x} \ket{y \oplus f (x)} = \ket{x} \ket{y \oplus f (x) \oplus f (x)} = \ket{x} \ket{y} $.</span><span class="sxs-lookup"><span data-stu-id="1b422-119">As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="1b422-120">Důležité je, abyste definovali Oracle tímto způsobem pro každý výpočetní stav $ \ket{x}\ket{y} $, který definuje, jak $O $ chovat pro jakýkoliv jiný stav.</span><span class="sxs-lookup"><span data-stu-id="1b422-120">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="1b422-121">Postup je ihned ze skutečnosti, že $O $, stejně jako všechny provozní operace, je lineární ve stavu, ve kterém funguje.</span><span class="sxs-lookup"><span data-stu-id="1b422-121">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="1b422-122">Zvažte operaci Hadamard, například, která je definována $H \ket{0} = \ket{+} $ a $H \ket{1} = \ket{-}$.</span><span class="sxs-lookup"><span data-stu-id="1b422-122">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="1b422-123">Pokud chceme zjistit, jak $H $ funguje na $ \ket{+} $, můžeme použít $H $ je lineární,</span><span class="sxs-lookup"><span data-stu-id="1b422-123">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

<span data-ttu-id="1b422-124">$ $ \begin{align} H\ket {+} & = \frac{1}{\sqrt{2}} H (\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0}-\ket{1}) = \ket{0}.</span><span class="sxs-lookup"><span data-stu-id="1b422-124">$$ \begin{align} H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
<span data-ttu-id="1b422-125">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="1b422-125">\end{align} $$</span></span>

<span data-ttu-id="1b422-126">V případě definování našeho Oracle $O $ můžeme podobně použít jakýkoliv stav $ \ket{\psi} $ v $n + m $ qubits může být zapsaný jako</span><span class="sxs-lookup"><span data-stu-id="1b422-126">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

<span data-ttu-id="1b422-127">$ $ \begin{align} \ket{\psi} & = \ sum_ {x \in \\{0, 1\\} ^ n, y \in \\{0, 1\\} ^ m} \Alpha (x, y) \ket{x} \ket{y} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="1b422-127">$$ \begin{align} \ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \end{align} $$</span></span>

<span data-ttu-id="1b422-128">kde $ \Alpha: \\{0, 1\\} ^ n \times \\{0, 1\\} ^ m \to \mathbb{C} $ představuje koeficienty stavu $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="1b422-128">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="1b422-129">Rozdíl</span><span class="sxs-lookup"><span data-stu-id="1b422-129">Thus,</span></span>

<span data-ttu-id="1b422-130">$ $ \begin{align} O \ket{\psi} & = O \ sum_ {x \in \\{0, 1\\} ^ n, y \in \\{0, 1\\} ^ m} \Alpha (x, y) \ket{x} \ket{y} \\\\ & = \ sum_ {x \in \\{0, 1\\} ^ n, y \in \\{0, 1\\} ^ m} \Alpha (x, y) O \ket{x} \ket{y} \\\\ & = \ sum_ {x \in \\{0; 1\\} ^ n , y \in \\{0, 1\\} ^ m} \Alpha (x, y) \ket{x} \ket{y \oplus f (x)}.</span><span class="sxs-lookup"><span data-stu-id="1b422-130">$$ \begin{align} O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="1b422-131">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="1b422-131">\end{align} $$</span></span>

## <a name="phase-oracles"></a><span data-ttu-id="1b422-132">Fáze Oracle</span><span class="sxs-lookup"><span data-stu-id="1b422-132">Phase oracles</span></span>
<span data-ttu-id="1b422-133">Další možností je kódování $f $ do Oracle $O $, a to použitím _fáze_ založené na vstupu do $O $.</span><span class="sxs-lookup"><span data-stu-id="1b422-133">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$.</span></span>
<span data-ttu-id="1b422-134">Můžeme například definovat $O $, což je $ $ \begin{align} O \ket{x} = (-1) ^ {f (x)} \ket{x}.</span><span class="sxs-lookup"><span data-stu-id="1b422-134">For instance, we might define $O$ such that $$ \begin{align} O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
<span data-ttu-id="1b422-135">\end{align} $ $ Pokud fáze Oracle funguje na prvním registru ve stavu výpočtu $ \ket{x} $, pak je tato fáze globální fází, a proto nepozorovatelná.</span><span class="sxs-lookup"><span data-stu-id="1b422-135">\end{align} $$ If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="1b422-136">Takové Oracle ale může být velmi výkonný prostředek, pokud se aplikuje na nadpozici nebo jako kontrolované operace.</span><span class="sxs-lookup"><span data-stu-id="1b422-136">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="1b422-137">Představte si třeba fázi orcale $O _f $ pro qubit funkci s jedním $f $.</span><span class="sxs-lookup"><span data-stu-id="1b422-137">For example, consider a phase orcale $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="1b422-138">Pak $ $ \begin{align} O_f \ket{+} & = O_f (\ket{0} + \ket{1})/\sqrt{2} \\\\ & = ((-1) ^ {f (0)} \ket{0} + (-1) ^ {f (1)} \ket{1})/\sqrt{2} \\\\ & = (-1) ^ {f (0)} (\ket{0} + (-1) ^ {f (1)-f (0)} \ket{1})/\sqrt{2} \\\\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket{+}.</span><span class="sxs-lookup"><span data-stu-id="1b422-138">Then, $$ \begin{align} O_f \ket{+} & = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\ & = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
<span data-ttu-id="1b422-139">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="1b422-139">\end{align} $$</span></span>

<span data-ttu-id="1b422-140">Obecně platí, že obě zobrazení Oracle lze rozšířit tak, aby představovalo klasické funkce, které vracejí reálné hodnoty místo pouze jednoho bitu.</span><span class="sxs-lookup"><span data-stu-id="1b422-140">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="1b422-141">Volba nejlepšího způsobu implementace Oracle závisí intenzivně na tom, jak se tento Oracle bude používat v daném algoritmu.</span><span class="sxs-lookup"><span data-stu-id="1b422-141">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="1b422-142">Například [algoritmus Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) spoléhá na rozhraní Oracle implementované prvním způsobem, zatímco [algoritmus Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) spoléhá na rozhraní Oracle implementované druhým způsobem.</span><span class="sxs-lookup"><span data-stu-id="1b422-142">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="1b422-143">Pro další podrobnosti doporučujeme diskuzi v [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).</span><span class="sxs-lookup"><span data-stu-id="1b422-143">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
