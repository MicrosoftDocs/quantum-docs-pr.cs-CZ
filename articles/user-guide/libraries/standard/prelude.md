---
title: Vnitřní operace a funkce v QDK
description: Seznamte se s vnitřními operacemi a funkcemi v QDK, včetně klasických funkcí a operací s jednotkou, rotací a měřením.
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.prelude
no-loc:
- Q#
- $$v
ms.openlocfilehash: dd507d0c644ae711a5e5a1dff9156f571cb0fa92
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833543"
---
# <a name="the-prelude"></a><span data-ttu-id="d5623-103">Předehru</span><span class="sxs-lookup"><span data-stu-id="d5623-103">The Prelude</span></span> #

<span data-ttu-id="d5623-104">Q#Kompilátor a cílové počítače, které jsou součástí vývojové sady pro práci po částech, poskytují sadu vnitřních funkcí a operací, které se dají použít při psaní programů v poli Q# .</span><span class="sxs-lookup"><span data-stu-id="d5623-104">The Q# compiler and the target machines included with the Quantum Development Kit provide a set of intrinsic functions and operations that can be used when writing quantum programs in Q#.</span></span>

## <a name="intrinsic-operations-and-functions"></a><span data-ttu-id="d5623-105">Vnitřní operace a funkce</span><span class="sxs-lookup"><span data-stu-id="d5623-105">Intrinsic Operations and Functions</span></span> ##

<span data-ttu-id="d5623-106">Vnitřní operace definované ve standardní knihovně zhruba spadají do jedné z několika kategorií:</span><span class="sxs-lookup"><span data-stu-id="d5623-106">The intrinsic operations defined in the standard library roughly fall into one of several categories:</span></span>

