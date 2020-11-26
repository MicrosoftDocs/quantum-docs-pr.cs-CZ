---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: Operace ComputeReciprocalFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: 3ca050d6ce9daaa10e14c2f12dd571398cf436b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223387"
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

