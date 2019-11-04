---
title: 'Q # standardní knihovny – předehru | Microsoft Docs'
description: 'Q # standardní knihovny – předehru'
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: dddb3d4a5ebcdca16da41a5ae5520d98ea900a7f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/29/2019
ms.locfileid: "73183229"
---
# <a name="the-prelude"></a><span data-ttu-id="5411b-103">Předehru</span><span class="sxs-lookup"><span data-stu-id="5411b-103">The Prelude</span></span> #

<span data-ttu-id="5411b-104">Kompilátor Q # a cílové počítače, které jsou součástí vývojové sady pro plnění, poskytují sadu vnitřních funkcí a operací, které se dají použít při psaní programů v systému Q #.</span><span class="sxs-lookup"><span data-stu-id="5411b-104">The Q# compiler and the target machines included with the Quantum Development Kit provide a set of intrinsic functions and operations that can be used when writing quantum programs in Q#.</span></span>

## <a name="intrinsic-operations-and-functions"></a><span data-ttu-id="5411b-105">Vnitřní operace a funkce</span><span class="sxs-lookup"><span data-stu-id="5411b-105">Intrinsic Operations and Functions</span></span> ##

<span data-ttu-id="5411b-106">Vnitřní operace definované ve standardní knihovně zhruba spadají do jedné z několika kategorií:</span><span class="sxs-lookup"><span data-stu-id="5411b-106">The intrinsic operations defined in the standard library roughly fall into one of several categories:</span></span>

