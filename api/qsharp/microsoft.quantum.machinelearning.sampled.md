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
# <a name="sampled-function"></a>Ukázková funkce

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Vzorkuje dané pole pomocí zadaného plánu.

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a>Vstup

### <a name="schedule--samplingschedule"></a>plán: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Plán, který se má použít v hodnotách vzorkování.


### <a name="values--t"></a>hodnoty: t []

Pole hodnot, které se mají vzorkovat



## <a name="output--t"></a>Výstup: t []

Pole prvků z hodnot podle zadaného plánu.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

