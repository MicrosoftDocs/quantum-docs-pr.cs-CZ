---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Ukázková funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 5dd599246847718f4f0411715585cb416595db9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854946"
---
# <a name="sampled-function"></a><span data-ttu-id="8a15f-102">Ukázková funkce</span><span class="sxs-lookup"><span data-stu-id="8a15f-102">Sampled function</span></span>

<span data-ttu-id="8a15f-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="8a15f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="8a15f-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="8a15f-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="8a15f-105">Vzorkuje dané pole pomocí zadaného plánu.</span><span class="sxs-lookup"><span data-stu-id="8a15f-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="8a15f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="8a15f-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="8a15f-107">plán: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="8a15f-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="8a15f-108">Plán, který se má použít v hodnotách vzorkování.</span><span class="sxs-lookup"><span data-stu-id="8a15f-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="8a15f-109">hodnoty: t []</span><span class="sxs-lookup"><span data-stu-id="8a15f-109">values : 'T[]</span></span>

<span data-ttu-id="8a15f-110">Pole hodnot, které se mají vzorkovat</span><span class="sxs-lookup"><span data-stu-id="8a15f-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="8a15f-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="8a15f-111">Output : 'T[]</span></span>

<span data-ttu-id="8a15f-112">Pole prvků z hodnot podle zadaného plánu.</span><span class="sxs-lookup"><span data-stu-id="8a15f-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8a15f-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8a15f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8a15f-114">'S</span><span class="sxs-lookup"><span data-stu-id="8a15f-114">'T</span></span>

