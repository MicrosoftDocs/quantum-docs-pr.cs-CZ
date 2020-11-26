---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: Operace dělení
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 4cff191e1f9d42659768b4059e477f1a07948ba1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223302"
---
# <a name="dividei-operation"></a>Operace dělení

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Vydělí dvě celá čísla.

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

`xs` bude obsahovat zbytek `xs - floor(xs/ys) * ys` a `result` bude obsahovat `floor(xs/ys)` .

## <a name="input"></a>Vstup

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit děleno, bude zbytek nahrazen.


### <a name="ys--littleendian"></a>y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bitový dělitel


### <a name="result--littleendian"></a>výsledek: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n bitový výsledek, musí být ve stavu $ \ket {0} $ zpočátku a bude nahrazen výsledkem dělení celého čísla.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

K implementaci dělení používá standardní přístup SHIFT a odečíst.
Řízená verze je specializovaná, taková odčítání nevyžaduje další ovládací prvky.