---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 46b24c283a01e6ac1c959ee4a6899591ee708ff7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848418"
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