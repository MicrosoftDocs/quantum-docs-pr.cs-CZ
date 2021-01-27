---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: ea6a88d07d3b246f666b793f0b10ab6598ea4ff6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854839"
---
# <a name="pnormalized-function"></a>PNormalized – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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