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
# <a name="schedulelength-function"></a>ScheduleLength – funkce

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Vrátí počet prvků v daném plánu vzorkování.

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a>Vstup

### <a name="schedule--samplingschedule"></a>plán: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Plán vzorkování, jehož délka má být vrácena.



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Počet prvků v daném plánu vzorkování.