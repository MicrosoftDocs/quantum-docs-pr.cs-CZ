---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: PurifiedMixedStateWithData – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: c89ee8f5df58e5d6b154b67d2b39db208bc8a215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229949"
---
# <a name="purifiedmixedstatewithdata-function"></a><span data-ttu-id="8a72a-102">PurifiedMixedStateWithData – funkce</span><span class="sxs-lookup"><span data-stu-id="8a72a-102">PurifiedMixedStateWithData function</span></span>

<span data-ttu-id="8a72a-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="8a72a-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="8a72a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8a72a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8a72a-105">Vrátí operaci, která připraví čištění daného kombinovaného stavu, entangled s registrem reprezentujícím danou kolekci dat.</span><span class="sxs-lookup"><span data-stu-id="8a72a-105">Returns an operation that prepares a a purification of a given mixed state, entangled with a register representing a given collection of data.</span></span>
<span data-ttu-id="8a72a-106">"Vyčištěný smíšený stav s daty" odkazuje na stav formuláře σi √ PI | i ⟩ | XI ⟩ | uvolňování ⟩, kde každé XI je BITSTRING kódování dalších dat přidružených k registru | i ⟩.</span><span class="sxs-lookup"><span data-stu-id="8a72a-106">A "purified mixed state with data" refers to a state of the form Σᵢ √𝑝ᵢ |𝑖⟩ |𝑥ᵢ⟩ |garbageᵢ⟩, where each 𝑥ᵢ is a bitstring encoding additional data associated with the register |𝑖⟩.</span></span>

<span data-ttu-id="8a72a-107"> https://arxiv.org/pdf/1805.03662.pdf?page=15Další diskuzi najdete v tématu.</span><span class="sxs-lookup"><span data-stu-id="8a72a-107">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="8a72a-108">Popis</span><span class="sxs-lookup"><span data-stu-id="8a72a-108">Description</span></span>

<span data-ttu-id="8a72a-109">Pomocí techniky paměti pro paměťovou jednotku vystupuje danou matici hustoty a vrátí tuto reprezentaci jako operaci přípravy stavu.</span><span class="sxs-lookup"><span data-stu-id="8a72a-109">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="8a72a-110">Konkrétně je uveden seznam $N $ koeficientů $ \ alpha_j $ a BITSTRING $ \vec{x}_j $ přidružených k jednotlivým koeficientům. Tato funkce vrátí operaci, která pomocí techniky paměti pro procesory dopraví aproximaci $ $ \begin{align} \tilde\rho = \sum_{j = 0} ^ {N-1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x} _J} \bra{\vec{x}_j} \end{align} $ $ smíšeného stavu $ $ \begin{align} \rho = \sum_{j = 0} ^ {N-1} \ FRAC {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x} _j}, \end{align} $ $, kde každá $p _j $ je aproximací daného součinitele $ \ alpha_j $, například $ $ \begin{align} \left | p_j – \frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \le \frac{\epsilon}{N} \end{align} $ $ for each $j $.</span><span class="sxs-lookup"><span data-stu-id="8a72a-110">In particular, given a list of $N$ coefficients $\alpha_j$, and a bitstring $\vec{x}_j$ associated with each coefficient, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="8a72a-111">Při předání registru indexu a registru pro uvolňování paměti qubits, zpočátku ve stavu $ \ket {0} \ket{00\cdots 0}, vrácená operace připraví Registry do čištění $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j} \ket{\vec{x} _J} \ket{\text{garbage} _J}, \end{align} $ $, což resetuje a ruší registraci uvolnění paměti, vypíše požadovanou přípravu do cílové chyby $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="8a72a-111">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j} \ket{\vec{x}_j} \ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="8a72a-112">Vstup</span><span class="sxs-lookup"><span data-stu-id="8a72a-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="8a72a-113">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8a72a-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8a72a-114">Cílová chyba $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="8a72a-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--doublebool"></a><span data-ttu-id="8a72a-115">koeficienty: ([Double](xref:microsoft.quantum.lang-ref.double),[bool](xref:microsoft.quantum.lang-ref.bool)[]) []</span><span class="sxs-lookup"><span data-stu-id="8a72a-115">coefficients : ([Double](xref:microsoft.quantum.lang-ref.double),[Bool](xref:microsoft.quantum.lang-ref.bool)[])[]</span></span>

<span data-ttu-id="8a72a-116">Pole $N $ koeficienty určující pravděpodobnost základních stavů společně s BITSTRING $ \vec{x} _j $ asociované s každým koeficientem.</span><span class="sxs-lookup"><span data-stu-id="8a72a-116">Array of $N$ coefficients specifying the probability of basis states, along with the bitstring $\vec{x}_j$ associated with each coefficient.</span></span>
<span data-ttu-id="8a72a-117">Záporná čísla $-\ alpha_j $ se budou považovat za pozitivní $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="8a72a-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="8a72a-118">Výstup: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="8a72a-118">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="8a72a-119">Operace, která připraví $ \tilde \rho $ jako čištění do společného indexu a registru pro uvolňování paměti.</span><span class="sxs-lookup"><span data-stu-id="8a72a-119">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="remarks"></a><span data-ttu-id="8a72a-120">Poznámky</span><span class="sxs-lookup"><span data-stu-id="8a72a-120">Remarks</span></span>

<span data-ttu-id="8a72a-121">Koeficienty poskytované této operaci jsou normalizovány po 1 normě, což znamená, že koeficienty jsou vždy považovány za Popis platné distribuce pravděpodobnosti kategorií.</span><span class="sxs-lookup"><span data-stu-id="8a72a-121">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="8a72a-122">Reference</span><span class="sxs-lookup"><span data-stu-id="8a72a-122">References</span></span>

- <span data-ttu-id="8a72a-123">Kódování elektronického spektra v Okruhech v případě využití lineární T, Babbush, Craig Gidney, Dominic W. bobulovin, Nathan Wiebe, Jarrod McClean, Alexandru bledější, Austin Fowlera, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="8a72a-123">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="8a72a-124">Viz také</span><span class="sxs-lookup"><span data-stu-id="8a72a-124">See Also</span></span>

- [<span data-ttu-id="8a72a-125">Microsoft. Přípravno. Preparation. PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="8a72a-125">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)