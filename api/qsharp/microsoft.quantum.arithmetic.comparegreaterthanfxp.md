---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: Operace CompareGreaterThanFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: 1e9afc7645f62b932fa8ebc3d33e21a2a5182361
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223523"
---
# <a name="comparegreaterthanfxp-operation"></a>Operace CompareGreaterThanFxP

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Porovná dvě číslo s pevnou desetinnou čárkou, která jsou uložená v registrech, a řídí převrácení výsledku.

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="fp1--fixedpoint"></a>FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

První číslo s pevnou desetinnou čárkou, které se má porovnat


### <a name="fp2--fixedpoint"></a>FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Druhé číslo s pevnou desetinnou čárkou, které se má porovnat


### <a name="result--qubit"></a>výsledek: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Výsledek porovnání Bude převráceno `fp1 > fp2` , pokud.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Aktuální implementace vyžaduje, aby dvě čísla s pevnou desetinnou čárkou měla stejnou polohu bodu a stejný počet qubits.