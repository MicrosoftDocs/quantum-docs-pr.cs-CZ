---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: Operace AssertMostSignificantBit
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 408e50ed9f2e6c8ba35db20855608d2bd1f24eea
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707449"
---
# <a name="assertmostsignificantbit-operation"></a>Operace AssertMostSignificantBit

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček [](https://nuget.org/packages/)


Vyhodnotí, že nejvýznamnější qubit registru qubit, který představuje unsigned integer, je v určitém stavu.

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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