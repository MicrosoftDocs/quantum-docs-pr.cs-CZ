---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificationFromStatePreparation – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: e64ad5ad4e975483f20f92c0b070dd6788ef296b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847441"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="2b30d-102">AmplitudeAmplificationFromStatePreparation – funkce</span><span class="sxs-lookup"><span data-stu-id="2b30d-102">AmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="2b30d-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="2b30d-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="2b30d-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2b30d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2b30d-105">Amplituda zesílení pro částečné odrazy od Oracle</span><span class="sxs-lookup"><span data-stu-id="2b30d-105">Amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="2b30d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2b30d-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="2b30d-107">fáze: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="2b30d-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="2b30d-108">Fáze částečných odrazů</span><span class="sxs-lookup"><span data-stu-id="2b30d-108">Phases of partial reflections</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="2b30d-109">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="2b30d-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="2b30d-110">Jednotková databáze Oracle $A $, která připraví stav spuštění</span><span class="sxs-lookup"><span data-stu-id="2b30d-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="2b30d-111">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2b30d-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2b30d-112">Index pro označení qubit</span><span class="sxs-lookup"><span data-stu-id="2b30d-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="2b30d-113">Výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="2b30d-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2b30d-114">Operace, která implementuje zesílení amplitudy od Oracle, které jsou implementované částečnými odrazy.</span><span class="sxs-lookup"><span data-stu-id="2b30d-114">An operation that implements amplitude amplification by oracles that are implemented by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b30d-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2b30d-115">Remarks</span></span>

<span data-ttu-id="2b30d-116">To představuje přísnější podmínky ve formě počátečních a cílových stavů než v `AmpAmpByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="2b30d-116">This imposes stricter conditions on form of the start and target states than in `AmpAmpByReflectionPhases`.</span></span>
<span data-ttu-id="2b30d-117">Předpokládá se, že cílový stav je označený jako $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="2b30d-117">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="2b30d-118">Předpokládá se, že \begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} ve většině případů `flagQubit` a `auxiliaryRegister` jsou inicializovány ve stavu $ \ket {0} \_ {f} \ket {0} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="2b30d-118">It is assumed that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} In most cases, `flagQubit` and `auxiliaryRegister` are initialized in the state $\ket{0}\_{f}\ket{0}\_s$.</span></span>