---
uid: Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier
title: Operace ValidateSequentialClassifier
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidateSequentialClassifier
qsharp.summary: Validates a given sequential classifier against a given set of pre-labeled samples.
ms.openlocfilehash: 5174085edbfd846e8f6649f33e325fd1979ae6a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196102"
---
# <a name="validatesequentialclassifier-operation"></a>Operace ValidateSequentialClassifier

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Ověří daný sekvenční klasifikátor proti dané sadě ukázek s předdefinovaným názvem.

```qsharp
operation ValidateSequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], tolerance : Double, nMeasurements : Int, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Microsoft.Quantum.MachineLearning.ValidationResults
```


## <a name="input"></a>Vstup

### <a name="model--sequentialmodel"></a>Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Sekvenční model, který má být ověřen.


### <a name="samples--labeledsample"></a>Ukázky: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

Ukázky, které se mají použít k ověření daného modelu.


### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

Tolerance aproximace, která se má použít při kódování jednotlivých vzorků jako vstup sekvenčního třídění.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Počet měření, která se mají použít při klasifikaci jednotlivých vzorků.


### <a name="validationschedule--samplingschedule"></a>validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Plán, podle kterého by měly být z sady ověření vykresleny vzorky.



## <a name="output--validationresults"></a>Výstup: [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)

Výsledky daného ověření.