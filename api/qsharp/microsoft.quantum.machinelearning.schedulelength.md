---
uid: Microsoft.Quantum.MachineLearning.ScheduleLength
title: ScheduleLength – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ScheduleLength
qsharp.summary: Returns the number of elements in a given sampling schedule.
ms.openlocfilehash: 008bdcdc0a7c0ad2775dea65ebba46556092beed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211589"
---
# <a name="schedulelength-function"></a><span data-ttu-id="5ae0d-102">ScheduleLength – funkce</span><span class="sxs-lookup"><span data-stu-id="5ae0d-102">ScheduleLength function</span></span>

<span data-ttu-id="5ae0d-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="5ae0d-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="5ae0d-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="5ae0d-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="5ae0d-105">Vrátí počet prvků v daném plánu vzorkování.</span><span class="sxs-lookup"><span data-stu-id="5ae0d-105">Returns the number of elements in a given sampling schedule.</span></span>

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a><span data-ttu-id="5ae0d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5ae0d-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="5ae0d-107">plán: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="5ae0d-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="5ae0d-108">Plán vzorkování, jehož délka má být vrácena.</span><span class="sxs-lookup"><span data-stu-id="5ae0d-108">A sampling schedule whose length is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="5ae0d-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5ae0d-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5ae0d-110">Počet prvků v daném plánu vzorkování.</span><span class="sxs-lookup"><span data-stu-id="5ae0d-110">The number of elements in the given sampling schedule.</span></span>