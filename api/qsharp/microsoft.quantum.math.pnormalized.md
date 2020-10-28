---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 6f9dfebe83f52cbf486cd8e6874d3699f5e6b8ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707917"
---
# <a name="pnormalized-function"></a>PNormalized – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček [](https://nuget.org/packages/)


Normalizuje vektor `Double` s v `L(p)` normě.

To znamená, že předané pole $x $ typu `Double[]` vrátí pole, kde jsou všechny prvky děleny $p $-norm $ \| x \| _p $.

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a>Vstup

### <a name="p--double"></a>p: [Double](xref:microsoft.quantum.lang-ref.double)

Exponent $p $ v $p $-norma.


### <a name="array--double"></a>Array: [Double](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)[]

Pole $x $ normalizován $p $-norm $ \| x \| _p $.

## <a name="see-also"></a>Viz také

- [Microsoft. PNorm. Math.](xref:Microsoft.Quantum.Math.PNorm)