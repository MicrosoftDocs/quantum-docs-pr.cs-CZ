---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: Operace AssertMostSignificantBit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 41381455d1a96970647f887e038f7dff3a4eb204
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223778"
---
# <a name="assertmostsignificantbit-operation"></a>Operace AssertMostSignificantBit

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vyhodnotí, že nejvýznamnější qubit registru qubit, který představuje unsigned integer, je v určitém stavu.

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="value--__invalidresult__"></a>hodnota: __neplatné <Result>__

Hodnota nejvyššího bitu, který je využíván jako kontrolní výraz.


### <a name="number--littleendian"></a>číslo: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Celé číslo bez znaménka, z něhož je zaškrtnuto nejvyšší bit.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Řízená verze této operace ignoruje ovládací prvky.

## <a name="see-also"></a>Viz také

- [Microsoft. v. vnitřní. Assert](xref:Microsoft.Quantum.Intrinsic.Assert)