---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 9e356d68233519978e007e5a2999ca1be8cb7f83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697228"
---
# <a name="nmisclassifications-function"></a>NMisclassifications – funkce

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček [](https://nuget.org/packages/)


Vzhledem k sadě odvozených popisků a sadě správných popisků vrátí počet indexů, na kterých se každá sada popisků liší.

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>Vstup

### <a name="proposed--int"></a>Navrhovaný: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>skutečnost: [int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Počet indexů `idx` , které `inferredLabels[idx] != actualLabels[idx]` .