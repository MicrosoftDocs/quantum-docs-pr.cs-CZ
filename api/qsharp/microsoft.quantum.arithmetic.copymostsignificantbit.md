---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: Operace CopyMostSignificantBit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 609e937a03bebf45aa9398225bd1b7e2b717807a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843273"
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