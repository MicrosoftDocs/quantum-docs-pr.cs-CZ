---
uid: Microsoft.Quantum.Arithmetic.EvaluatePolynomialFxP
title: Operace EvaluatePolynomialFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluatePolynomialFxP
qsharp.summary: Evaluates a polynomial in a fixed-point representation.
ms.openlocfilehash: d88f9002f4ce39b6a16091837c76168fb3a2f086
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843211"
---
# <a name="evaluatepolynomialfxp-operation"></a>Operace EvaluatePolynomialFxP

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Vyhodnotí polynomickou reprezentaci s pevnou desetinnou čárkou.

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="coefficients--double"></a>koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]

Koúčinnosti polynomu jako dvojitá Array, tj. Array $ [a_0, a_1,..., a_d] $ pro polynomická $P (x) = a_0 + a_1 x + \cdots + a_d x ^ d $.


### <a name="fpx--fixedpoint"></a>FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Vstupní číslo s pevnou desetinnou čárkou, pro které se má vyhodnotit polynomická hodnota


### <a name="result--fixedpoint"></a>výsledek: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Výstupní číslo s pevnou desetinnou čárkou, které bude obsahovat $P (x) $. Musí být ve stavu $ \ket {0} $ původně.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