- <span data-ttu-id="5411b-107">Základní klasické funkce shromážděné v oboru názvů <xref:microsoft.quantum.core>.</span><span class="sxs-lookup"><span data-stu-id="5411b-107">Essential classical functions, collected in the <xref:microsoft.quantum.core> namespace.</span></span>
- <span data-ttu-id="5411b-108">Operace, které představují unitaries tvořené [Clifford a $T $ branami](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="5411b-108">Operations representing unitaries composed of [Clifford and $T$ gates](xref:microsoft.quantum.concepts.qubit).</span></span>
- <span data-ttu-id="5411b-109">Operace představující rotace různých operátorů.</span><span class="sxs-lookup"><span data-stu-id="5411b-109">Operations representing rotations about various operators.</span></span>
- <span data-ttu-id="5411b-110">Operace implementující měření.</span><span class="sxs-lookup"><span data-stu-id="5411b-110">Operations implementing measurements.</span></span>

<span data-ttu-id="5411b-111">Vzhledem k tomu, že sada Clifford + $T $ je [univerzální](xref:microsoft.quantum.concepts.multiple-qubits) pro práci s výpočetním prostředím, tyto operace postačují k tomu, aby se v negligibly malé chybě vyimplementovala jakákoli algoritmus.</span><span class="sxs-lookup"><span data-stu-id="5411b-111">Since the Clifford + $T$ gate set is [universal](xref:microsoft.quantum.concepts.multiple-qubits) for quantum computing, these operations suffice to approximately implement any quantum algorithm within negligibly small error.</span></span>
<span data-ttu-id="5411b-112">V případě, že zadáváte i rotace, Q # umožňuje programátorovi pracovat v rámci jedné qubit jednotkové a CNOTové knihovny brány.</span><span class="sxs-lookup"><span data-stu-id="5411b-112">By providing rotations as well, Q# allows the programmer to work within the single qubit unitary and CNOT gate library.</span></span> <span data-ttu-id="5411b-113">Tato knihovna je mnohem jednodušší, protože nepotřebuje programátora přímo vyjádřit Clifford $T + dekompozici $ a protože pro kompilaci jednoho qubit unitaries do Clifford a na $T $ Branch existují vysoce efektivní metody (viz [tady](xref:microsoft.quantum.more-information) pro další informace).</span><span class="sxs-lookup"><span data-stu-id="5411b-113">This library is much easier to think about because it does not  require the programmer to directly express the Clifford + $T$ decomposition and because highly efficient methods exist for compiling single qubit unitaries into Clifford and $T$ gates (see [here](xref:microsoft.quantum.more-information) for more information).</span></span>

<span data-ttu-id="5411b-114">Pokud je to možné, operace definované v předehru, které fungují na qubits, umožňují použít `Controlled` variantu, takže cílový počítač provede příslušné rozklady.</span><span class="sxs-lookup"><span data-stu-id="5411b-114">Where possible, the operations defined in the prelude which act on qubits allow for applying the `Controlled` variant, such that the target machine will perform the appropriate decomposition.</span></span>

<span data-ttu-id="5411b-115">Mnohé z funkcí a operací definovaných v této části předehru jsou v oboru názvů @"microsoft.quantum.intrinsic", takže většina zdrojových souborů Q # bude mít direktivu `open Microsoft.Quantum.Intrinsic;` hned po deklaraci počátečního oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="5411b-115">Many of the functions and operations defined in this portion of the prelude are in the @"microsoft.quantum.intrinsic" namespace, such that most Q# source files will have an `open Microsoft.Quantum.Intrinsic;` directive immediately following the initial namespace declaration.</span></span>
<span data-ttu-id="5411b-116">Obor názvů <xref:microsoft.quantum.core> je automaticky otevřen, takže funkce jako <xref:microsoft.quantum.core.length> lze použít bez příkazu `open`.</span><span class="sxs-lookup"><span data-stu-id="5411b-116">The <xref:microsoft.quantum.core> namespace is automatically opened, so that functions such as <xref:microsoft.quantum.core.length> can be used without an `open` statement at all.</span></span>

### <a name="common-single-qubit-unitary-operations"></a><span data-ttu-id="5411b-117">Běžné operace s jedním qubit jednotkou</span><span class="sxs-lookup"><span data-stu-id="5411b-117">Common Single-Qubit Unitary Operations</span></span> ###

<span data-ttu-id="5411b-118">Předehru také definuje mnoho běžných [qubit operací](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span><span class="sxs-lookup"><span data-stu-id="5411b-118">The prelude also defines many common [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>
<span data-ttu-id="5411b-119">Všechny tyto operace umožňují `Controlled` i `Adjoint` funktory.</span><span class="sxs-lookup"><span data-stu-id="5411b-119">All of these operations allow both the `Controlled` and `Adjoint` functors.</span></span>

#### <a name="pauli-operators"></a><span data-ttu-id="5411b-120">Pauli operátory</span><span class="sxs-lookup"><span data-stu-id="5411b-120">Pauli Operators</span></span> ####

<span data-ttu-id="5411b-121">Operace <xref:microsoft.quantum.intrinsic.x> implementuje operátor Pauli $X $.</span><span class="sxs-lookup"><span data-stu-id="5411b-121">The <xref:microsoft.quantum.intrinsic.x> operation implements the Pauli $X$ operator.</span></span>
<span data-ttu-id="5411b-122">Tato situace se někdy označuje také jako brána `NOT`.</span><span class="sxs-lookup"><span data-stu-id="5411b-122">This is sometimes also known as the `NOT` gate.</span></span>
<span data-ttu-id="5411b-123">Má `(Qubit => Unit is Adj + Ctl)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="5411b-123">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="5411b-124">Odpovídá qubit jednotkám:</span><span class="sxs-lookup"><span data-stu-id="5411b-124">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="5411b-125">\begin{Equation} \begin{bmatrix} 0 & 1 \\\\% FIXME: aktuálně používá napadení quadwhack.</span><span class="sxs-lookup"><span data-stu-id="5411b-125">\begin{equation} \begin{bmatrix} 0 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="5411b-126">1 & 0 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="5411b-126">1 & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="5411b-127">Operace <xref:microsoft.quantum.intrinsic.y> implementuje operátor Pauli $Y $.</span><span class="sxs-lookup"><span data-stu-id="5411b-127">The <xref:microsoft.quantum.intrinsic.y> operation implements the Pauli $Y$ operator.</span></span>
<span data-ttu-id="5411b-128">Má `(Qubit => Unit is Adj + Ctl)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="5411b-128">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="5411b-129">Odpovídá qubit jednotkám:</span><span class="sxs-lookup"><span data-stu-id="5411b-129">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="5411b-130">\begin{Equation} \begin{bmatrix} 0 &-i \\\\% FIXME: aktuálně používá napadení quadwhack.</span><span class="sxs-lookup"><span data-stu-id="5411b-130">\begin{equation} \begin{bmatrix} 0 & -i \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="5411b-131">i & 0 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="5411b-131">i & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="5411b-132">Operace <xref:microsoft.quantum.intrinsic.z> implementuje operátor Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="5411b-132">The <xref:microsoft.quantum.intrinsic.z> operation implements the Pauli $Z$ operator.</span></span>
<span data-ttu-id="5411b-133">Má `(Qubit => Unit is Adj + Ctl)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="5411b-133">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="5411b-134">Odpovídá qubit jednotkám:</span><span class="sxs-lookup"><span data-stu-id="5411b-134">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="5411b-135">\begin{Equation} \begin{bmatrix} 1 & 0 \\\\% FIXME: aktuálně používá napadení quadwhack.</span><span class="sxs-lookup"><span data-stu-id="5411b-135">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="5411b-136">0 &-1 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="5411b-136">0 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="5411b-137">Níže vidíte, že tyto transformace jsou mapované na [Bloch koule](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (osa otočení v každém případě je zvýrazněna červeně):</span><span class="sxs-lookup"><span data-stu-id="5411b-137">Below we see these transformations mapped to the [Bloch sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (the rotation axis in each case is highlighted red):</span></span>

![Pauli operace mapované na sféru Bloch](~/media/prelude_pauliBloch.png)

<span data-ttu-id="5411b-139">Je důležité si uvědomit, že použití stejné Pauliové brány dvakrát na stejný qubit zruší operaci (protože jste nyní provedli úplné otočení 2π (360 °) na povrchu Bloch koule, čímž se dorazí zpátky na výchozí bod).</span><span class="sxs-lookup"><span data-stu-id="5411b-139">It is important to note that applying the same Pauli gate twice to the same qubit cancels out the operation (because you have now performed a full rotation of 2π (360°) over the surface to the Bloch Sphere, thus arriving back at the starting point).</span></span> <span data-ttu-id="5411b-140">Tím se nám přineseme k následující identitě:</span><span class="sxs-lookup"><span data-stu-id="5411b-140">This brings us to the following identity:</span></span>

<span data-ttu-id="5411b-141">$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $</span><span class="sxs-lookup"><span data-stu-id="5411b-141">$$ X^2=Y^2=Z^2=\boldone $$</span></span>

<span data-ttu-id="5411b-142">To může být visualised v oblasti Bloch:</span><span class="sxs-lookup"><span data-stu-id="5411b-142">This can be visualised on the Bloch sphere:</span></span>

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a><span data-ttu-id="5411b-144">Další Cliffords s jedním qubit</span><span class="sxs-lookup"><span data-stu-id="5411b-144">Other Single-Qubit Cliffords</span></span> ####

<span data-ttu-id="5411b-145">Operace <xref:microsoft.quantum.intrinsic.h> implementuje bránu Hadamard.</span><span class="sxs-lookup"><span data-stu-id="5411b-145">The <xref:microsoft.quantum.intrinsic.h> operation implements the Hadamard gate.</span></span>
<span data-ttu-id="5411b-146">Tím se změní Pauli $X $ a $Z $ na osy cílového qubit, například $H \ket{0} = \ket{+} \mathrel{: =} (\ket{0} + \ket{1})/\sqrt{2}$ a $H \ket{+} = \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="5411b-146">This interchanges the Pauli $X$ and $Z$ axes of the target qubit, such that $H\ket{0} = \ket{+} \mathrel{:=} (\ket{0} + \ket{1}) / \sqrt{2}$ and $H\ket{+} = \ket{0}$.</span></span>
<span data-ttu-id="5411b-147">Má signaturu `(Qubit => Unit is Adj + Ctl)`a odpovídá qubit jednotkám:</span><span class="sxs-lookup"><span data-stu-id="5411b-147">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="5411b-148">\begin{Equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\% FIXME: aktuálně používá napadení quadwhack.</span><span class="sxs-lookup"><span data-stu-id="5411b-148">\begin{equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="5411b-149">1 &-1 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="5411b-149">1 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="5411b-150">Brána Hadamard je zvláště důležitá, protože se dá použít k vytvoření nadmnožiny{1}států $ \ket{0}$ a $ \ket.</span><span class="sxs-lookup"><span data-stu-id="5411b-150">The Hadamard gate is particularly important as it can be used to create a superposition of the $\ket{0}$ and $\ket{1}$ states.</span></span> <span data-ttu-id="5411b-151">V Blochi sféry je nejjednodušší ho představit jako rotaci $ \ket{\psi} $ kolem osy x \pi $ radiánů ($ 180 ^ \circ $) následovanou otočením (po směru hodinových ručiček) kolem osy y podle $ \ pi/2 $ radiánů ($ 90 ^ \circ $):</span><span class="sxs-lookup"><span data-stu-id="5411b-151">In the Bloch sphere representation, it is easiest to think of this as a rotation of $\ket{\psi}$ around the x-axis by $\pi$ radians ($180^\circ$) followed by a (clockwise) rotation around the y-axis by $\pi/2$ radians ($90^\circ$):</span></span>

![Hadamard operace mapovaná na sféru Bloch](~/media/prelude_hadamardBloch.png)

<span data-ttu-id="5411b-153">Operace <xref:microsoft.quantum.intrinsic.s> implementuje bránu fáze $S $.</span><span class="sxs-lookup"><span data-stu-id="5411b-153">The <xref:microsoft.quantum.intrinsic.s> operation implements the phase gate $S$.</span></span>
<span data-ttu-id="5411b-154">Toto je maticová odmocnina operace Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="5411b-154">This is the matrix square root of the Pauli $Z$ operation.</span></span>
<span data-ttu-id="5411b-155">To znamená, $S ^ 2 = Z $.</span><span class="sxs-lookup"><span data-stu-id="5411b-155">That is, $S^2 = Z$.</span></span>
<span data-ttu-id="5411b-156">Má signaturu `(Qubit => Unit is Adj + Ctl)`a odpovídá qubit jednotkám:</span><span class="sxs-lookup"><span data-stu-id="5411b-156">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="5411b-157">\begin{Equation} \begin{bmatrix} 1 & 0 \\\\% FIXME: aktuálně používá napadení quadwhack.</span><span class="sxs-lookup"><span data-stu-id="5411b-157">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="5411b-158">0 & \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="5411b-158">0 & i \end{bmatrix} \end{equation}</span></span>

#### <a name="rotations"></a><span data-ttu-id="5411b-159">Rotace</span><span class="sxs-lookup"><span data-stu-id="5411b-159">Rotations</span></span> ####

<span data-ttu-id="5411b-160">Kromě výše uvedených Pauli a Clifford operací Q # předehru poskytuje celou řadu způsobů, jak vyjádřit rotace.</span><span class="sxs-lookup"><span data-stu-id="5411b-160">In addition to the Pauli and Clifford operations above, the Q# prelude provides a variety of ways of expressing rotations.</span></span>
<span data-ttu-id="5411b-161">Jak je popsáno v [qubit operacích](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), možnost otáčení je zásadní pro algoritmy.</span><span class="sxs-lookup"><span data-stu-id="5411b-161">As described in [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), the ability to rotate is critical to quantum algorithms.</span></span>

<span data-ttu-id="5411b-162">Začneme zpětným voláním, které umožňuje vyjádřit jakoukoli operaci s jedním qubit pomocí $H $ a $T $, kde $H $ je operace Hadamard a kde \begin{Equation} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\\\% FIXME: aktuálně používá Quad back. napadení/Swagger/docs/v1.</span><span class="sxs-lookup"><span data-stu-id="5411b-162">We start by recalling that we can express any single-qubit operation using the $H$ and $T$ gates, where $H$ is the Hadamard operation, and where \begin{equation} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quad back whack hack.</span></span>
<span data-ttu-id="5411b-163">0 & e ^ {i \pi/4} \end{bmatrix} \end{Equation} je to druhá odmocnina operace <xref:microsoft.quantum.intrinsic.s>, například $T ^ 2 = S $.</span><span class="sxs-lookup"><span data-stu-id="5411b-163">0 & e^{i \pi / 4} \end{bmatrix} \end{equation} This is the square root of the <xref:microsoft.quantum.intrinsic.s> operation, such that $T^2 = S$.</span></span>
<span data-ttu-id="5411b-164">Brána $T $ je v rámci operace <xref:microsoft.quantum.intrinsic.t> implementovaná a má `(Qubit => Unit is Adj + Ctl)`signatury, což značí, že se jedná o jednotnou operaci na jednom qubit.</span><span class="sxs-lookup"><span data-stu-id="5411b-164">The $T$ gate is in turn implemented by the <xref:microsoft.quantum.intrinsic.t> operation, and has signature `(Qubit => Unit is Adj + Ctl)`, indicating that it is a unitary operation on a single-qubit.</span></span>

<span data-ttu-id="5411b-165">I když je to v zásadě dostačující pro popsání jakékoli libovolné operace s jedním qubit, mohou být v různých cílových počítačích efektivnější reprezentace o Pauli operátorech, takže předehru zahrnuje různé způsoby, jak convienently. Vyjádřete taková otočení.</span><span class="sxs-lookup"><span data-stu-id="5411b-165">Even though this is in principle sufficient to describe any arbitrary single-qubit operation, different target machines may have more efficient representations for rotations about Pauli operators, such that the prelude includes a variety of ways to convienently express such rotations.</span></span>
<span data-ttu-id="5411b-166">Nejzákladnější z nich je operace <xref:microsoft.quantum.intrinsic.r>, která implementuje otočení kolem zadané osy Pauli, \begin{Equation} R (\sigma, \phi) \mathrel{: =} \exp (-i \phi \sigma/2), \end{Equation} kde $ \sigma $ je Pauli operátor, $ \phi $ je úhel a kde $ \exp $ představuje exponenciální matrici.</span><span class="sxs-lookup"><span data-stu-id="5411b-166">The most basic of these is the <xref:microsoft.quantum.intrinsic.r> operation, which implements a rotation around a specified Pauli axis, \begin{equation} R(\sigma, \phi) \mathrel{:=} \exp(-i \phi \sigma / 2), \end{equation} where $\sigma$ is a Pauli operator, $\phi$ is an angle, and where $\exp$ represents the matrix exponential.</span></span>
<span data-ttu-id="5411b-167">Má `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`podpisů, kde první dvě části vstupu reprezentují klasické argumenty $ \sigma $ a $ \phi $, které jsou potřebné k určení jednotkového operátoru $R (\sigma, \phi) $.</span><span class="sxs-lookup"><span data-stu-id="5411b-167">It has signature `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`, where the first two parts of the input represent the classical arguments $\sigma$ and $\phi$ needed to specify the unitary operator $R(\sigma, \phi)$.</span></span>
<span data-ttu-id="5411b-168">Částečně se dá použít $ \sigma $ a $ \phi $, aby se získala operace, jejíž typ je jedna qubit jednotně.</span><span class="sxs-lookup"><span data-stu-id="5411b-168">We can partially apply $\sigma$ and $\phi$ to obtain an operation whose type is that of a single-qubit unitary.</span></span>
<span data-ttu-id="5411b-169">Například `R(PauliZ, PI() / 4, _)` má typ `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="5411b-169">For example, `R(PauliZ, PI() / 4, _)` has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

> [!NOTE]
> <span data-ttu-id="5411b-170">Operace <xref:microsoft.quantum.intrinsic.r> rozdělí vstupní úhel o 2 a násobí ho hodnotou-1.</span><span class="sxs-lookup"><span data-stu-id="5411b-170">The <xref:microsoft.quantum.intrinsic.r> operation divides the input angle by 2 and multiplies it by -1.</span></span>
> <span data-ttu-id="5411b-171">Pro $Z $ rotace to znamená, že $ \ket{0}$ eigenstate je otočeno pomocí $-\phi/$2 a $ \ket{1}$ eigenstate je otočeno $ \phi/$2, takže $ \ket{1}$ eigenstate je otočena $ \phi $ vzhledem k $ \ket{0}$ eigenstate.</span><span class="sxs-lookup"><span data-stu-id="5411b-171">For $Z$ rotations, this means that the $\ket{0}$ eigenstate is rotated by $-\phi / 2$ and the $\ket{1}$ eigenstate is rotated by $\phi / 2$, so that the $\ket{1}$ eigenstate is rotated by $\phi$ relative to the $\ket{0}$ eigenstate.</span></span>
>
> <span data-ttu-id="5411b-172">Konkrétně to znamená, že `T` a `R(PauliZ, PI() / 8, _)` se liší pouze nepodstatnými [globálními fázemi](xref:microsoft.quantum.glossary#global-phase).</span><span class="sxs-lookup"><span data-stu-id="5411b-172">In particular, this means that `T` and `R(PauliZ, PI() / 8, _)` differ only by an irrelevant [global phase](xref:microsoft.quantum.glossary#global-phase).</span></span>
> <span data-ttu-id="5411b-173">Z tohoto důvodu se $T $ někdy označuje jako brána $ \frac{\pi}{8}$-.</span><span class="sxs-lookup"><span data-stu-id="5411b-173">For this reason, $T$ is sometimes known as the $\frac{\pi}{8}$-gate.</span></span>
>
> <span data-ttu-id="5411b-174">Všimněte si také, že při otočení `PauliI` stačí použít globální fázi $ \phi/$2.</span><span class="sxs-lookup"><span data-stu-id="5411b-174">Note also that rotating around `PauliI` simply applies a global phase of $\phi / 2$.</span></span> <span data-ttu-id="5411b-175">I když tyto fáze nejsou důležité, jak je uvedeno v [koncepčních dokumentech](xref:microsoft.quantum.concepts.qubit), jsou relevantní pro kontrolované `PauliI` rotace.</span><span class="sxs-lookup"><span data-stu-id="5411b-175">While such phases are irrelevant, as argued in [the conceptual documents](xref:microsoft.quantum.concepts.qubit), they are relevant for controlled `PauliI` rotations.</span></span>

<span data-ttu-id="5411b-176">V rámci algoritmů doby použitelnosti je často užitečné vyjádřit rotace jako dyadic zlomky, jako je $ \phi = \pi k/2 ^ n $ pro některá $k \in \mathbb{Z} $ a $n \in \mathbb{N} $.</span><span class="sxs-lookup"><span data-stu-id="5411b-176">Within quantum algorithms, it is often useful to express rotations as dyadic fractions, such that $\phi = \pi k / 2^n$ for some $k \in \mathbb{Z}$ and $n \in \mathbb{N}$.</span></span>
<span data-ttu-id="5411b-177">Operace <xref:microsoft.quantum.intrinsic.rfrac> implementuje otočení kolem zadané osy Pauli pomocí této konvence.</span><span class="sxs-lookup"><span data-stu-id="5411b-177">The <xref:microsoft.quantum.intrinsic.rfrac> operation implements a rotation around a specified Pauli axis using this convention.</span></span>
<span data-ttu-id="5411b-178">Liší se od <xref:microsoft.quantum.intrinsic.r> v tom, že úhel otočení je zadán jako dva vstupy typu `Int`a interpretovány jako dyadic zlomek.</span><span class="sxs-lookup"><span data-stu-id="5411b-178">It differs from <xref:microsoft.quantum.intrinsic.r> in that the rotation angle is specified as two inputs of type `Int`, interpreted as a dyadic fraction.</span></span>
<span data-ttu-id="5411b-179">Proto `RFrac` má `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`signatury.</span><span class="sxs-lookup"><span data-stu-id="5411b-179">Thus, `RFrac` has signature `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="5411b-180">Implementuje jedinou qubit jednotk $ \exp (i \pi k \sigma/2 ^ n) $, kde $ \sigma $ je Pauli matice odpovídající prvnímu argumentu, $k $ je druhý argument a $n $ je třetí argument.</span><span class="sxs-lookup"><span data-stu-id="5411b-180">It implements the single-qubit unitary $\exp(i \pi k \sigma / 2^n)$, where $\sigma$ is the Pauli matrix corresponding to the first argument, $k$ is the second argument, and $n$ is the third argument.</span></span>
<span data-ttu-id="5411b-181">`RFrac(_,k,n,_)` je stejná jako `R(_,-πk/2^n,_)`; Všimněte si, že úhel je *záporný* pro zlomek.</span><span class="sxs-lookup"><span data-stu-id="5411b-181">`RFrac(_,k,n,_)` is the same as `R(_,-πk/2^n,_)`; note that the angle is the *negative* of the fraction.</span></span>

<span data-ttu-id="5411b-182">Operace <xref:microsoft.quantum.intrinsic.rx> implementuje otočení kolem osy Pauli $X $.</span><span class="sxs-lookup"><span data-stu-id="5411b-182">The <xref:microsoft.quantum.intrinsic.rx> operation implements a rotation around the Pauli $X$ axis.</span></span>
<span data-ttu-id="5411b-183">Má `((Double, Qubit) => Unit is Adj + Ctl)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="5411b-183">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="5411b-184">`Rx(_, _)` je stejná jako `R(PauliX, _, _)`.</span><span class="sxs-lookup"><span data-stu-id="5411b-184">`Rx(_, _)` is the same as `R(PauliX, _, _)`.</span></span>

<span data-ttu-id="5411b-185">Operace <xref:microsoft.quantum.intrinsic.ry> implementuje otočení kolem osy Pauli $Y $.</span><span class="sxs-lookup"><span data-stu-id="5411b-185">The <xref:microsoft.quantum.intrinsic.ry> operation implements a rotation around the Pauli $Y$ axis.</span></span>
<span data-ttu-id="5411b-186">Má `((Double, Qubit) => Unit is Adj + Ctl)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="5411b-186">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="5411b-187">`Ry(_, _)` je stejná jako `R(PauliY,_ , _)`.</span><span class="sxs-lookup"><span data-stu-id="5411b-187">`Ry(_, _)` is the same as `R(PauliY,_ , _)`.</span></span>

<span data-ttu-id="5411b-188">Operace <xref:microsoft.quantum.intrinsic.rz> implementuje otočení kolem osy Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="5411b-188">The <xref:microsoft.quantum.intrinsic.rz> operation implements a rotation around the Pauli $Z$ axis.</span></span>
<span data-ttu-id="5411b-189">Má `((Double, Qubit) => Unit is Adj + Ctl)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="5411b-189">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="5411b-190">`Rz(_, _)` je stejná jako `R(PauliZ, _, _)`.</span><span class="sxs-lookup"><span data-stu-id="5411b-190">`Rz(_, _)` is the same as `R(PauliZ, _, _)`.</span></span>

<span data-ttu-id="5411b-191">Operace <xref:microsoft.quantum.intrinsic.r1> implementuje rotaci o danou velikost kolem $ \ket{1}$, eigenstate $-$1 z $Z $.</span><span class="sxs-lookup"><span data-stu-id="5411b-191">The <xref:microsoft.quantum.intrinsic.r1> operation implements a rotation by the given amount around $\ket{1}$, the $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="5411b-192">Má `((Double, Qubit) => Unit is Adj + Ctl)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="5411b-192">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="5411b-193">`R1(phi,_)` je stejná jako `R(PauliZ,phi,_)` následovaná `R(PauliI,-phi,_)`.</span><span class="sxs-lookup"><span data-stu-id="5411b-193">`R1(phi,_)` is the same as `R(PauliZ,phi,_)` followed by `R(PauliI,-phi,_)`.</span></span>

<span data-ttu-id="5411b-194">Operace <xref:microsoft.quantum.intrinsic.r1frac> implementuje zlomkové otočení o zadanou hodnotu kolem hodnoty Z = 1 eigenstate.</span><span class="sxs-lookup"><span data-stu-id="5411b-194">The <xref:microsoft.quantum.intrinsic.r1frac> operation implements a fractional rotation by the given amount around the Z=1 eigenstate.</span></span>
<span data-ttu-id="5411b-195">Má `((Int,Int, Qubit) => Unit is Adj + Ctl)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="5411b-195">It has signature `((Int,Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="5411b-196">`R1Frac(k,n,_)` je stejná jako `RFrac(PauliZ,-k.n+1,_)` následovaná `RFrac(PauliI,k,n+1,_)`.</span><span class="sxs-lookup"><span data-stu-id="5411b-196">`R1Frac(k,n,_)` is the same as `RFrac(PauliZ,-k.n+1,_)` followed by `RFrac(PauliI,k,n+1,_)`.</span></span>

<span data-ttu-id="5411b-197">Příklad operace otočení (kolem osy Pauli $Z $, v této instanci) mapované na Bloch koule, je uveden níže:</span><span class="sxs-lookup"><span data-stu-id="5411b-197">An example of a rotation operation (around the Pauli $Z$ axis, in this instance) mapped onto the Bloch sphere is shown below:</span></span>

![Operace otočení mapovaná na sféru Bloch](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a><span data-ttu-id="5411b-199">Operace s více qubit</span><span class="sxs-lookup"><span data-stu-id="5411b-199">Multi-Qubit Operations</span></span> ####

<span data-ttu-id="5411b-200">Kromě qubit operací uvedených výše definuje předehru také několik operací s více qubit.</span><span class="sxs-lookup"><span data-stu-id="5411b-200">In addition to the single-qubit operations above, the prelude also defines several multi-qubit operations.</span></span>

<span data-ttu-id="5411b-201">Nejprve operace <xref:microsoft.quantum.intrinsic.cnot> provádí standardní bránu řízenou`NOT`, \begin{Equation} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="5411b-201">First, the <xref:microsoft.quantum.intrinsic.cnot> operation performs a standard controlled-`NOT` gate, \begin{equation} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}.</span></span>
<span data-ttu-id="5411b-202">\end{Equation} má signatura `((Qubit, Qubit) => Unit is Adj + Ctl)`, která představuje, že $ \operatorname{CNOT} $ funguje unitarily na dvou individuálních qubits.</span><span class="sxs-lookup"><span data-stu-id="5411b-202">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`, representing that $\operatorname{CNOT}$ acts unitarily on two individual qubits.</span></span>
<span data-ttu-id="5411b-203">`CNOT(q1, q2)` je stejná jako `(Controlled X)([q1], q2)`.</span><span class="sxs-lookup"><span data-stu-id="5411b-203">`CNOT(q1, q2)` is the same as `(Controlled X)([q1], q2)`.</span></span>
<span data-ttu-id="5411b-204">Vzhledem k tomu, že `Controlled` funktor umožňuje řízení v registru, používáme `[q1]` literálu pole k označení toho, že chceme mít pouze jeden ovládací prvek.</span><span class="sxs-lookup"><span data-stu-id="5411b-204">Since the `Controlled` functor allows for controlling on a register, we use the array literal `[q1]` to indicate that we want only the one control.</span></span>

<span data-ttu-id="5411b-205">Operace <xref:microsoft.quantum.intrinsic.ccnot> provádí nebránu se dvěma procesory, někdy také označované jako brána Toffoli.</span><span class="sxs-lookup"><span data-stu-id="5411b-205">The <xref:microsoft.quantum.intrinsic.ccnot> operation performs doubly-controlled NOT gate, sometimes also known as the Toffoli gate.</span></span>
<span data-ttu-id="5411b-206">Má `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="5411b-206">It has signature `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="5411b-207">`CCNOT(q1, q2, q3)` je stejná jako `(Controlled X)([q1, q2], q3)`.</span><span class="sxs-lookup"><span data-stu-id="5411b-207">`CCNOT(q1, q2, q3)` is the same as `(Controlled X)([q1, q2], q3)`.</span></span>

<span data-ttu-id="5411b-208">Operace <xref:microsoft.quantum.intrinsic.swap> proměňuje stavy se dvěma qubitsy.</span><span class="sxs-lookup"><span data-stu-id="5411b-208">The <xref:microsoft.quantum.intrinsic.swap> operation swaps the quantum states of two qubits.</span></span>
<span data-ttu-id="5411b-209">To znamená, že implementuje jednotnou matrici \begin{Equation} \operatorname{SWAP} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="5411b-209">That is, it implements the unitary matrix \begin{equation} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}.</span></span>
<span data-ttu-id="5411b-210">\end{Equation} má podpis `((Qubit, Qubit) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="5411b-210">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="5411b-211">`SWAP(q1,q2)` je ekvivalentní `CNOT(q1, q2)`, po kterém následuje `CNOT(q2, q1)` a potom `CNOT(q1, q2)`.</span><span class="sxs-lookup"><span data-stu-id="5411b-211">`SWAP(q1,q2)` is equivalent to `CNOT(q1, q2)` followed by `CNOT(q2, q1)` and then `CNOT(q1, q2)`.</span></span>

> [!NOTE]
> <span data-ttu-id="5411b-212">Brána *swap není stejná* jako změna uspořádání prvků proměnné s typem `Qubit[]`.</span><span class="sxs-lookup"><span data-stu-id="5411b-212">The SWAP gate is *not* the same as rearranging the elements of a variable with type `Qubit[]`.</span></span>
> <span data-ttu-id="5411b-213">Použití `SWAP(q1, q2)` způsobí změnu stavu qubits, na který odkazuje `q1` a `q2`, zatímco `let swappedRegister = [q2, q1];` má vliv na to, jak odkazujeme na tyto qubits.</span><span class="sxs-lookup"><span data-stu-id="5411b-213">Applying `SWAP(q1, q2)` causes a change to the state of the qubits referred to by `q1` and `q2`, while `let swappedRegister = [q2, q1];` only affects how we refer to those qubits.</span></span>
> <span data-ttu-id="5411b-214">Kromě toho `(Controlled SWAP)([q0], (q1, q2))` umožňuje, aby bylo `SWAP` podmíněně ve stavu třetího qubit, který nemůžeme reprezentovat prvky.</span><span class="sxs-lookup"><span data-stu-id="5411b-214">Moreover, `(Controlled SWAP)([q0], (q1, q2))` allows for `SWAP` to be conditioned on the state of a third qubit, which we cannot represent by rearranging elements.</span></span>
> <span data-ttu-id="5411b-215">Brána kontrolovaného zahození, označovaná také jako brána Fredkin, je dostatečně výkonná pro zahrnutí všech klasických výpočtů.</span><span class="sxs-lookup"><span data-stu-id="5411b-215">The controlled-SWAP gate, also known as the Fredkin gate, is powerful enough to include all classical computation.</span></span>

<span data-ttu-id="5411b-216">Nakonec předehru poskytuje dvě operace pro reprezentaci exponenciálních hodnot operátorů Pauli s více qubit.</span><span class="sxs-lookup"><span data-stu-id="5411b-216">Finally, the prelude provides two operations for representing exponentials of multi-qubit Pauli operators.</span></span>
<span data-ttu-id="5411b-217">Operace <xref:microsoft.quantum.intrinsic.exp> provádí rotaci na základě tensor produktu Paulich matric, jak je znázorněno v qubit jednotkovém \begin{Equation} \operatorname{Exp} (\vec{\sigma}, \phi) \mathrel{: =} \exp\left (i \phi \sigma_0 \otimes \sigma_1 \otimes \ cdots \otimes \sigma_n \right), \end{Equation} kde $ \vec{\sigma} = (\sigma_0, \sigma_1, \dots, \sigma_n) $ je sekvence operátorů qubit s jedním Pauli a kde $ \phi $ je úhel.</span><span class="sxs-lookup"><span data-stu-id="5411b-217">The <xref:microsoft.quantum.intrinsic.exp> operation performs a rotation based on a tensor product of Pauli matrices, as represented by the multi-qubit unitary \begin{equation} \operatorname{Exp}(\vec{\sigma}, \phi) \mathrel{:=} \exp\left(i \phi \sigma_0 \otimes \sigma_1 \otimes \cdots \otimes \sigma_n \right), \end{equation} where $\vec{\sigma} = (\sigma_0, \sigma_1, \dots, \sigma_n)$ is a sequence of single-qubit Pauli operators, and where $\phi$ is an angle.</span></span>
<span data-ttu-id="5411b-218">`Exp` rotace představuje $ \vec{\sigma} $ jako pole `Pauli` prvků, takže má `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`signatury.</span><span class="sxs-lookup"><span data-stu-id="5411b-218">The `Exp` rotation represents $\vec{\sigma}$ as an array of `Pauli` elements, such that it has signature `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="5411b-219">Operace <xref:microsoft.quantum.intrinsic.expfrac> provádí stejnou rotaci pomocí dyadic zlomkového zápisu popsaného výše.</span><span class="sxs-lookup"><span data-stu-id="5411b-219">The <xref:microsoft.quantum.intrinsic.expfrac> operation performs the same rotation, using the dyadic fraction notation discussed above.</span></span>
<span data-ttu-id="5411b-220">Má `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="5411b-220">It has signature `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

> [!WARNING]
> <span data-ttu-id="5411b-221">Exponenciální podíly tensor produktu operátorů Pauli nejsou stejné jako tensor produkty exponenciálních operátorů Pauli.</span><span class="sxs-lookup"><span data-stu-id="5411b-221">Exponentials of the tensor product of Pauli operators are not the same as tensor products of the exponentials of Pauli operators.</span></span>
> <span data-ttu-id="5411b-222">To znamená, $e ^ {i (Z \otimes Z) \phi} \Ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $.</span><span class="sxs-lookup"><span data-stu-id="5411b-222">That is, $e^{i (Z \otimes Z) \phi} \ne e^{i Z \phi} \otimes e^{i Z \phi}$.</span></span>

### <a name="measurements"></a><span data-ttu-id="5411b-223">Měření</span><span class="sxs-lookup"><span data-stu-id="5411b-223">Measurements</span></span> ###

<span data-ttu-id="5411b-224">Při měření `Zero` odpovídá eigenvalue a-1 eigenvalueému operátoru, který má výsledek `One`.</span><span class="sxs-lookup"><span data-stu-id="5411b-224">When measuring, the +1 eigenvalue of the operator being measured corresponds to a `Zero` result, and the -1 eigenvalue to a `One` result.</span></span>

> [!NOTE]
> <span data-ttu-id="5411b-225">I když se tato konvence může zdát lichá, má dvě skvělé výhody.</span><span class="sxs-lookup"><span data-stu-id="5411b-225">While this convention might seem odd, it has two very nice advantages.</span></span>
> <span data-ttu-id="5411b-226">Nejprve se zobrazí výsledek $ \ket{0}$, který je reprezentován hodnotou `Result` `Zero`, zatímco sledování $ \ket{1}$ odpovídá `One`.</span><span class="sxs-lookup"><span data-stu-id="5411b-226">First, observing the outcome $\ket{0}$ is represented by the `Result` value `Zero`, while observing $\ket{1}$ corresponds to `One`.</span></span>
> <span data-ttu-id="5411b-227">Za druhé můžeme napsat, že eigenvalue $ \lambda $ odpovídající výsledku $r $ je $ \lambda = (-1) ^ r $.</span><span class="sxs-lookup"><span data-stu-id="5411b-227">Second, we can write out that the eigenvalue $\lambda$ corresponding to a result $r$ is $\lambda = (-1)^r$.</span></span>

<span data-ttu-id="5411b-228">Měření operací nepodporuje ani `Adjoint` ani `Controlled` funktor.</span><span class="sxs-lookup"><span data-stu-id="5411b-228">Measurement operations support neither the `Adjoint` nor the `Controlled` functor.</span></span>

<span data-ttu-id="5411b-229">Operace <xref:microsoft.quantum.intrinsic.measure> provádí společné měření jednoho nebo více qubits v zadaném produktu Pauli Operators.</span><span class="sxs-lookup"><span data-stu-id="5411b-229">The <xref:microsoft.quantum.intrinsic.measure> operation performs a joint measurement of one or more qubits in the specified product of Pauli operators.</span></span>
<span data-ttu-id="5411b-230">Pokud se pole Pauli a qubit liší od různých délek, operace se nezdařila.</span><span class="sxs-lookup"><span data-stu-id="5411b-230">If the Pauli array and qubit array are different lengths, then the operation fails.</span></span>
<span data-ttu-id="5411b-231">`Measure` má `((Pauli[], Qubit[]) => Result)`signatury.</span><span class="sxs-lookup"><span data-stu-id="5411b-231">`Measure` has signature `((Pauli[], Qubit[]) => Result)`.</span></span>

<span data-ttu-id="5411b-232">Počítejte s tím, že společná měření není shodná s měřením jednotlivých qubit jednotlivě.</span><span class="sxs-lookup"><span data-stu-id="5411b-232">Note that a joint measurement is not the same as measuring each qubit individually.</span></span>
<span data-ttu-id="5411b-233">Zvažte například stav $ \ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$.</span><span class="sxs-lookup"><span data-stu-id="5411b-233">For example, consider the state $\ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$.</span></span>
<span data-ttu-id="5411b-234">Měření $Z _0 $ a $Z _1 každou jednotlivě získáme výsledky $r _0 = $1 a $r _1 = $1.</span><span class="sxs-lookup"><span data-stu-id="5411b-234">Measuring $Z_0$ and $Z_1$ each individually, we get the results $r_0 = 1$ and $r_1 = 1$.</span></span>
<span data-ttu-id="5411b-235">Měření $Z _0 Z_1 $ ale získáme jeden výsledek $r _ {\textrm{Joint}} = $0, což představuje, že dvojice $ \ket{11}$ je kladná.</span><span class="sxs-lookup"><span data-stu-id="5411b-235">Measuring $Z_0 Z_1$, however, we get the single result $r_{\textrm{joint}} = 0$, representing that the pairity of $\ket{11}$ is positive.</span></span>
<span data-ttu-id="5411b-236">Neumísťujte jinak $ (-1) ^ {r_0 + r_1} = (-1) ^ R_ {\textrm{Joint}}) $.</span><span class="sxs-lookup"><span data-stu-id="5411b-236">Put differently, $(-1)^{r_0 + r_1} = (-1)^r_{\textrm{joint}})$.</span></span>
<span data-ttu-id="5411b-237">Vzhledem k tomu, že jsme se dozvěděli *jenom* o paritě z tohoto měření, jsou zachovány všechny informace o všech procesorech, které jsou reprezentované na pozici mezi 2 2 qubit stavy kladné parity, $ \ket{00}$ a $ \ket{11}$.</span><span class="sxs-lookup"><span data-stu-id="5411b-237">Critically, since we *only* learn the parity from this measurement, any quantum information represented in the superposition between the two two-qubit states of positive parity, $\ket{00}$ and $\ket{11}$, is preserved.</span></span>
<span data-ttu-id="5411b-238">Tato vlastnost bude v podstatě pozdější, protože se zabývá opravami chyb.</span><span class="sxs-lookup"><span data-stu-id="5411b-238">This property will be essential later, as we discuss error correction.</span></span>

<span data-ttu-id="5411b-239">Pro usnadnění práce předehru poskytuje také dvě další operace pro měření qubits.</span><span class="sxs-lookup"><span data-stu-id="5411b-239">For convenience, the prelude also provides two other operations for measuring qubits.</span></span>
<span data-ttu-id="5411b-240">Vzhledem k tomu, že provádění qubit měření je poměrně běžné, definuje předehru pro tento případ Zkrácený Zkrácený tvar.</span><span class="sxs-lookup"><span data-stu-id="5411b-240">First, since performing single-qubit measurements is quite common, the prelude defines a shorthand for this case.</span></span>
<span data-ttu-id="5411b-241">Operace <xref:microsoft.quantum.intrinsic.m> měří operátor Pauli $Z $ v jednom qubit a má `(Qubit => Result)`podpisu.</span><span class="sxs-lookup"><span data-stu-id="5411b-241">The <xref:microsoft.quantum.intrinsic.m> operation measures the Pauli $Z$ operator on a single qubit, and has signature `(Qubit => Result)`.</span></span>
<span data-ttu-id="5411b-242">`M(q)` je ekvivalentem `Measure([PauliZ], [q])`.</span><span class="sxs-lookup"><span data-stu-id="5411b-242">`M(q)` is equivalent to `Measure([PauliZ], [q])`.</span></span>

<span data-ttu-id="5411b-243"><xref:microsoft.quantum.measurement.multim> měří operátor Pauli $Z $ *samostatně* pro každé pole qubits a vrátí *pole* `Result` hodnot získaných pro každé qubit.</span><span class="sxs-lookup"><span data-stu-id="5411b-243">The <xref:microsoft.quantum.measurement.multim> measures the Pauli $Z$ operator *separately* on each of an array of qubits, returning the *array* of `Result` values obtained for each qubit.</span></span>
<span data-ttu-id="5411b-244">V některých případech je to možné optimalizovat.</span><span class="sxs-lookup"><span data-stu-id="5411b-244">In some cases this can be optimized.</span></span> <span data-ttu-id="5411b-245">Má signaturu (`Qubit[] => Result[])`.</span><span class="sxs-lookup"><span data-stu-id="5411b-245">It has signature (`Qubit[] => Result[])`.</span></span>
<span data-ttu-id="5411b-246">`MultiM(qs)` je ekvivalentní:</span><span class="sxs-lookup"><span data-stu-id="5411b-246">`MultiM(qs)` is equivalent to:</span></span>

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a><span data-ttu-id="5411b-247">Funkce rozšíření a operace</span><span class="sxs-lookup"><span data-stu-id="5411b-247">Extension Functions and Operations</span></span> ##

<span data-ttu-id="5411b-248">Kromě toho předehru definuje bohatou sadu matematických a typových funkcí pro převod na úrovni .NET pro použití v kódu Q #.</span><span class="sxs-lookup"><span data-stu-id="5411b-248">In addition, the prelude defines a rich set of mathematical and type conversion functions at the .NET level for use within Q# code.</span></span>
<span data-ttu-id="5411b-249">Například obor názvů <xref:microsoft.quantum.extensions.math> definuje užitečné operace, jako jsou <xref:microsoft.quantum.extensions.math.sin> a <xref:microsoft.quantum.extensions.math.log>.</span><span class="sxs-lookup"><span data-stu-id="5411b-249">For instance, the <xref:microsoft.quantum.extensions.math> namespace defines useful operations such as <xref:microsoft.quantum.extensions.math.sin> and <xref:microsoft.quantum.extensions.math.log>.</span></span>
<span data-ttu-id="5411b-250">Implementace poskytovaná vývojovou sadou pro plnění z více systémů používá knihovnu klasických tříd .NET Base, a proto může zahrnovat další komunikaci s výměnou mezi programy a jejich klasickými ovladači.</span><span class="sxs-lookup"><span data-stu-id="5411b-250">The implementation provided by the Quantum Development Kit uses the classical .NET base class library, and thus may involve an additional communications round trip between quantum programs and their classical drivers.</span></span>
<span data-ttu-id="5411b-251">I když to nepředstavuje problém pro místní simulátor, může to být problém s výkonem při použití vzdáleného simulátoru nebo skutečného hardwaru jako cílového počítače.</span><span class="sxs-lookup"><span data-stu-id="5411b-251">While this does not present a problem for a local simulator, this can be a performance issue when using a remote simulator or actual hardware as a target machine.</span></span>
<span data-ttu-id="5411b-252">V takovém případě může jednotlivý cílový počítač zmírnit tento dopad na výkon tím, že tyto operace přepíše verze, které jsou pro konkrétní systém efektivnější.</span><span class="sxs-lookup"><span data-stu-id="5411b-252">That said, an individual target machine may mitigate this performance impact by overriding these operations with versions that are more efficient for that particular system.</span></span>

### <a name="math"></a><span data-ttu-id="5411b-253">Matematický</span><span class="sxs-lookup"><span data-stu-id="5411b-253">Math</span></span> ###

<span data-ttu-id="5411b-254">Obor názvů <xref:microsoft.quantum.extensions.math> poskytuje mnoho užitečných funkcí z [`System.Math` třídy](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1)základní knihovny třídy .NET.</span><span class="sxs-lookup"><span data-stu-id="5411b-254">The <xref:microsoft.quantum.extensions.math> namespace provides many useful functions from the .NET base class library's [`System.Math` class](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1).</span></span>
<span data-ttu-id="5411b-255">Tyto funkce lze použít stejným způsobem jako jakékoli jiné funkce Q #:</span><span class="sxs-lookup"><span data-stu-id="5411b-255">These functions can be used in the same manner as any other Q# functions:</span></span>

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

<span data-ttu-id="5411b-256">V případě přetížení statické metody rozhraní .NET na základě typu argumentů je odpovídající funkce Q # opatřena příponou, která označuje typ jejího vstupu:</span><span class="sxs-lookup"><span data-stu-id="5411b-256">Where a .NET static method has been overloaded based on the type of its arguments, the corresponding Q# function is annotated with a suffix indicating the type of its input:</span></span>

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a><span data-ttu-id="5411b-257">Bitové operace</span><span class="sxs-lookup"><span data-stu-id="5411b-257">Bitwise Operations</span></span> ###

<span data-ttu-id="5411b-258">Nakonec <xref:microsoft.quantum.extensions.bitwise> obor názvů poskytuje několik užitečných funkcí pro manipulaci s celými čísly prostřednictvím bitových operátorů.</span><span class="sxs-lookup"><span data-stu-id="5411b-258">Finally, the <xref:microsoft.quantum.extensions.bitwise> namespace provides several useful functions for manipulating integers through bitwise operators.</span></span>
<span data-ttu-id="5411b-259">Například <xref:microsoft.quantum.extensions.bitwise.parity> vrátí bitovou paritu celého čísla jako jiné celé číslo.</span><span class="sxs-lookup"><span data-stu-id="5411b-259">For instance, <xref:microsoft.quantum.extensions.bitwise.parity> returns the bitwise parity of an integer as another integer.</span></span>