- <span data-ttu-id="d5623-107">Základní klasické funkce shromážděné v <xref:microsoft.quantum.core> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="d5623-107">Essential classical functions, collected in the <xref:microsoft.quantum.core> namespace.</span></span>
- <span data-ttu-id="d5623-108">Operace, které představují unitaries tvořené [Clifford a $T $ branami](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="d5623-108">Operations representing unitaries composed of [Clifford and $T$ gates](xref:microsoft.quantum.concepts.qubit).</span></span>
- <span data-ttu-id="d5623-109">Operace představující rotace různých operátorů.</span><span class="sxs-lookup"><span data-stu-id="d5623-109">Operations representing rotations about various operators.</span></span>
- <span data-ttu-id="d5623-110">Operace implementující měření.</span><span class="sxs-lookup"><span data-stu-id="d5623-110">Operations implementing measurements.</span></span>

<span data-ttu-id="d5623-111">Vzhledem k tomu, že sada Clifford + $T $ je [univerzální](xref:microsoft.quantum.concepts.multiple-qubits) pro práci s výpočetním prostředím, tyto operace postačují k tomu, aby se v negligibly malé chybě vyimplementovala jakákoli algoritmus.</span><span class="sxs-lookup"><span data-stu-id="d5623-111">Since the Clifford + $T$ gate set is [universal](xref:microsoft.quantum.concepts.multiple-qubits) for quantum computing, these operations suffice to approximately implement any quantum algorithm within negligibly small error.</span></span>
<span data-ttu-id="d5623-112">Díky poskytování rotací Q# umožňuje programátorům pracovat v rámci jedné qubit jednotkové a CNOTové knihovny brány.</span><span class="sxs-lookup"><span data-stu-id="d5623-112">By providing rotations as well, Q# allows the programmer to work within the single qubit unitary and CNOT gate library.</span></span> <span data-ttu-id="d5623-113">Tato knihovna je mnohem jednodušší, protože nepotřebuje programátora přímo vyjádřit $T Clifford a dekompozici $, protože pro kompilaci jednoduchých qubit unitaries do Clifford a $T $ Branch existují vysoce efektivní metody (Další informace najdete [tady](xref:microsoft.quantum.more-information) ).</span><span class="sxs-lookup"><span data-stu-id="d5623-113">This library is much easier to think about because it does not  require the programmer to directly express the Clifford + $T$ decomposition and because highly efficient methods exist for compiling single qubit unitaries into Clifford and $T$ gates (see [here](xref:microsoft.quantum.more-information) for more information).</span></span>

<span data-ttu-id="d5623-114">Pokud je to možné, operace definované v předehru, které fungují na qubits, umožňují použití `Controlled` varianty, takže cílový počítač provede příslušné rozklady.</span><span class="sxs-lookup"><span data-stu-id="d5623-114">Where possible, the operations defined in the prelude which act on qubits allow for applying the `Controlled` variant, such that the target machine will perform the appropriate decomposition.</span></span>

<span data-ttu-id="d5623-115">Mnohé z funkcí a operací, které jsou definovány v této části předehru, jsou v @"microsoft.quantum.intrinsic" oboru názvů, takže většina Q# zdrojových souborů bude obsahovat `open Microsoft.Quantum.Intrinsic;` direktivu hned po počáteční deklaraci oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="d5623-115">Many of the functions and operations defined in this portion of the prelude are in the @"microsoft.quantum.intrinsic" namespace, such that most Q# source files will have an `open Microsoft.Quantum.Intrinsic;` directive immediately following the initial namespace declaration.</span></span>
<span data-ttu-id="d5623-116"><xref:microsoft.quantum.core>Obor názvů se automaticky otevře, takže funkce, jako například, <xref:microsoft.quantum.core.length> lze použít bez `open` příkazu.</span><span class="sxs-lookup"><span data-stu-id="d5623-116">The <xref:microsoft.quantum.core> namespace is automatically opened, so that functions such as <xref:microsoft.quantum.core.length> can be used without an `open` statement at all.</span></span>

### <a name="common-single-qubit-unitary-operations"></a><span data-ttu-id="d5623-117">Běžné operace s jedním qubit jednotkou</span><span class="sxs-lookup"><span data-stu-id="d5623-117">Common Single-Qubit Unitary Operations</span></span> ###

<span data-ttu-id="d5623-118">Předehru také definuje mnoho běžných [qubit operací](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span><span class="sxs-lookup"><span data-stu-id="d5623-118">The prelude also defines many common [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>
<span data-ttu-id="d5623-119">Všechny tyto operace umožňují `Controlled` `Adjoint` funktory i.</span><span class="sxs-lookup"><span data-stu-id="d5623-119">All of these operations allow both the `Controlled` and `Adjoint` functors.</span></span>

#### <a name="pauli-operators"></a><span data-ttu-id="d5623-120">Pauli operátory</span><span class="sxs-lookup"><span data-stu-id="d5623-120">Pauli Operators</span></span> ####

<span data-ttu-id="d5623-121"><xref:microsoft.quantum.intrinsic.x>Operace implementuje operátor Pauli $X $.</span><span class="sxs-lookup"><span data-stu-id="d5623-121">The <xref:microsoft.quantum.intrinsic.x> operation implements the Pauli $X$ operator.</span></span>
<span data-ttu-id="d5623-122">Tato situace se někdy označuje také jako `NOT` Brána.</span><span class="sxs-lookup"><span data-stu-id="d5623-122">This is sometimes also known as the `NOT` gate.</span></span>
<span data-ttu-id="d5623-123">Má signaturu `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-123">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="d5623-124">Odpovídá qubit jednotkám:</span><span class="sxs-lookup"><span data-stu-id="d5623-124">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="d5623-125">\begin{Equation} \begin{bmatrix} 0 & 1 \\ \\ % fixme: aktuálně používá napadení quadwhack.</span><span class="sxs-lookup"><span data-stu-id="d5623-125">\begin{equation} \begin{bmatrix} 0 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="d5623-126">1 & 0 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="d5623-126">1 & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="d5623-127"><xref:microsoft.quantum.intrinsic.y>Operace implementuje operátor Pauli $Y $.</span><span class="sxs-lookup"><span data-stu-id="d5623-127">The <xref:microsoft.quantum.intrinsic.y> operation implements the Pauli $Y$ operator.</span></span>
<span data-ttu-id="d5623-128">Má signaturu `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-128">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="d5623-129">Odpovídá qubit jednotkám:</span><span class="sxs-lookup"><span data-stu-id="d5623-129">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="d5623-130">\begin{Equation} \begin{bmatrix} 0 &-i \\ \\ % fixme: aktuálně používá napadení quadwhack.</span><span class="sxs-lookup"><span data-stu-id="d5623-130">\begin{equation} \begin{bmatrix} 0 & -i \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="d5623-131">i & 0 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="d5623-131">i & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="d5623-132"><xref:microsoft.quantum.intrinsic.z>Operace implementuje operátor Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="d5623-132">The <xref:microsoft.quantum.intrinsic.z> operation implements the Pauli $Z$ operator.</span></span>
<span data-ttu-id="d5623-133">Má signaturu `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-133">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="d5623-134">Odpovídá qubit jednotkám:</span><span class="sxs-lookup"><span data-stu-id="d5623-134">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="d5623-135">\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % fixme: aktuálně používá napadení quadwhack.</span><span class="sxs-lookup"><span data-stu-id="d5623-135">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="d5623-136">0 &-1 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="d5623-136">0 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="d5623-137">Níže vidíte, že tyto transformace jsou mapované na [Bloch koule](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (osa otočení v každém případě je zvýrazněna červeně):</span><span class="sxs-lookup"><span data-stu-id="d5623-137">Below we see these transformations mapped to the [Bloch sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (the rotation axis in each case is highlighted red):</span></span>

![Pauli operace mapované na sféru Bloch](~/media/prelude_pauliBloch.png)

<span data-ttu-id="d5623-139">Je důležité si uvědomit, že použití stejné Pauliové brány dvakrát na stejný qubit zruší operaci (protože jste nyní provedli úplné otočení 2π (360 °) na povrchu Bloch koule, čímž se dorazí zpátky na výchozí bod).</span><span class="sxs-lookup"><span data-stu-id="d5623-139">It is important to note that applying the same Pauli gate twice to the same qubit cancels out the operation (because you have now performed a full rotation of 2π (360°) over the surface to the Bloch Sphere, thus arriving back at the starting point).</span></span> <span data-ttu-id="d5623-140">Tím se nám přineseme k následující identitě:</span><span class="sxs-lookup"><span data-stu-id="d5623-140">This brings us to the following identity:</span></span>

<span data-ttu-id="d5623-141">$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $</span><span class="sxs-lookup"><span data-stu-id="d5623-141">$$ X^2=Y^2=Z^2=\boldone $$</span></span>

<span data-ttu-id="d5623-142">To může být visualised v oblasti Bloch:</span><span class="sxs-lookup"><span data-stu-id="d5623-142">This can be visualised on the Bloch sphere:</span></span>

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a><span data-ttu-id="d5623-144">Další Cliffords s jedním qubit</span><span class="sxs-lookup"><span data-stu-id="d5623-144">Other Single-Qubit Cliffords</span></span> ####

<span data-ttu-id="d5623-145">Tato <xref:microsoft.quantum.intrinsic.h> operace implementuje bránu Hadamard.</span><span class="sxs-lookup"><span data-stu-id="d5623-145">The <xref:microsoft.quantum.intrinsic.h> operation implements the Hadamard gate.</span></span>
<span data-ttu-id="d5623-146">Tím se změní Pauli $X $ a $Z $ na osy cílového qubit, například $H \ket {0} = \ket{+} \mathrel{: =} (\ket {0} + \ket {1} )/\sqrt {2} $ a $H \ket{+} = \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="d5623-146">This interchanges the Pauli $X$ and $Z$ axes of the target qubit, such that $H\ket{0} = \ket{+} \mathrel{:=} (\ket{0} + \ket{1}) / \sqrt{2}$ and $H\ket{+} = \ket{0}$.</span></span>
<span data-ttu-id="d5623-147">Má signaturu `(Qubit => Unit is Adj + Ctl)` a odpovídá qubit jednotkám v jednom:</span><span class="sxs-lookup"><span data-stu-id="d5623-147">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="d5623-148">\begin{Equation} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ % fixme: aktuálně používá napadení quadwhack.</span><span class="sxs-lookup"><span data-stu-id="d5623-148">\begin{equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="d5623-149">1 &-1 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="d5623-149">1 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="d5623-150">Brána Hadamard je zvláště důležitá, protože se dá použít k vytvoření nadmnožiny {0} stavů $ \ket $ a $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="d5623-150">The Hadamard gate is particularly important as it can be used to create a superposition of the $\ket{0}$ and $\ket{1}$ states.</span></span> <span data-ttu-id="d5623-151">V Blochi sféry je nejjednodušší ho představit jako rotaci $ \ket{\psi} $ kolem osy x \pi $ radiánů ($ 180 ^ \circ $) následovanou otočením (po směru hodinových ručiček) kolem osy y podle $ \ pi/2 $ radiánů ($ 90 ^ \circ $):</span><span class="sxs-lookup"><span data-stu-id="d5623-151">In the Bloch sphere representation, it is easiest to think of this as a rotation of $\ket{\psi}$ around the x-axis by $\pi$ radians ($180^\circ$) followed by a (clockwise) rotation around the y-axis by $\pi/2$ radians ($90^\circ$):</span></span>

![Hadamard operace mapovaná na sféru Bloch](~/media/prelude_hadamardBloch.png)

<span data-ttu-id="d5623-153">Tato <xref:microsoft.quantum.intrinsic.s> operace implementuje bránu fáze $S $.</span><span class="sxs-lookup"><span data-stu-id="d5623-153">The <xref:microsoft.quantum.intrinsic.s> operation implements the phase gate $S$.</span></span>
<span data-ttu-id="d5623-154">Toto je maticová odmocnina operace Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="d5623-154">This is the matrix square root of the Pauli $Z$ operation.</span></span>
<span data-ttu-id="d5623-155">To znamená, $S ^ 2 = Z $.</span><span class="sxs-lookup"><span data-stu-id="d5623-155">That is, $S^2 = Z$.</span></span>
<span data-ttu-id="d5623-156">Má signaturu `(Qubit => Unit is Adj + Ctl)` a odpovídá qubit jednotkám v jednom:</span><span class="sxs-lookup"><span data-stu-id="d5623-156">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="d5623-157">\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % fixme: aktuálně používá napadení quadwhack.</span><span class="sxs-lookup"><span data-stu-id="d5623-157">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="d5623-158">0 & \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="d5623-158">0 & i \end{bmatrix} \end{equation}</span></span>

#### <a name="rotations"></a><span data-ttu-id="d5623-159">Plány střídání</span><span class="sxs-lookup"><span data-stu-id="d5623-159">Rotations</span></span> ####

<span data-ttu-id="d5623-160">Kromě výše uvedených Pauli a Clifford operací Q# poskytuje předehru řadu způsobů, jak vyjádřit rotace.</span><span class="sxs-lookup"><span data-stu-id="d5623-160">In addition to the Pauli and Clifford operations above, the Q# prelude provides a variety of ways of expressing rotations.</span></span>
<span data-ttu-id="d5623-161">Jak je popsáno v [qubit operacích](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), možnost otáčení je zásadní pro algoritmy.</span><span class="sxs-lookup"><span data-stu-id="d5623-161">As described in [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), the ability to rotate is critical to quantum algorithms.</span></span>

<span data-ttu-id="d5623-162">Začneme vrácením se změnami, kterou můžeme vyjádřit pomocí $H $ a $T $, kde $H $ je operace Hadamard a kde \begin{Equation} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ % fixme: to v současné době používá napadení ze čtyř back-qubit.</span><span class="sxs-lookup"><span data-stu-id="d5623-162">We start by recalling that we can express any single-qubit operation using the $H$ and $T$ gates, where $H$ is the Hadamard operation, and where \begin{equation} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quad back whack hack.</span></span>
<span data-ttu-id="d5623-163">0 & e ^ {i \pi/4} \end{bmatrix} \end{Equation} Toto je druhá odmocnina <xref:microsoft.quantum.intrinsic.s> operace, například $T ^ 2 = S $.</span><span class="sxs-lookup"><span data-stu-id="d5623-163">0 & e^{i \pi / 4} \end{bmatrix} \end{equation} This is the square root of the <xref:microsoft.quantum.intrinsic.s> operation, such that $T^2 = S$.</span></span>
<span data-ttu-id="d5623-164">Brána $T $ je zase implementovaná <xref:microsoft.quantum.intrinsic.t> operací a má signaturu `(Qubit => Unit is Adj + Ctl)` , která značí, že se jedná o jednotnou operaci na jednom qubit.</span><span class="sxs-lookup"><span data-stu-id="d5623-164">The $T$ gate is in turn implemented by the <xref:microsoft.quantum.intrinsic.t> operation, and has signature `(Qubit => Unit is Adj + Ctl)`, indicating that it is a unitary operation on a single-qubit.</span></span>

<span data-ttu-id="d5623-165">I když je to v zásadě dostačující pro popsání jakékoli jakékoli operace s jedním qubit, mohou mít různé cílové počítače efektivnější reprezentace o Paulich operátorech, takže předehru obsahuje nejrůznější způsoby, jak convienently vyjádřit v takových rotacích.</span><span class="sxs-lookup"><span data-stu-id="d5623-165">Even though this is in principle sufficient to describe any arbitrary single-qubit operation, different target machines may have more efficient representations for rotations about Pauli operators, such that the prelude includes a variety of ways to convienently express such rotations.</span></span>
<span data-ttu-id="d5623-166">Nejběžnější je <xref:microsoft.quantum.intrinsic.r> operace, která implementuje otočení kolem zadané osy Pauli, \Begin{Equation} R (\sigma, \phi) \mathrel{: =} \exp (-i \phi \sigma/2), \end{Equation} kde $ \sigma $ je operátor Pauli, $ \phi $ je úhel a kde $ \exp $ představuje exponenciální hodnotu matice.</span><span class="sxs-lookup"><span data-stu-id="d5623-166">The most basic of these is the <xref:microsoft.quantum.intrinsic.r> operation, which implements a rotation around a specified Pauli axis, \begin{equation} R(\sigma, \phi) \mathrel{:=} \exp(-i \phi \sigma / 2), \end{equation} where $\sigma$ is a Pauli operator, $\phi$ is an angle, and where $\exp$ represents the matrix exponential.</span></span>
<span data-ttu-id="d5623-167">Má signaturu `((Pauli, Double, Qubit) => Unit is Adj + Ctl)` , kde první dvě části vstupu reprezentují klasické argumenty $ \sigma $ a $ \phi $ potřebné k určení jednotkového operátoru $R (\sigma, \phi) $.</span><span class="sxs-lookup"><span data-stu-id="d5623-167">It has signature `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`, where the first two parts of the input represent the classical arguments $\sigma$ and $\phi$ needed to specify the unitary operator $R(\sigma, \phi)$.</span></span>
<span data-ttu-id="d5623-168">Částečně se dá použít $ \sigma $ a $ \phi $, aby se získala operace, jejíž typ je jedna qubit jednotně.</span><span class="sxs-lookup"><span data-stu-id="d5623-168">We can partially apply $\sigma$ and $\phi$ to obtain an operation whose type is that of a single-qubit unitary.</span></span>
<span data-ttu-id="d5623-169">Například `R(PauliZ, PI() / 4, _)` je typu `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-169">For example, `R(PauliZ, PI() / 4, _)` has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

> [!NOTE]
> <span data-ttu-id="d5623-170"><xref:microsoft.quantum.intrinsic.r>Operace rozdělí vstupní úhel o 2 a násobí ho hodnotou-1.</span><span class="sxs-lookup"><span data-stu-id="d5623-170">The <xref:microsoft.quantum.intrinsic.r> operation divides the input angle by 2 and multiplies it by -1.</span></span>
> <span data-ttu-id="d5623-171">Pro $Z $ rotace to znamená, že $ \ket {0} $ eigenstate je otočeno pomocí $-\phi/$2 a $ \ket {1} $ eigenstate je otočeno $ \phi/$2, takže $ \ket {1} $ eigenstate je otočen $ \phi $ vzhledem k $ \ket {0} $ eigenstate.</span><span class="sxs-lookup"><span data-stu-id="d5623-171">For $Z$ rotations, this means that the $\ket{0}$ eigenstate is rotated by $-\phi / 2$ and the $\ket{1}$ eigenstate is rotated by $\phi / 2$, so that the $\ket{1}$ eigenstate is rotated by $\phi$ relative to the $\ket{0}$ eigenstate.</span></span>
>
> <span data-ttu-id="d5623-172">Konkrétně to znamená, že `T` a `R(PauliZ, PI() / 8, _)` liší se pouze nepodstatnými [globálními fázemi](xref:microsoft.quantum.glossary#global-phase).</span><span class="sxs-lookup"><span data-stu-id="d5623-172">In particular, this means that `T` and `R(PauliZ, PI() / 8, _)` differ only by an irrelevant [global phase](xref:microsoft.quantum.glossary#global-phase).</span></span>
> <span data-ttu-id="d5623-173">Z tohoto důvodu se $T $ někdy označuje jako brána $ \frac{\pi} {8} $.</span><span class="sxs-lookup"><span data-stu-id="d5623-173">For this reason, $T$ is sometimes known as the $\frac{\pi}{8}$-gate.</span></span>
>
> <span data-ttu-id="d5623-174">Všimněte si také, že `PauliI` v jednoduchém otočení se aplikuje globální fáze $ \phi/$2.</span><span class="sxs-lookup"><span data-stu-id="d5623-174">Note also that rotating around `PauliI` simply applies a global phase of $\phi / 2$.</span></span> <span data-ttu-id="d5623-175">I když tyto fáze nejsou důležité, jak je uvedeno v [koncepčních dokumentech](xref:microsoft.quantum.concepts.qubit), jsou relevantní pro řízená `PauliI` otočení.</span><span class="sxs-lookup"><span data-stu-id="d5623-175">While such phases are irrelevant, as argued in [the conceptual documents](xref:microsoft.quantum.concepts.qubit), they are relevant for controlled `PauliI` rotations.</span></span>

<span data-ttu-id="d5623-176">V rámci algoritmů doby použitelnosti je často užitečné vyjádřit rotace jako dyadic zlomky, jako je $ \phi = \pi k/2 ^ n $ pro některá $k \in \mathbb{Z} $ a $n \in \mathbb{N} $.</span><span class="sxs-lookup"><span data-stu-id="d5623-176">Within quantum algorithms, it is often useful to express rotations as dyadic fractions, such that $\phi = \pi k / 2^n$ for some $k \in \mathbb{Z}$ and $n \in \mathbb{N}$.</span></span>
<span data-ttu-id="d5623-177"><xref:microsoft.quantum.intrinsic.rfrac>Operace implementuje otočení kolem zadané osy Pauli pomocí této konvence.</span><span class="sxs-lookup"><span data-stu-id="d5623-177">The <xref:microsoft.quantum.intrinsic.rfrac> operation implements a rotation around a specified Pauli axis using this convention.</span></span>
<span data-ttu-id="d5623-178">Liší se od <xref:microsoft.quantum.intrinsic.r> v tom, že úhel otočení je zadán jako dva vstupy typu `Int` , interpretovány jako dyadic zlomek.</span><span class="sxs-lookup"><span data-stu-id="d5623-178">It differs from <xref:microsoft.quantum.intrinsic.r> in that the rotation angle is specified as two inputs of type `Int`, interpreted as a dyadic fraction.</span></span>
<span data-ttu-id="d5623-179">Proto `RFrac` má signaturu `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-179">Thus, `RFrac` has signature `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="d5623-180">Implementuje jedinou qubit jednotk $ \exp (i \pi k \sigma/2 ^ n) $, kde $ \sigma $ je Pauli matice odpovídající prvnímu argumentu, $k $ je druhý argument a $n $ je třetí argument.</span><span class="sxs-lookup"><span data-stu-id="d5623-180">It implements the single-qubit unitary $\exp(i \pi k \sigma / 2^n)$, where $\sigma$ is the Pauli matrix corresponding to the first argument, $k$ is the second argument, and $n$ is the third argument.</span></span>
<span data-ttu-id="d5623-181">`RFrac(_,k,n,_)` je stejná jako `R(_,-πk/2^n,_)` ; Všimněte si, že úhel je *záporný* pro zlomek.</span><span class="sxs-lookup"><span data-stu-id="d5623-181">`RFrac(_,k,n,_)` is the same as `R(_,-πk/2^n,_)`; note that the angle is the *negative* of the fraction.</span></span>

<span data-ttu-id="d5623-182"><xref:microsoft.quantum.intrinsic.rx>Operace implementuje otočení kolem osy Pauli $X $.</span><span class="sxs-lookup"><span data-stu-id="d5623-182">The <xref:microsoft.quantum.intrinsic.rx> operation implements a rotation around the Pauli $X$ axis.</span></span>
<span data-ttu-id="d5623-183">Má signaturu `((Double, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-183">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="d5623-184">`Rx(_, _)` je stejná jako `R(PauliX, _, _)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-184">`Rx(_, _)` is the same as `R(PauliX, _, _)`.</span></span>

<span data-ttu-id="d5623-185"><xref:microsoft.quantum.intrinsic.ry>Operace implementuje otočení kolem osy Pauli $Y $.</span><span class="sxs-lookup"><span data-stu-id="d5623-185">The <xref:microsoft.quantum.intrinsic.ry> operation implements a rotation around the Pauli $Y$ axis.</span></span>
<span data-ttu-id="d5623-186">Má signaturu `((Double, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-186">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="d5623-187">`Ry(_, _)` je stejná jako `R(PauliY,_ , _)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-187">`Ry(_, _)` is the same as `R(PauliY,_ , _)`.</span></span>

<span data-ttu-id="d5623-188"><xref:microsoft.quantum.intrinsic.rz>Operace implementuje otočení kolem osy Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="d5623-188">The <xref:microsoft.quantum.intrinsic.rz> operation implements a rotation around the Pauli $Z$ axis.</span></span>
<span data-ttu-id="d5623-189">Má signaturu `((Double, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-189">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="d5623-190">`Rz(_, _)` je stejná jako `R(PauliZ, _, _)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-190">`Rz(_, _)` is the same as `R(PauliZ, _, _)`.</span></span>

<span data-ttu-id="d5623-191"><xref:microsoft.quantum.intrinsic.r1>Operace implementuje rotaci o danou velikost kolem $ \ket {1} $, $-$1 eigenstate z $Z $.</span><span class="sxs-lookup"><span data-stu-id="d5623-191">The <xref:microsoft.quantum.intrinsic.r1> operation implements a rotation by the given amount around $\ket{1}$, the $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="d5623-192">Má signaturu `((Double, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-192">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="d5623-193">`R1(phi,_)` je stejný jako `R(PauliZ,phi,_)` následováno `R(PauliI,-phi,_)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-193">`R1(phi,_)` is the same as `R(PauliZ,phi,_)` followed by `R(PauliI,-phi,_)`.</span></span>

<span data-ttu-id="d5623-194"><xref:microsoft.quantum.intrinsic.r1frac>Operace implementuje zlomkové otočení o zadanou hodnotu kolem hodnoty z = 1 eigenstate.</span><span class="sxs-lookup"><span data-stu-id="d5623-194">The <xref:microsoft.quantum.intrinsic.r1frac> operation implements a fractional rotation by the given amount around the Z=1 eigenstate.</span></span>
<span data-ttu-id="d5623-195">Má signaturu `((Int,Int, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-195">It has signature `((Int,Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="d5623-196">`R1Frac(k,n,_)` je stejný jako `RFrac(PauliZ,-k.n+1,_)` následováno `RFrac(PauliI,k,n+1,_)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-196">`R1Frac(k,n,_)` is the same as `RFrac(PauliZ,-k.n+1,_)` followed by `RFrac(PauliI,k,n+1,_)`.</span></span>

<span data-ttu-id="d5623-197">Příklad operace otočení (kolem osy Pauli $Z $, v této instanci) mapované na Bloch koule, je uveden níže:</span><span class="sxs-lookup"><span data-stu-id="d5623-197">An example of a rotation operation (around the Pauli $Z$ axis, in this instance) mapped onto the Bloch sphere is shown below:</span></span>

![Operace otočení mapovaná na sféru Bloch](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a><span data-ttu-id="d5623-199">Operace s více qubit</span><span class="sxs-lookup"><span data-stu-id="d5623-199">Multi-Qubit Operations</span></span> ####

<span data-ttu-id="d5623-200">Kromě qubit operací uvedených výše definuje předehru také několik operací s více qubit.</span><span class="sxs-lookup"><span data-stu-id="d5623-200">In addition to the single-qubit operations above, the prelude also defines several multi-qubit operations.</span></span>

<span data-ttu-id="d5623-201">Nejprve <xref:microsoft.quantum.intrinsic.cnot> operace provede standardní řízenou `NOT` bránu, \begin{Equation} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & \\ \\ 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="d5623-201">First, the <xref:microsoft.quantum.intrinsic.cnot> operation performs a standard controlled-`NOT` gate, \begin{equation} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}.</span></span>
<span data-ttu-id="d5623-202">\end{Equation} má signaturu `((Qubit, Qubit) => Unit is Adj + Ctl)` , která představuje $ \operatorname{CNOT} $ chová unitarily na dvou individuálních qubits.</span><span class="sxs-lookup"><span data-stu-id="d5623-202">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`, representing that $\operatorname{CNOT}$ acts unitarily on two individual qubits.</span></span>
<span data-ttu-id="d5623-203">`CNOT(q1, q2)` je stejná jako `(Controlled X)([q1], q2)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-203">`CNOT(q1, q2)` is the same as `(Controlled X)([q1], q2)`.</span></span>
<span data-ttu-id="d5623-204">Vzhledem k `Controlled` tomu, že funktor umožňuje řízení v registru, používáme literál pole `[q1]` k označení toho, že chceme mít pouze jeden ovládací prvek.</span><span class="sxs-lookup"><span data-stu-id="d5623-204">Since the `Controlled` functor allows for controlling on a register, we use the array literal `[q1]` to indicate that we want only the one control.</span></span>

<span data-ttu-id="d5623-205">Tato <xref:microsoft.quantum.intrinsic.ccnot> operace provádí nebránu s neřízenými dvěma procesory, někdy také známou jako Toffoli brána.</span><span class="sxs-lookup"><span data-stu-id="d5623-205">The <xref:microsoft.quantum.intrinsic.ccnot> operation performs doubly-controlled NOT gate, sometimes also known as the Toffoli gate.</span></span>
<span data-ttu-id="d5623-206">Má signaturu `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-206">It has signature `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="d5623-207">`CCNOT(q1, q2, q3)` je stejná jako `(Controlled X)([q1, q2], q3)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-207">`CCNOT(q1, q2, q3)` is the same as `(Controlled X)([q1, q2], q3)`.</span></span>

<span data-ttu-id="d5623-208"><xref:microsoft.quantum.intrinsic.swap>Operace prohodí stavy se dvěma qubitsy.</span><span class="sxs-lookup"><span data-stu-id="d5623-208">The <xref:microsoft.quantum.intrinsic.swap> operation swaps the quantum states of two qubits.</span></span>
<span data-ttu-id="d5623-209">To znamená, že implementuje jednotnou matrici \begin{Equation} \operatorname{SWAP} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="d5623-209">That is, it implements the unitary matrix \begin{equation} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}.</span></span>
<span data-ttu-id="d5623-210">\end{Equation} má signaturu `((Qubit, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-210">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="d5623-211">`SWAP(q1,q2)` je ekvivalentem pro `CNOT(q1, q2)` následovaný `CNOT(q2, q1)` a pak `CNOT(q1, q2)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-211">`SWAP(q1,q2)` is equivalent to `CNOT(q1, q2)` followed by `CNOT(q2, q1)` and then `CNOT(q1, q2)`.</span></span>

> [!NOTE]
> <span data-ttu-id="d5623-212">Brána *swap není stejná* jako změna uspořádání prvků proměnné s typem `Qubit[]` .</span><span class="sxs-lookup"><span data-stu-id="d5623-212">The SWAP gate is *not* the same as rearranging the elements of a variable with type `Qubit[]`.</span></span>
> <span data-ttu-id="d5623-213">Použití `SWAP(q1, q2)` způsobí změnu stavu qubits, na který odkazuje `q1` a `q2` , zatímco `let swappedRegister = [q2, q1];` pouze to ovlivňuje způsob, jakým odkazujeme na tyto qubits.</span><span class="sxs-lookup"><span data-stu-id="d5623-213">Applying `SWAP(q1, q2)` causes a change to the state of the qubits referred to by `q1` and `q2`, while `let swappedRegister = [q2, q1];` only affects how we refer to those qubits.</span></span>
> <span data-ttu-id="d5623-214">Kromě toho `(Controlled SWAP)([q0], (q1, q2))` umožňuje, `SWAP` aby bylo možné nastavit stav třetího qubit, který nemůžeme reprezentovat prvky.</span><span class="sxs-lookup"><span data-stu-id="d5623-214">Moreover, `(Controlled SWAP)([q0], (q1, q2))` allows for `SWAP` to be conditioned on the state of a third qubit, which we cannot represent by rearranging elements.</span></span>
> <span data-ttu-id="d5623-215">Brána kontrolovaného zahození, označovaná také jako brána Fredkin, je dostatečně výkonná pro zahrnutí všech klasických výpočtů.</span><span class="sxs-lookup"><span data-stu-id="d5623-215">The controlled-SWAP gate, also known as the Fredkin gate, is powerful enough to include all classical computation.</span></span>

<span data-ttu-id="d5623-216">Nakonec předehru poskytuje dvě operace pro reprezentaci exponenciálních hodnot operátorů Pauli s více qubit.</span><span class="sxs-lookup"><span data-stu-id="d5623-216">Finally, the prelude provides two operations for representing exponentials of multi-qubit Pauli operators.</span></span>
<span data-ttu-id="d5623-217"><xref:microsoft.quantum.intrinsic.exp>Operace provádí rotaci na základě tensor produktu Paulich matric, jak je reprezentované qubit jednotkou \begin{Equation} (\vec{\sigma}, \phi) \mathrel{: =} \exp\left (i \phi \ sigma_0 \otimes \ sigma_1 \otimes \cdots \otimes \ sigma_n \right), \end{Equation} kde $ \vec{\sigma} = (\ sigma_0, \ sigma_1, \dots, \ sigma_n) $ je sekvence operátorů s jedním qubitm Pauli a kde $ \phi $ je úhel.</span><span class="sxs-lookup"><span data-stu-id="d5623-217">The <xref:microsoft.quantum.intrinsic.exp> operation performs a rotation based on a tensor product of Pauli matrices, as represented by the multi-qubit unitary \begin{equation} \operatorname{Exp}(\vec{\sigma}, \phi) \mathrel{:=} \exp\left(i \phi \sigma_0 \otimes \sigma_1 \otimes \cdots \otimes \sigma_n \right), \end{equation} where $\vec{\sigma} = (\sigma_0, \sigma_1, \dots, \sigma_n)$ is a sequence of single-qubit Pauli operators, and where $\phi$ is an angle.</span></span>
<span data-ttu-id="d5623-218">`Exp`Rotace představuje $ \vec{\sigma} $ jako pole `Pauli` prvků, takže má signaturu `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-218">The `Exp` rotation represents $\vec{\sigma}$ as an array of `Pauli` elements, such that it has signature `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="d5623-219"><xref:microsoft.quantum.intrinsic.expfrac>Operace provede stejnou rotaci pomocí dyadic zlomkového zápisu popsaného výše.</span><span class="sxs-lookup"><span data-stu-id="d5623-219">The <xref:microsoft.quantum.intrinsic.expfrac> operation performs the same rotation, using the dyadic fraction notation discussed above.</span></span>
<span data-ttu-id="d5623-220">Má signaturu `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-220">It has signature `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

> [!WARNING]
> <span data-ttu-id="d5623-221">Exponenciální podíly tensor produktu operátorů Pauli nejsou stejné jako tensor produkty exponenciálních operátorů Pauli.</span><span class="sxs-lookup"><span data-stu-id="d5623-221">Exponentials of the tensor product of Pauli operators are not the same as tensor products of the exponentials of Pauli operators.</span></span>
> <span data-ttu-id="d5623-222">To znamená, $e ^ {i (Z \otimes Z) \phi} \Ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $.</span><span class="sxs-lookup"><span data-stu-id="d5623-222">That is, $e^{i (Z \otimes Z) \phi} \ne e^{i Z \phi} \otimes e^{i Z \phi}$.</span></span>

### <a name="measurements"></a><span data-ttu-id="d5623-223">Měření</span><span class="sxs-lookup"><span data-stu-id="d5623-223">Measurements</span></span> ###

<span data-ttu-id="d5623-224">Při měření odpovídá eigenvalue + 1 operátoru, který je změřen jako `Zero` výsledek, a-1 eigenvalue na `One` výsledek.</span><span class="sxs-lookup"><span data-stu-id="d5623-224">When measuring, the +1 eigenvalue of the operator being measured corresponds to a `Zero` result, and the -1 eigenvalue to a `One` result.</span></span>

> [!NOTE]
> <span data-ttu-id="d5623-225">I když se tato konvence může zdát lichá, má dvě skvělé výhody.</span><span class="sxs-lookup"><span data-stu-id="d5623-225">While this convention might seem odd, it has two very nice advantages.</span></span>
> <span data-ttu-id="d5623-226">Nejprve se bude jednat o výsledek $ \ket {0} $, který je reprezentován `Result` hodnotou `Zero` , zatímco pozorování $ \ket {1} $ odpovídá `One` .</span><span class="sxs-lookup"><span data-stu-id="d5623-226">First, observing the outcome $\ket{0}$ is represented by the `Result` value `Zero`, while observing $\ket{1}$ corresponds to `One`.</span></span>
> <span data-ttu-id="d5623-227">Za druhé můžeme napsat, že eigenvalue $ \lambda $ odpovídající výsledku $r $ je $ \lambda = (-1) ^ r $.</span><span class="sxs-lookup"><span data-stu-id="d5623-227">Second, we can write out that the eigenvalue $\lambda$ corresponding to a result $r$ is $\lambda = (-1)^r$.</span></span>

<span data-ttu-id="d5623-228">Měření operací nepodporuje ani `Adjoint` `Controlled` funktor.</span><span class="sxs-lookup"><span data-stu-id="d5623-228">Measurement operations support neither the `Adjoint` nor the `Controlled` functor.</span></span>

<span data-ttu-id="d5623-229">Tato <xref:microsoft.quantum.intrinsic.measure> operace provede společné měření jednoho nebo více qubits v zadaném produktu Pauli Operators.</span><span class="sxs-lookup"><span data-stu-id="d5623-229">The <xref:microsoft.quantum.intrinsic.measure> operation performs a joint measurement of one or more qubits in the specified product of Pauli operators.</span></span>
<span data-ttu-id="d5623-230">Pokud se pole Pauli a qubit liší od různých délek, operace se nezdařila.</span><span class="sxs-lookup"><span data-stu-id="d5623-230">If the Pauli array and qubit array are different lengths, then the operation fails.</span></span>
<span data-ttu-id="d5623-231">`Measure` má signaturu `((Pauli[], Qubit[]) => Result)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-231">`Measure` has signature `((Pauli[], Qubit[]) => Result)`.</span></span>

<span data-ttu-id="d5623-232">Počítejte s tím, že společná měření není shodná s měřením jednotlivých qubit jednotlivě.</span><span class="sxs-lookup"><span data-stu-id="d5623-232">Note that a joint measurement is not the same as measuring each qubit individually.</span></span>
<span data-ttu-id="d5623-233">Zvažte například stav $ \ket {11} = \ket {1} \otimes \Ket {1} = X\otimes X \ket {00} $.</span><span class="sxs-lookup"><span data-stu-id="d5623-233">For example, consider the state $\ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$.</span></span>
<span data-ttu-id="d5623-234">Měření $Z _0 $ a $Z _1 každou jednotlivě získáme výsledky $r _0 = $1 a $r _1 = $1.</span><span class="sxs-lookup"><span data-stu-id="d5623-234">Measuring $Z_0$ and $Z_1$ each individually, we get the results $r_0 = 1$ and $r_1 = 1$.</span></span>
<span data-ttu-id="d5623-235">Měření $Z _0 Z_1 $ ale získáme jediný výsledek $r _ {\textrm{Joint}} = $0, který představuje, že je dvojice $ \ket {11} $ kladná.</span><span class="sxs-lookup"><span data-stu-id="d5623-235">Measuring $Z_0 Z_1$, however, we get the single result $r_{\textrm{joint}} = 0$, representing that the pairity of $\ket{11}$ is positive.</span></span>
<span data-ttu-id="d5623-236">Vložit jinak, $ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{Joint}}) $.</span><span class="sxs-lookup"><span data-stu-id="d5623-236">Put differently, $(-1)^{r_0 + r_1} = (-1)^r_{\textrm{joint}})$.</span></span>
<span data-ttu-id="d5623-237">Vzhledem k tomu, že se vám od tohoto měření učí *jenom* parita, jsou zachovány všechny informace o počtu procesorů, které jsou reprezentované na pozici mezi 2 2 – qubit stavy pozitivní parity, $ \ket {00} $ a $ \ket {11} $.</span><span class="sxs-lookup"><span data-stu-id="d5623-237">Critically, since we *only* learn the parity from this measurement, any quantum information represented in the superposition between the two two-qubit states of positive parity, $\ket{00}$ and $\ket{11}$, is preserved.</span></span>
<span data-ttu-id="d5623-238">Tato vlastnost bude v podstatě pozdější, protože se zabývá opravami chyb.</span><span class="sxs-lookup"><span data-stu-id="d5623-238">This property will be essential later, as we discuss error correction.</span></span>

<span data-ttu-id="d5623-239">Pro usnadnění práce předehru poskytuje také dvě další operace pro měření qubits.</span><span class="sxs-lookup"><span data-stu-id="d5623-239">For convenience, the prelude also provides two other operations for measuring qubits.</span></span>
<span data-ttu-id="d5623-240">Vzhledem k tomu, že provádění qubit měření je poměrně běžné, definuje předehru pro tento případ Zkrácený Zkrácený tvar.</span><span class="sxs-lookup"><span data-stu-id="d5623-240">First, since performing single-qubit measurements is quite common, the prelude defines a shorthand for this case.</span></span>
<span data-ttu-id="d5623-241">Tato <xref:microsoft.quantum.intrinsic.m> operace měří operátor Pauli $Z $ v jednom qubit a má signaturu `(Qubit => Result)` .</span><span class="sxs-lookup"><span data-stu-id="d5623-241">The <xref:microsoft.quantum.intrinsic.m> operation measures the Pauli $Z$ operator on a single qubit, and has signature `(Qubit => Result)`.</span></span>
<span data-ttu-id="d5623-242">`M(q)` je ekvivalentem k `Measure([PauliZ], [q])` .</span><span class="sxs-lookup"><span data-stu-id="d5623-242">`M(q)` is equivalent to `Measure([PauliZ], [q])`.</span></span>

<span data-ttu-id="d5623-243"><xref:microsoft.quantum.measurement.multim>Měří operátor Pauli $Z $ *samostatně* pro každé pole qubits a vrací *pole* `Result` hodnot získaných pro každé qubit.</span><span class="sxs-lookup"><span data-stu-id="d5623-243">The <xref:microsoft.quantum.measurement.multim> measures the Pauli $Z$ operator *separately* on each of an array of qubits, returning the *array* of `Result` values obtained for each qubit.</span></span>
<span data-ttu-id="d5623-244">V některých případech je to možné optimalizovat.</span><span class="sxs-lookup"><span data-stu-id="d5623-244">In some cases this can be optimized.</span></span> <span data-ttu-id="d5623-245">Má signaturu ( `Qubit[] => Result[])` .</span><span class="sxs-lookup"><span data-stu-id="d5623-245">It has signature (`Qubit[] => Result[])`.</span></span>
<span data-ttu-id="d5623-246">`MultiM(qs)` je ekvivalentem:</span><span class="sxs-lookup"><span data-stu-id="d5623-246">`MultiM(qs)` is equivalent to:</span></span>

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a><span data-ttu-id="d5623-247">Funkce rozšíření a operace</span><span class="sxs-lookup"><span data-stu-id="d5623-247">Extension Functions and Operations</span></span> ##

<span data-ttu-id="d5623-248">Kromě toho předehru definuje bohatou sadu matematických a typových funkcí pro převod na úrovni .NET pro použití v rámci Q# kódu.</span><span class="sxs-lookup"><span data-stu-id="d5623-248">In addition, the prelude defines a rich set of mathematical and type conversion functions at the .NET level for use within Q# code.</span></span>
<span data-ttu-id="d5623-249">Například <xref:microsoft.quantum.math> obor názvů definuje užitečné operace, jako například <xref:microsoft.quantum.math.sin> a <xref:microsoft.quantum.math.log> .</span><span class="sxs-lookup"><span data-stu-id="d5623-249">For instance, the <xref:microsoft.quantum.math> namespace defines useful operations such as <xref:microsoft.quantum.math.sin> and <xref:microsoft.quantum.math.log>.</span></span>
<span data-ttu-id="d5623-250">Implementace poskytovaná vývojovou sadou pro plnění z více systémů používá knihovnu klasických tříd .NET Base, a proto může zahrnovat další komunikaci s výměnou mezi programy a jejich klasickými ovladači.</span><span class="sxs-lookup"><span data-stu-id="d5623-250">The implementation provided by the Quantum Development Kit uses the classical .NET base class library, and thus may involve an additional communications round trip between quantum programs and their classical drivers.</span></span>
<span data-ttu-id="d5623-251">I když to nepředstavuje problém pro místní simulátor, může to být problém s výkonem při použití vzdáleného simulátoru nebo skutečného hardwaru jako cílového počítače.</span><span class="sxs-lookup"><span data-stu-id="d5623-251">While this does not present a problem for a local simulator, this can be a performance issue when using a remote simulator or actual hardware as a target machine.</span></span>
<span data-ttu-id="d5623-252">V takovém případě může jednotlivý cílový počítač zmírnit tento dopad na výkon tím, že tyto operace přepíše verze, které jsou pro konkrétní systém efektivnější.</span><span class="sxs-lookup"><span data-stu-id="d5623-252">That said, an individual target machine may mitigate this performance impact by overriding these operations with versions that are more efficient for that particular system.</span></span>

### <a name="math"></a><span data-ttu-id="d5623-253">Matematické</span><span class="sxs-lookup"><span data-stu-id="d5623-253">Math</span></span> ###

<span data-ttu-id="d5623-254"><xref:microsoft.quantum.math>Obor názvů poskytuje mnoho užitečných funkcí z [ `System.Math` třídy](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1&preserve-view=true)knihovny základní třídy .NET.</span><span class="sxs-lookup"><span data-stu-id="d5623-254">The <xref:microsoft.quantum.math> namespace provides many useful functions from the .NET base class library's [`System.Math` class](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1&preserve-view=true).</span></span>
<span data-ttu-id="d5623-255">Tyto funkce lze použít stejným způsobem jako všechny další Q# funkce:</span><span class="sxs-lookup"><span data-stu-id="d5623-255">These functions can be used in the same manner as any other Q# functions:</span></span>

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

<span data-ttu-id="d5623-256">V případě přetížení statické metody .NET na základě typu argumentů Q# je odpovídající funkce opatřena příponou, která označuje typ jejího vstupu:</span><span class="sxs-lookup"><span data-stu-id="d5623-256">Where a .NET static method has been overloaded based on the type of its arguments, the corresponding Q# function is annotated with a suffix indicating the type of its input:</span></span>

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a><span data-ttu-id="d5623-257">Bitové operace</span><span class="sxs-lookup"><span data-stu-id="d5623-257">Bitwise Operations</span></span> ###

<span data-ttu-id="d5623-258">Nakonec <xref:microsoft.quantum.bitwise> obor názvů poskytuje několik užitečných funkcí pro manipulaci s celými čísly prostřednictvím bitových operátorů.</span><span class="sxs-lookup"><span data-stu-id="d5623-258">Finally, the <xref:microsoft.quantum.bitwise> namespace provides several useful functions for manipulating integers through bitwise operators.</span></span>
<span data-ttu-id="d5623-259">Například <xref:microsoft.quantum.bitwise.parity> vrátí bitovou paritu celého čísla jako jiné celé číslo.</span><span class="sxs-lookup"><span data-stu-id="d5623-259">For instance, <xref:microsoft.quantum.bitwise.parity> returns the bitwise parity of an integer as another integer.</span></span>
