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