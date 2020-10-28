---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: ObliviousAmplitudeAmplificationFromStatePreparation – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 9975d26af8f9beb2b91e409ad78159d6f04936e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707720"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="5910c-102">ObliviousAmplitudeAmplificationFromStatePreparation – funkce</span><span class="sxs-lookup"><span data-stu-id="5910c-102">ObliviousAmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="5910c-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="5910c-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="5910c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5910c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5910c-105">Oblivious zesílení amplitudy od Oracle po částečné odrazy.</span><span class="sxs-lookup"><span data-stu-id="5910c-105">Oblivious amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="5910c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5910c-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="5910c-107">fáze: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="5910c-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="5910c-108">Fáze částečných odrazů</span><span class="sxs-lookup"><span data-stu-id="5910c-108">Phases of partial reflections</span></span>


### <a name="startstateoracle--deterministicstateoracle"></a><span data-ttu-id="5910c-109">startStateOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="5910c-109">startStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="5910c-110">Jednotková databáze Oracle $A $, která připraví pomocný stav spuštění</span><span class="sxs-lookup"><span data-stu-id="5910c-110">Unitary oracle $A$ that prepares auxiliary start state</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="5910c-111">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="5910c-111">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="5910c-112">Jednotkový typ Oracle $O $ `ObliviousOracle` , který pracuje společně s pomocným a systémovým registrem</span><span class="sxs-lookup"><span data-stu-id="5910c-112">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system register</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="5910c-113">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5910c-113">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5910c-114">Index do registru příznaků s jedním qubit</span><span class="sxs-lookup"><span data-stu-id="5910c-114">Index to single-qubit flag register</span></span>



## <a name="output--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="5910c-115">Výstup: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[];[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="5910c-115">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="5910c-116">Operace, která implementuje zesílení oblivious amplitud na základě částečných odrazů.</span><span class="sxs-lookup"><span data-stu-id="5910c-116">An operation that implements oblivious amplitude amplification based on partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="5910c-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5910c-117">Remarks</span></span>

<span data-ttu-id="5910c-118">To ukládá přísnější podmínky pro formu pomocných stavů Start a target než v `AmpAmpObliviousByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="5910c-118">This imposes stricter conditions on form of the auxiliary start and target states than in `AmpAmpObliviousByReflectionPhases`.</span></span>
<span data-ttu-id="5910c-119">Předpokládá se, že $A \ket {0} \_ f\ket {0} \_ A = \ket{\Text{Start}} \_ {FA} $ připraví pomocný počáteční stav $ \ket{\Text{Start}} \_ {FA} $ z výpočetního základu $ \ket {0} \_ f\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="5910c-119">It is assumed that $A\ket{0}\_f\ket{0}\_a= \ket{\text{start}}\_{fa}$ prepares the auxiliary start state $\ket{\text{start}}\_{fa}$ from the computational basis $\ket{0}\_f\ket{0}$.</span></span>
<span data-ttu-id="5910c-120">Předpokládá se, že cílový stav je označený jako $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="5910c-120">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="5910c-121">Předpokládá se, že \begin{align} O\ket {\ text {Start}} \_ {FA} \ket{\psi} \_ s = \lambda\ket {1} \_ f\ket {\ text {cokoli}} \_ a\ket {\ text {Target}} \_ s u \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} pro některé jednotkové $U $.</span><span class="sxs-lookup"><span data-stu-id="5910c-121">It is assumed that \begin{align} O\ket{\text{start}}\_{fa}\ket{\psi}\_s= \lambda\ket{1}\_f\ket{\text{anything}}\_a\ket{\text{target}}\_s U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} for some unitary $U$.</span></span>