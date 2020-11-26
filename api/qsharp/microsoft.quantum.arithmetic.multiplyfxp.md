---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: Operace MultiplyFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 3c9ef9ade660e1f420d85162104d773b96722eeb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222605"
---
# <a name="multiplyfxp-operation"></a>Operace MultiplyFxP

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Vynásobí dvě čísla s pevnou desetinnou čárkou v registrech.

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="fp1--fixedpoint"></a>FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

První číslo s pevnou desetinnou čárkou.


### <a name="fp2--fixedpoint"></a>FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Druhé číslo s pevnou desetinnou čárkou.


### <a name="result--fixedpoint"></a>výsledek: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Výsledek s pevnou desetinnou čárkou, musí být ve stavu $ \ket {0} $ původně.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Aktuální implementace vyžaduje, aby tři čísla s pevnou desetinnou čárkou měla stejnou polohu bodu a stejný počet qubits.