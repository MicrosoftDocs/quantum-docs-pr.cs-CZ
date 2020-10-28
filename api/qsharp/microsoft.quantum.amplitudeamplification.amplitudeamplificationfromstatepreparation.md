---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificationFromStatePreparation – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 7725ff327e327578ff36242a2b1bc6d03fab0d0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707768"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="5e476-102">AmplitudeAmplificationFromStatePreparation – funkce</span><span class="sxs-lookup"><span data-stu-id="5e476-102">AmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="5e476-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="5e476-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="5e476-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5e476-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5e476-105">Amplituda zesílení pro částečné odrazy od Oracle</span><span class="sxs-lookup"><span data-stu-id="5e476-105">Amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="5e476-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5e476-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="5e476-107">fáze: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="5e476-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="5e476-108">Fáze částečných odrazů</span><span class="sxs-lookup"><span data-stu-id="5e476-108">Phases of partial reflections</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="5e476-109">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="5e476-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="5e476-110">Jednotková databáze Oracle $A $, která připraví stav spuštění</span><span class="sxs-lookup"><span data-stu-id="5e476-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="5e476-111">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5e476-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5e476-112">Index pro označení qubit</span><span class="sxs-lookup"><span data-stu-id="5e476-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="5e476-113">Výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="5e476-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="5e476-114">Operace, která implementuje zesílení amplitudy od Oracle, které jsou implementované částečnými odrazy.</span><span class="sxs-lookup"><span data-stu-id="5e476-114">An operation that implements amplitude amplification by oracles that are implemented by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="5e476-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5e476-115">Remarks</span></span>

<span data-ttu-id="5e476-116">To představuje přísnější podmínky ve formě počátečních a cílových stavů než v `AmpAmpByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="5e476-116">This imposes stricter conditions on form of the start and target states than in `AmpAmpByReflectionPhases`.</span></span>
<span data-ttu-id="5e476-117">Předpokládá se, že cílový stav je označený jako $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="5e476-117">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="5e476-118">Předpokládá se, že \begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} ve většině případů `flagQubit` a `auxiliaryRegister` jsou inicializovány ve stavu $ \ket {0} \_ {f} \ket {0} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="5e476-118">It is assumed that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} In most cases, `flagQubit` and `auxiliaryRegister` are initialized in the state $\ket{0}\_{f}\ket{0}\_s$.</span></span>