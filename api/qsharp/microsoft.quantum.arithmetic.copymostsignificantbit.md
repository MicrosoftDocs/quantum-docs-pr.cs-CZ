---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: Operace CopyMostSignificantBit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 39a2dc2fe33f46c2767def06a44cde07e2f01497
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223285"
---
# <a name="copymostsignificantbit-operation"></a>Operace CopyMostSignificantBit

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zkopíruje nejvýznamnější bit qubit registru `from` reprezentujícího unsigned integer do qubit `target` .

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
```


## <a name="input"></a>Vstup

### <a name="from--littleendian"></a>z: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Unsigned integer, ze kterých se kopíruje nejvyšší bit.
celé číslo je kódováno ve formátu Little endian.


### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, do kterého se kopíruje nejvyšší bit. Bitové kódování je v výpočetních intervalech.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Viz také

- [Microsoft. prostředníky. aritmetické. LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)