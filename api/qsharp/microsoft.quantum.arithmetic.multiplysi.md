---
uid: Microsoft.Quantum.Arithmetic.MultiplySI
title: Operace MultiplySI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplySI
qsharp.summary: Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7c7e7dfaee9b9dc717db44956506984e60281dd2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843018"
---
# <a name="multiplysi-operation"></a>Operace MultiplySI

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Vynásobit celé číslo se znaménkem `xs` (signed integer) `ys` a uložit výsledek do `result` , který musí být zpočátku nula.

```qsharp
operation MultiplySI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="xs--signedlittleendian"></a>xs: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

n-bit multiplicand (SignedLittleEndian)


### <a name="ys--signedlittleendian"></a>y: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

n-bit násobitele (SignedLittleEndian)


### <a name="result--signedlittleendian"></a>výsledek: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

2N výsledek (SignedLittleEndian), musí být ve stavu $ \ket {0} $ zpočátku.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

