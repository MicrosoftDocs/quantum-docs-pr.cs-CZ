---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: adc7042d6108c7ec72d13340633824d3eaf5e18e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853901"
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

## <a name="example"></a>Příklad

```qsharp
let nMisclassifications = NMisclassifications([1, 1, 0, 0], [0, 1, 1, 0]);
Message($"{nMisclassifications}"); // Will print 2.
```