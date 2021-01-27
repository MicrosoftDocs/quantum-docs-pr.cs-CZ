---
uid: Microsoft.Quantum.MachineLearning.ScheduleLength
title: ScheduleLength – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ScheduleLength
qsharp.summary: Returns the number of elements in a given sampling schedule.
ms.openlocfilehash: dd042b1282d2f5386ee0b67bf57ad4027eefd493
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854913"
---
# <a name="schedulelength-function"></a><span data-ttu-id="1f4db-102">ScheduleLength – funkce</span><span class="sxs-lookup"><span data-stu-id="1f4db-102">ScheduleLength function</span></span>

<span data-ttu-id="1f4db-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1f4db-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="1f4db-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1f4db-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="1f4db-105">Vrátí počet prvků v daném plánu vzorkování.</span><span class="sxs-lookup"><span data-stu-id="1f4db-105">Returns the number of elements in a given sampling schedule.</span></span>

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a><span data-ttu-id="1f4db-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="1f4db-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="1f4db-107">plán: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="1f4db-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="1f4db-108">Plán vzorkování, jehož délka má být vrácena.</span><span class="sxs-lookup"><span data-stu-id="1f4db-108">A sampling schedule whose length is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="1f4db-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1f4db-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1f4db-110">Počet prvků v daném plánu vzorkování.</span><span class="sxs-lookup"><span data-stu-id="1f4db-110">The number of elements in the given sampling schedule.</span></span>