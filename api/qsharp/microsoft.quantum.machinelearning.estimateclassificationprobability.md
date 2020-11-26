---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: Operace EstimateClassificationProbability
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 9d127bba9624e178fbdb631a1249efe5fc2be3b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196459"
---
# <a name="estimateclassificationprobability-operation"></a>Operace EstimateClassificationProbability

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Vzhledem k ukázce a sekvenčnímu třídění odhadne pravděpodobnost klasifikace pro tento vzorek opakovaným měřením výstupu klasifikátoru v dané ukázce.

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a>Vstup

### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

Tolerance, která umožňuje v kódování vzorku do operace přípravy stavu.


### <a name="model--sequentialmodel"></a>Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Sekvenční model, který má být použit k odhadu pravděpodobnosti klasifikace pro danou ukázku.


### <a name="sample--double"></a>Ukázka: [Double](xref:microsoft.quantum.lang-ref.double)[]

Vektor funkce pro ukázku, která má být klasifikována


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Počet měření, která se mají použít při odhadu pravděpodobnosti klasifikace.



## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)

Odhad pravděpodobnosti klasifikace pro danou ukázku.