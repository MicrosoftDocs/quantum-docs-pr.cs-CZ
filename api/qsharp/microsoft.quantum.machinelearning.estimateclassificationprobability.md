---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: Operace EstimateClassificationProbability
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: c2b74bc55ad9005a8f52d05796e856f4f2fb62ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853944"
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