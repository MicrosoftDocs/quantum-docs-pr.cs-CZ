---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: Operace AssertMostSignificantBit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: b0b52a4ba7492d68896669aeb0b6b550d2f27f64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843427"
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