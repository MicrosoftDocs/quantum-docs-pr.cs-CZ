---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: ObliviousAmplitudeAmplificationFromStatePreparation – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 873c436d4b8d8efc9dc61c2baba9b0e0f7f09fc2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845809"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="fc209-102">ObliviousAmplitudeAmplificationFromStatePreparation – funkce</span><span class="sxs-lookup"><span data-stu-id="fc209-102">ObliviousAmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="fc209-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="fc209-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="fc209-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fc209-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fc209-105">Oblivious zesílení amplitudy od Oracle po částečné odrazy.</span><span class="sxs-lookup"><span data-stu-id="fc209-105">Oblivious amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="fc209-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="fc209-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="fc209-107">fáze: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="fc209-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="fc209-108">Fáze částečných odrazů</span><span class="sxs-lookup"><span data-stu-id="fc209-108">Phases of partial reflections</span></span>


### <a name="startstateoracle--deterministicstateoracle"></a><span data-ttu-id="fc209-109">startStateOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="fc209-109">startStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="fc209-110">Jednotková databáze Oracle $A $, která připraví pomocný stav spuštění</span><span class="sxs-lookup"><span data-stu-id="fc209-110">Unitary oracle $A$ that prepares auxiliary start state</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="fc209-111">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="fc209-111">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="fc209-112">Jednotkový typ Oracle $O $ `ObliviousOracle` , který pracuje společně s pomocným a systémovým registrem</span><span class="sxs-lookup"><span data-stu-id="fc209-112">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system register</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="fc209-113">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fc209-113">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fc209-114">Index do registru příznaků s jedním qubit</span><span class="sxs-lookup"><span data-stu-id="fc209-114">Index to single-qubit flag register</span></span>



## <a name="output--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="fc209-115">Výstup: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[];[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="fc209-115">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="fc209-116">Operace, která implementuje zesílení oblivious amplitud na základě částečných odrazů.</span><span class="sxs-lookup"><span data-stu-id="fc209-116">An operation that implements oblivious amplitude amplification based on partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="fc209-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="fc209-117">Remarks</span></span>

<span data-ttu-id="fc209-118">To ukládá přísnější podmínky pro formu pomocných stavů Start a target než v `AmpAmpObliviousByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="fc209-118">This imposes stricter conditions on form of the auxiliary start and target states than in `AmpAmpObliviousByReflectionPhases`.</span></span>
<span data-ttu-id="fc209-119">Předpokládá se, že $A \ket {0} \_ f\ket {0} \_ A = \ket{\Text{Start}} \_ {FA} $ připraví pomocný počáteční stav $ \ket{\Text{Start}} \_ {FA} $ z výpočetního základu $ \ket {0} \_ f\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="fc209-119">It is assumed that $A\ket{0}\_f\ket{0}\_a= \ket{\text{start}}\_{fa}$ prepares the auxiliary start state $\ket{\text{start}}\_{fa}$ from the computational basis $\ket{0}\_f\ket{0}$.</span></span>
<span data-ttu-id="fc209-120">Předpokládá se, že cílový stav je označený jako $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="fc209-120">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="fc209-121">Předpokládá se, že \begin{align} O\ket {\ text {Start}} \_ {FA} \ket{\psi} \_ s = \lambda\ket {1} \_ f\ket {\ text {cokoli}} \_ a\ket {\ text {Target}} \_ s u \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} pro některé jednotkové $U $.</span><span class="sxs-lookup"><span data-stu-id="fc209-121">It is assumed that \begin{align} O\ket{\text{start}}\_{fa}\ket{\psi}\_s= \lambda\ket{1}\_f\ket{\text{anything}}\_a\ket{\text{target}}\_s U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} for some unitary $U$.</span></span>