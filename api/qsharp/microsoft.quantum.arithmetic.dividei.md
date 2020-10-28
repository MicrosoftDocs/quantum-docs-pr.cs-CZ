---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: Operace dělení
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 0cc16dddc27a000dbc30de6ae27976a01fd9f4ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707344"
---
# <a name="dividei-operation"></a>Operace dělení

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček [](https://nuget.org/packages/)


Vydělí dvě celá čísla.

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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