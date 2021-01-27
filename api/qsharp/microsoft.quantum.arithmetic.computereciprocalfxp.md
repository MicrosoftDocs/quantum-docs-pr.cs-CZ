---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: Operace ComputeReciprocalFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: db7425f1a8a9b5ddfdc6b123dad003298e3670e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843249"
---
# <a name="computereciprocalfxp-operation"></a>Operace ComputeReciprocalFxP

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Vypočítá $1/x $ pro číslo s pevnou desetinnou čárkou $x $.

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="x--fixedpoint"></a>x: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Číslo s pevnou desetinnou čárkou, které se má vrátit


### <a name="result--fixedpoint"></a>výsledek: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Číslo s pevnou desetinnou čárkou, které bude obsahovat výsledek. Je nutné inicializovat na $ \ket{0.0} $.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

