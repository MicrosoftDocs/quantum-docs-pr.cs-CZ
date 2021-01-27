---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingEpoch
title: Operace _RunSingleTrainingEpoch
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingEpoch
qsharp.summary: Perform one epoch of sequential classifier training on a subset of data samples.
ms.openlocfilehash: a8ae35fdd6c4e219444e7d6f7587ea31603b9999
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856183"
---
# <a name="_runsingletrainingepoch-operation"></a>Operace _RunSingleTrainingEpoch

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Proveďte jednu epocha sekvenčního školení třídění na podmnožinu ukázek dat.

```qsharp
operation _RunSingleTrainingEpoch (encodedSamples : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, periodScore : Int, options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel, nPreviousBestMisses : Int) : (Int, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a>Vstup

### <a name="encodedsamples--labeledsamplestategenerator"></a>encodedSamples: ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []




### <a name="schedule--samplingschedule"></a>plán: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)




### <a name="periodscore--int"></a>periodScore: [int](xref:microsoft.quantum.lang-ref.int)

Počet kroků přechodu mezi body bodování.
Pro nejlepší přesnost nastavte na hodnotu 1.


### <a name="options--trainingoptions"></a>možnosti: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

Možnosti, které se mají použít při školení


### <a name="model--sequentialmodel"></a>Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Sekvenční model, který se má vyškolet


### <a name="npreviousbestmisses--int"></a>nPreviousBestMisses: [int](xref:microsoft.quantum.lang-ref.int)

Nejlepší počet chybných klasifikací zjištěných v předchozích epochs.



## <a name="output--intsequentialmodel"></a>Výstup: ([int](xref:microsoft.quantum.lang-ref.int);[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))

- Nejmenší počet chybných klasifikací pozorovaných do tohoto epocha.
- Byl nalezen nový nejlepší sekvenční model.