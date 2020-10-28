---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Ukázková funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 9f9f91bc50861c5b31a76e28050189d13efda71e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707977"
---
# <a name="sampled-function"></a><span data-ttu-id="47bcc-102">Ukázková funkce</span><span class="sxs-lookup"><span data-stu-id="47bcc-102">Sampled function</span></span>

<span data-ttu-id="47bcc-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="47bcc-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="47bcc-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="47bcc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="47bcc-105">Vzorkuje dané pole pomocí zadaného plánu.</span><span class="sxs-lookup"><span data-stu-id="47bcc-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="47bcc-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="47bcc-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="47bcc-107">plán: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="47bcc-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="47bcc-108">Plán, který se má použít v hodnotách vzorkování.</span><span class="sxs-lookup"><span data-stu-id="47bcc-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="47bcc-109">hodnoty: t []</span><span class="sxs-lookup"><span data-stu-id="47bcc-109">values : 'T[]</span></span>

<span data-ttu-id="47bcc-110">Pole hodnot, které se mají vzorkovat</span><span class="sxs-lookup"><span data-stu-id="47bcc-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="47bcc-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="47bcc-111">Output : 'T[]</span></span>

<span data-ttu-id="47bcc-112">Pole prvků z hodnot podle zadaného plánu.</span><span class="sxs-lookup"><span data-stu-id="47bcc-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="47bcc-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="47bcc-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="47bcc-114">'S</span><span class="sxs-lookup"><span data-stu-id="47bcc-114">'T</span></span>

