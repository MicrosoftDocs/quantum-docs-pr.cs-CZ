---
uid: Microsoft.Quantum.MachineLearning._UpdatedBias
title: _UpdatedBias funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _UpdatedBias
qsharp.summary: Returns a bias value that leads to near-minimum misclassification score.
ms.openlocfilehash: 41a51d8a6a8af299ce3e84b727336b098a3d1160
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844447"
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

