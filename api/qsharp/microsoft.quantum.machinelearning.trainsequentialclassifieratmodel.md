---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel
title: Operace TrainSequentialClassifierAtModel
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifierAtModel
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.
ms.openlocfilehash: 4164c190cb19b6d3ea74d9803a77d2b19607279b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857158"
---
# <a name="trainsequentialclassifieratmodel-operation"></a>Operace TrainSequentialClassifierAtModel

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Vzhledem k struktuře sekvenčního klasifikátoru vlaky klasifikuje v dané sadě školení s označením, počínaje z konkrétního modelu.

```qsharp
operation TrainSequentialClassifierAtModel (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a>Vstup

### <a name="model--sequentialmodel"></a>Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Sekvenční model, který se má použít jako výchozí bod pro školení.


### <a name="samples--labeledsample"></a>Ukázky: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

Sada přidaných školicích dat, která se budou používat k provádění školení.


### <a name="options--trainingoptions"></a>možnosti: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

Konfigurace, která se má použít při školení; Další podrobnosti najdete v tématu @"microsoft.quantum.machinelearning.trainingoptions" a @"microsoft.quantum.machinelearning.defaulttrainingoptions" .


### <a name="trainingschedule--samplingschedule"></a>trainingSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Plán vzorkování, který se má použít při výběru ukázek z školicích dat během postupu školení.


### <a name="validationschedule--samplingschedule"></a>validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Plán vzorkování, který se má použít při výběru ukázek z školicích dat při výběru počátečního bodu, který vedlo k nejlepšímu skóre třídění.



## <a name="output--sequentialmodelint"></a>Výstup: ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[int](xref:microsoft.quantum.lang-ref.int))

- Parametrizace daného klasifikátoru a bias mezi dvěma třídami, společně odpovídající nejlepšímu výsledku z každého z daných počátečních bodů.
- Počet neúspěšných přístupů zjištěných v nejlepším modelu třídění.

## <a name="see-also"></a>Viz také

- [Microsoft. MachineLearning. TrainSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifier)
- [Microsoft. MachineLearning. ValidateSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)