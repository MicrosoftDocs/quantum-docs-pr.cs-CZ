---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: Operace EvaluateOddPolynomialFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: 1bf9b6e7c416e994e70b93e5967caefd444f6426
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223217"
---
# <a name="evaluateoddpolynomialfxp-operation"></a>Operace EvaluateOddPolynomialFxP

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Vyhodnotí lichý polynom v reprezentaci s pevnou desetinnou čárkou.

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="coefficients--double"></a>koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]

Poměrná část s lichým polynomem jako dvojitá Array, tj. Array $ [a_0, a_1,..., a_k] $ pro liché polynomy $P (x) = a_0 x + a_1 x ^ 3 + \cdots + a_k × ^ {2k + 1} $.


### <a name="fpx--fixedpoint"></a>FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Vstupní číslo s pevnou desetinnou čárkou, pro které se má vyhodnotit polynomická hodnota


### <a name="result--fixedpoint"></a>výsledek: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Výstupní číslo s pevnou desetinnou čárkou, které bude obsahovat P (x). Musí být ve stavu $ \ket {0} $ původně.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

