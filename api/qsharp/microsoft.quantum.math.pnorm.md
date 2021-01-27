---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 6207cca6cda5f9030facd31c327e58bdb9ecbf14
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847657"
---
# <a name="pnorm-function"></a>PNorm – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrací `L(p)` normu vektoru `Double` s.

To znamená, že předané pole $x $ typu `Double[]` vrátí $p $-norm $ \| x \| \_ p = (\ sum_ {j} | x_j | ^ {p}) ^ {1/p} $.

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a>Vstup

### <a name="p--double"></a>p: [Double](xref:microsoft.quantum.lang-ref.double)

Exponent $p $ v $p $-norma.


### <a name="array--double"></a>Array: [Double](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)

$P $-norm $ \| x \| _p $.