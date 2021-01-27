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

