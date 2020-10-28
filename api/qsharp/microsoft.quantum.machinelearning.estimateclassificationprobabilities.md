---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: Operace EstimateClassificationProbabilities
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 2b7845d39256f718cc3e415207b8a47b24620bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697241"
---
# <a name="estimateclassificationprobabilities-operation"></a>Operace EstimateClassificationProbabilities

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček [](https://nuget.org/packages/)


Vzhledem k sadě vzorků a sekvenčnímu třídění odhadne pravděpodobnost klasifikace těchto vzorků opakovaným měřením výstupu klasifikátoru v každé ukázce.

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a>Vstup

### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

Tolerance, která umožňuje v kódování vzorku do operace přípravy stavu.


### <a name="model--sequentialmodel"></a>Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Sekvenční model, který se použije k odhadu pravděpodobnosti klasifikace pro dané vzorky.


### <a name="samples--double"></a>Samples: [Double](xref:microsoft.quantum.lang-ref.double)[] []

Pole vektorů funkcí pro každý vzorek, který má být klasifikován.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Počet měření, která se mají použít při odhadu pravděpodobnosti klasifikace.



## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)[]

Pole odhadů pravděpodobnosti klasifikace pro každou danou ukázku.