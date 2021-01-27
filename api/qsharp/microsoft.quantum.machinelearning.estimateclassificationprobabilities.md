---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: Operace EstimateClassificationProbabilities
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: eea503d042d6ffc241186c117a7c02ee72983b09
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847726"
---
# <a name="estimateclassificationprobabilities-operation"></a>Operace EstimateClassificationProbabilities

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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