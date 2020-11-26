---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA
title: Operace ApplyReversedOpBEA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 17d05e0914eead28ff0e04b858b003659d37ab7f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202817"
---
# <a name="applyreversedopbea-operation"></a>Operace ApplyReversedOpBEA

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje operaci, která přebírá vstup big-endian do registru kódování unsigned integer ve formátu Little endian.

```qsharp
operation ApplyReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj
```


## <a name="input"></a>Vstup

### <a name="op--bigendian--unit--is-adj"></a>op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) bigEndian je ADJ.

Operace, která funguje v registru big-endian.


### <a name="register--littleendian"></a>registrovat: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registr s malým endianm, který se má transformovat



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Viz také

- [Microsoft. prostředníky. aritmetické. ApplyReversedOpBE](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [Microsoft. prostředníky. aritmetické. ApplyReversedOpBEC](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [Microsoft. prostředníky. aritmetické. ApplyReversedOpBECA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)