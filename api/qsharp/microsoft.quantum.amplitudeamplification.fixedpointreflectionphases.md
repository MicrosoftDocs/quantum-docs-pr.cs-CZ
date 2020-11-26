---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 8cc1073447f5fae87ece38db64dcc312f6208899
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191444"
---
# <a name="fixedpointreflectionphases-function"></a><span data-ttu-id="ee70f-102">FixedPointReflectionPhases – funkce</span><span class="sxs-lookup"><span data-stu-id="ee70f-102">FixedPointReflectionPhases function</span></span>

<span data-ttu-id="ee70f-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="ee70f-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="ee70f-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ee70f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ee70f-105">Vypočítá částečné odrazové fáze pro zesílení amplitudy s pevnou desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="ee70f-105">Computes partial reflection phases for fixed-point amplitude amplification.</span></span>

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="ee70f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ee70f-106">Input</span></span>

### <a name="nqueries--int"></a><span data-ttu-id="ee70f-107">nQueries: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ee70f-107">nQueries : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ee70f-108">Počet dotazů na přípravu stavu Oracle.</span><span class="sxs-lookup"><span data-stu-id="ee70f-108">Number of queries to the state preparation oracle.</span></span> <span data-ttu-id="ee70f-109">Musí být liché celé číslo.</span><span class="sxs-lookup"><span data-stu-id="ee70f-109">Must be an odd integer.</span></span>


### <a name="successmin--double"></a><span data-ttu-id="ee70f-110">successMin: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ee70f-110">successMin : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ee70f-111">Cíl minimální pravděpodobnosti úspěšnosti.</span><span class="sxs-lookup"><span data-stu-id="ee70f-111">Target minimum success probability.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="ee70f-112">Výstup: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="ee70f-112">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="ee70f-113">Pole fází, které lze použít při implementaci algoritmu amplitudy amplitudy s pevnou desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="ee70f-113">Array of phases that can be used in fixed-point amplitude amplification quantum algorithm implementation.</span></span>

## <a name="references"></a><span data-ttu-id="ee70f-114">Reference</span><span class="sxs-lookup"><span data-stu-id="ee70f-114">References</span></span>

<span data-ttu-id="ee70f-115">Použijeme fáze v zesílení amplitudy s pevnou desetinnou čárkou s optimálním počtem dotazů.</span><span class="sxs-lookup"><span data-stu-id="ee70f-115">We use the phases in "Fixed-Point Amplitude Amplification with an Optimal Number of Queries"</span></span>

- <span data-ttu-id="ee70f-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Viz také "metodologie kompozitních" bran pro plnění "</span><span class="sxs-lookup"><span data-stu-id="ee70f-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) See also "Methodology of composite quantum gates"</span></span>
- <span data-ttu-id="ee70f-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) pro fáze ve `RotationPhases` formátu.</span><span class="sxs-lookup"><span data-stu-id="ee70f-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) for phases in the `RotationPhases` format.</span></span>