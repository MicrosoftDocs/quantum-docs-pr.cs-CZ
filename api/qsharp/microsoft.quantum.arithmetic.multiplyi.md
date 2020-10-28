---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: Operace násobení
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7b44f64fdddfd95f51683c2c3b2f4d37d0cf6841
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706369"
---
# <a name="multiplyi-operation"></a>Operace násobení

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček [](https://nuget.org/packages/)


Vynásobit celé číslo `xs` `ys` a uložit výsledek do `result` , který musí být zpočátku nula.

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Vstup

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit multiplicand (LittleEndian)


### <a name="ys--littleendian"></a>y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit násobitele (LittleEndian)


### <a name="result--littleendian"></a>výsledek: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$2N $-bit výsledek (LittleEndian), musí být ve stavu $ \ket {0} $ zpočátku.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

K implementaci násobení slouží standardní přístup Shift-and-Add.
Řízená verze se vylepšila tak, že se $x _i $ do ancilla qubit v podmínce qubits ovládacího prvku a pak se řízení přidalo na ancilla qubit.