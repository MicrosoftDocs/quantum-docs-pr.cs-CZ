---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 594a1d9fa674e457ab88072ade4198283b677af6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854305"
---
# <a name="purifiedmixedstate-function"></a><span data-ttu-id="f8ca1-102">PurifiedMixedState – funkce</span><span class="sxs-lookup"><span data-stu-id="f8ca1-102">PurifiedMixedState function</span></span>

<span data-ttu-id="f8ca1-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="f8ca1-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="f8ca1-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f8ca1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f8ca1-105">Vrátí operaci, která připraví čištění daného smíšeného stavu.</span><span class="sxs-lookup"><span data-stu-id="f8ca1-105">Returns an operation that prepares a a purification of a given mixed state.</span></span>
<span data-ttu-id="f8ca1-106">"Vyčištěný smíšený stav" odkazuje na stavy formuláře | ψ ⟩ = σi √ PI | i ⟩ | uvolňování ⟩ určené vektorem koeficientů {PI}.</span><span class="sxs-lookup"><span data-stu-id="f8ca1-106">A "purified mixed state" refers to states of the form |ψ⟩ = Σᵢ √𝑝ᵢ |𝑖⟩ |garbageᵢ⟩ specified by a vector of coefficients {𝑝ᵢ}.</span></span> <span data-ttu-id="f8ca1-107">Stavy tohoto formuláře se dají snížit na smíšené stavy ρ ≔ PI | i ⟩ ⟨ i | trasováním v registru "uvolnění paměti" (to znamená smíšený stav, který je šikmý v výpočetních intervalech).</span><span class="sxs-lookup"><span data-stu-id="f8ca1-107">States of this form can be reduced to mixed states ρ ≔ 𝑝ᵢ |𝑖⟩⟨𝑖| by tracing over the "garbage" register (that is, a mixed state that is diagonal in the computational basis).</span></span>

<span data-ttu-id="f8ca1-108"> https://arxiv.org/pdf/1805.03662.pdf?page=15Další diskuzi najdete v tématu.</span><span class="sxs-lookup"><span data-stu-id="f8ca1-108">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="f8ca1-109">Popis</span><span class="sxs-lookup"><span data-stu-id="f8ca1-109">Description</span></span>

<span data-ttu-id="f8ca1-110">Pomocí techniky paměti pro paměťovou jednotku vystupuje danou matici hustoty a vrátí tuto reprezentaci jako operaci přípravy stavu.</span><span class="sxs-lookup"><span data-stu-id="f8ca1-110">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="f8ca1-111">Konkrétně v případě, že seznam $N $-efektivnosti $ \ alpha_j $, tato funkce vrátí operaci, která pomocí techniky paměti pro práci s procesory připraví aproximaci $ $ \begin{align} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ pro smíšený stav $ $ \begin{align} \rho = \ sum_ {j = 0} ^ {N-1} \ FRAC {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j}, \end{align} $ $, kde každá $p _j $ je sblížená s daným koeficientem $ \ alpha_j $, například $ $ \begin{align} \left | p_j – \frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \le \frac{\epsilon}{N} \end{align} $ $ for each $j $.</span><span class="sxs-lookup"><span data-stu-id="f8ca1-111">In particular, given a list of $N$ coefficients $\alpha_j$, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="f8ca1-112">Při předání registru indexu a registru qubits paměti ve stavu $ \ket {0} \ket{00\cdots 0} tato vrácená operace připraví oba Registry do čištění $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _J}, \end{align} $ $ tak, aby resetování a zrušení přidělení uvolňování paměti vypravilo požadovanou přípravu v rámci cílové chyby $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="f8ca1-112">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="f8ca1-113">Vstup</span><span class="sxs-lookup"><span data-stu-id="f8ca1-113">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="f8ca1-114">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f8ca1-114">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f8ca1-115">Cílová chyba $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="f8ca1-115">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="f8ca1-116">koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f8ca1-116">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="f8ca1-117">Pole $N $ koeficientů určujících pravděpodobnost základních stavů.</span><span class="sxs-lookup"><span data-stu-id="f8ca1-117">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="f8ca1-118">Záporná čísla $-\ alpha_j $ se budou považovat za pozitivní $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="f8ca1-118">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="f8ca1-119">Výstup: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="f8ca1-119">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="f8ca1-120">Operace, která připraví $ \tilde \rho $ jako čištění do společného indexu a registru pro uvolňování paměti.</span><span class="sxs-lookup"><span data-stu-id="f8ca1-120">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="example"></a><span data-ttu-id="f8ca1-121">Příklad</span><span class="sxs-lookup"><span data-stu-id="f8ca1-121">Example</span></span>

<span data-ttu-id="f8ca1-122">Následující fragment kódu připraví čištění pro $3 $-qubit State $ \rho = \ sum_ {j = 0} ^ {4} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $, kde $ \vec\alpha = (1.0, 2,0, 3,0, 4,0, 5,0) $ a cílová chyba je $10 ^ {-3} $:</span><span class="sxs-lookup"><span data-stu-id="f8ca1-122">The following code snippet prepares an purification of the $3$-qubit state $\rho=\sum_{j=0}^{4}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$, where $\vec\alpha=(1.0, 2.0, 3.0, 4.0, 5.0)$, and the target error is $10^{-3}$:</span></span>

```qsharp
let coefficients = [1.0, 2.0, 3.0, 4.0, 5.0];
let targetError = 1e-3;
let purifiedState = PurifiedMixedState(targetError, coefficients);
using (indexRegister = Qubit[purifiedState::Requirements::NIndexQubits]) {
    using (garbageRegister = Qubit[purifiedState::Requirements::NGarbageQubits]) {
        purifiedState::Prepare(LittleEndian(indexRegister), new Qubit[0], garbageRegister);
    }
}
```

## <a name="remarks"></a><span data-ttu-id="f8ca1-123">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f8ca1-123">Remarks</span></span>

<span data-ttu-id="f8ca1-124">Koeficienty poskytované této operaci jsou normalizovány po 1 normě, což znamená, že koeficienty jsou vždy považovány za Popis platné distribuce pravděpodobnosti kategorií.</span><span class="sxs-lookup"><span data-stu-id="f8ca1-124">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="f8ca1-125">Reference</span><span class="sxs-lookup"><span data-stu-id="f8ca1-125">References</span></span>

- <span data-ttu-id="f8ca1-126">Kódování elektronického spektra v Okruhech v případě využití lineární T, Babbush, Craig Gidney, Dominic W. bobulovin, Nathan Wiebe, Jarrod McClean, Alexandru bledější, Austin Fowlera, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="f8ca1-126">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="f8ca1-127">Viz také</span><span class="sxs-lookup"><span data-stu-id="f8ca1-127">See Also</span></span>

- [<span data-ttu-id="f8ca1-128">Microsoft. Přípravno. Preparation. PurifiedMixedStateWithData</span><span class="sxs-lookup"><span data-stu-id="f8ca1-128">Microsoft.Quantum.Preparation.PurifiedMixedStateWithData</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)