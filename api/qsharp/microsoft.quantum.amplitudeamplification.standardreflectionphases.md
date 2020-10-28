---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: c189b34b641989ab458986fb3f2872759b949be5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707678"
---
# <a name="standardreflectionphases-function"></a><span data-ttu-id="23b9a-102">StandardReflectionPhases – funkce</span><span class="sxs-lookup"><span data-stu-id="23b9a-102">StandardReflectionPhases function</span></span>

<span data-ttu-id="23b9a-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="23b9a-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="23b9a-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="23b9a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="23b9a-105">Vypočítá částečné odrazové fáze pro zesílení standardního amplitudy.</span><span class="sxs-lookup"><span data-stu-id="23b9a-105">Computes partial reflection phases for standard amplitude amplification.</span></span>

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="23b9a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="23b9a-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="23b9a-107">nIterations: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="23b9a-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="23b9a-108">Počet iterací zesílení amplitudy, pro které se mají generovat částečné fáze reflexe pro.</span><span class="sxs-lookup"><span data-stu-id="23b9a-108">Number of amplitude amplification iterations to generate partial reflection phases for.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="23b9a-109">Výstup: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="23b9a-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="23b9a-110">Operace, která implementuje fáze určené jako částečné odrazy</span><span class="sxs-lookup"><span data-stu-id="23b9a-110">An operation that implements phases specified as partial reflections</span></span>

## <a name="remarks"></a><span data-ttu-id="23b9a-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="23b9a-111">Remarks</span></span>

<span data-ttu-id="23b9a-112">Všechny fáze jsou $ \pi $ s výjimkou prvního odrazu k počátečnímu stavu a posledního reflexe týkající se cílového stavu, což jsou $0 $.</span><span class="sxs-lookup"><span data-stu-id="23b9a-112">All phases are $\pi$, except for the first reflection about the start state and the last reflection about the target state, which are $0$.</span></span>