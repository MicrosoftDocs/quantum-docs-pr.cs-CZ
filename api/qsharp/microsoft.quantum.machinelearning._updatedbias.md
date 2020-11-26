---
uid: Microsoft.Quantum.MachineLearning._UpdatedBias
title: _UpdatedBias funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _UpdatedBias
qsharp.summary: Returns a bias value that leads to near-minimum misclassification score.
ms.openlocfilehash: 141edf6e425a060a995bfc181aefb1bcffdb128b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196697"
---
# <a name="_updatedbias-function"></a>_UpdatedBias funkce

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Vrátí hodnotu posunu, která vede k téměř minimálnímu skóre klasifikace.

```qsharp
function _UpdatedBias (labeledProbabilities : (Double, Int)[], bias : Double, tolerance : Double) : Double
```


## <a name="input"></a>Vstup

### <a name="labeledprobabilities--doubleint"></a>labeledProbabilities: ([Double](xref:microsoft.quantum.lang-ref.double),[int](xref:microsoft.quantum.lang-ref.int)) []




### <a name="bias--double"></a>bias: [Double](xref:microsoft.quantum.lang-ref.double)




### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)

