---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: AmplitudeAmplificationFromPartialReflections – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: e4030aabcab55db35bcb8199e37bee837ead6ad0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845894"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="5647c-102">AmplitudeAmplificationFromPartialReflections – funkce</span><span class="sxs-lookup"><span data-stu-id="5647c-102">AmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="5647c-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="5647c-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="5647c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5647c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5647c-105">Amplituda amplitud na základě částečných odrazů</span><span class="sxs-lookup"><span data-stu-id="5647c-105">Amplitude amplification by partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="5647c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5647c-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="5647c-107">fáze: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="5647c-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="5647c-108">Fáze částečných odrazů</span><span class="sxs-lookup"><span data-stu-id="5647c-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="5647c-109">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="5647c-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="5647c-110">Operátor reflexe o počátečním stavu</span><span class="sxs-lookup"><span data-stu-id="5647c-110">Reflection operator about start state</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="5647c-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="5647c-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="5647c-112">Operátor reflexe pro cílový stav</span><span class="sxs-lookup"><span data-stu-id="5647c-112">Reflection operator about target state</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="5647c-113">Výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="5647c-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="5647c-114">Operace, která implementuje zesílení amplitud pomocí částečných odrazů.</span><span class="sxs-lookup"><span data-stu-id="5647c-114">An operation that implements amplitude amplification by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="5647c-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5647c-115">Remarks</span></span>

<span data-ttu-id="5647c-116">Zesílení amplitud je zvláštní případ oblivious zesílení amplitud, kde nejsou žádné systémové qubits a oblivious Oracle je nastavená na identity.</span><span class="sxs-lookup"><span data-stu-id="5647c-116">Amplitude amplification is a special case of oblivious amplitude amplification where there are no system qubits and the oblivious oracle is set to identity.</span></span>
<span data-ttu-id="5647c-117">Ve většině případů `startQubits` je inicializován ve stavu $ \ket{\text{start}} \_ $1, což je eigenstate $-$1 pro `startStateReflection` .</span><span class="sxs-lookup"><span data-stu-id="5647c-117">In most cases, `startQubits` is initialized in the state $\ket{\text{start}}\_1$, which is the $-1$ eigenstate of `startStateReflection`.</span></span>