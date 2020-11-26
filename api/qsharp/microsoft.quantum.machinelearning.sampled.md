---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Ukázková funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: ddff72bbed6f20e8e0ceb3bfe3fc50a3da0bd2a9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211623"
---
# <a name="sampled-function"></a><span data-ttu-id="d68ea-102">Ukázková funkce</span><span class="sxs-lookup"><span data-stu-id="d68ea-102">Sampled function</span></span>

<span data-ttu-id="d68ea-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d68ea-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="d68ea-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d68ea-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="d68ea-105">Vzorkuje dané pole pomocí zadaného plánu.</span><span class="sxs-lookup"><span data-stu-id="d68ea-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="d68ea-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="d68ea-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="d68ea-107">plán: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="d68ea-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="d68ea-108">Plán, který se má použít v hodnotách vzorkování.</span><span class="sxs-lookup"><span data-stu-id="d68ea-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="d68ea-109">hodnoty: t []</span><span class="sxs-lookup"><span data-stu-id="d68ea-109">values : 'T[]</span></span>

<span data-ttu-id="d68ea-110">Pole hodnot, které se mají vzorkovat</span><span class="sxs-lookup"><span data-stu-id="d68ea-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="d68ea-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="d68ea-111">Output : 'T[]</span></span>

<span data-ttu-id="d68ea-112">Pole prvků z hodnot podle zadaného plánu.</span><span class="sxs-lookup"><span data-stu-id="d68ea-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d68ea-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d68ea-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d68ea-114">'S</span><span class="sxs-lookup"><span data-stu-id="d68ea-114">'T</span></span>

