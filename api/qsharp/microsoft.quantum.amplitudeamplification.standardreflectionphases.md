---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: 316c8f22a16859ebb439824eda9a5aa02c750b5d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191121"
---
# <a name="standardreflectionphases-function"></a><span data-ttu-id="e93c9-102">StandardReflectionPhases – funkce</span><span class="sxs-lookup"><span data-stu-id="e93c9-102">StandardReflectionPhases function</span></span>

<span data-ttu-id="e93c9-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="e93c9-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="e93c9-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e93c9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e93c9-105">Vypočítá částečné odrazové fáze pro zesílení standardního amplitudy.</span><span class="sxs-lookup"><span data-stu-id="e93c9-105">Computes partial reflection phases for standard amplitude amplification.</span></span>

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="e93c9-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e93c9-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="e93c9-107">nIterations: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e93c9-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e93c9-108">Počet iterací zesílení amplitudy, pro které se mají generovat částečné fáze reflexe pro.</span><span class="sxs-lookup"><span data-stu-id="e93c9-108">Number of amplitude amplification iterations to generate partial reflection phases for.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="e93c9-109">Výstup: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="e93c9-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="e93c9-110">Operace, která implementuje fáze určené jako částečné odrazy</span><span class="sxs-lookup"><span data-stu-id="e93c9-110">An operation that implements phases specified as partial reflections</span></span>

## <a name="remarks"></a><span data-ttu-id="e93c9-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e93c9-111">Remarks</span></span>

<span data-ttu-id="e93c9-112">Všechny fáze jsou $ \pi $ s výjimkou prvního odrazu k počátečnímu stavu a posledního reflexe týkající se cílového stavu, což jsou $0 $.</span><span class="sxs-lookup"><span data-stu-id="e93c9-112">All phases are $\pi$, except for the first reflection about the start state and the last reflection about the target state, which are $0$.</span></span>