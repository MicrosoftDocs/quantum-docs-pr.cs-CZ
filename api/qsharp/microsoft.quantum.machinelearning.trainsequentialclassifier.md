---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifier
title: Operace TrainSequentialClassifier
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifier
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set.
ms.openlocfilehash: 97865965bef831eeb53245ba0c23d6bce54643ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847706"
---
# <a name="trainsequentialclassifier-operation"></a>Operace TrainSequentialClassifier

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Vzhledem k struktuře sekvenčního klasifikátoru vlaky zajišťují třídění na dané sadě školení s označením.

```qsharp
operation TrainSequentialClassifier (models : Microsoft.Quantum.MachineLearning.SequentialModel[], samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a>Vstup

### <a name="models--sequentialmodel"></a>modely: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]

Pole modelů, které se mají použít jako počáteční body během školení.


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

- [Microsoft. MachineLearning. TrainSequentialClassifierAtModel](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel)
- [Microsoft. MachineLearning. ValidateSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)