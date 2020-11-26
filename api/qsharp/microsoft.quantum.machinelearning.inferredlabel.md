---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: b64bb1ec52d2456ee1b627b920890223d173533b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211776"
---
# <a name="inferredlabel-function"></a>InferredLabel – funkce

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


S ohledem na pravděpodobnost klasifikace a bias vrátí popisek odvozený z této pravděpodobnosti.

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a>Vstup

### <a name="bias--double"></a>bias: [Double](xref:microsoft.quantum.lang-ref.double)

Posun mezi dvěma třídami, obvykle výsledek školení klasifikátoru.


### <a name="probability--double"></a>pravděpodobnost: [Double](xref:microsoft.quantum.lang-ref.double)

Pravděpodobnost klasifikace pro konkrétní vzorek, obvykle vyplývají z odhadu jeho četnosti klasifikace.



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Popisek odvozený od zadané pravděpodobnosti klasifikace.