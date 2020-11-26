---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 30d049ba54630cd2f5f350280bad7f587599f459
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196306"
---
# <a name="nmisclassifications-function"></a>NMisclassifications – funkce

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Vzhledem k sadě odvozených popisků a sadě správných popisků vrátí počet indexů, na kterých se každá sada popisků liší.

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>Vstup

### <a name="proposed--int"></a>Navrhovaný: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>skutečnost: [int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Počet indexů `idx` , které `inferredLabels[idx] != actualLabels[idx]` .