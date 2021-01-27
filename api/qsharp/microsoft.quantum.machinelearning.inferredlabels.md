---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 576b4b1f11fc21476bbb019d4b0326981294528c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848396"
---
# <a name="inferredlabels-function"></a>InferredLabels – funkce

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Vzhledem k poli pravděpodobnosti klasifikace a posunu vrátí popisek odvozený od každé pravděpodobnosti.

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a>Vstup

### <a name="bias--double"></a>bias: [Double](xref:microsoft.quantum.lang-ref.double)

Posun mezi dvěma třídami, obvykle výsledek školení klasifikátoru.


### <a name="probabilities--double"></a>pravděpodobnost: [Double](xref:microsoft.quantum.lang-ref.double)[]

Pole pravděpodobnosti klasifikace pro sadu vzorků, která obvykle vede k odhadování frekvencí klasifikace.



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]

Popisek odvozený od každé pravděpodobnosti klasifikace