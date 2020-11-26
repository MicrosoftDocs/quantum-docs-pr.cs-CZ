---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: 969be01204bad497496ff24cb64213f5fe1f089b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209753"
---
# <a name="xbits-function"></a>XBits – funkce

Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Vrací celé číslo představující X bitů pole operátorů Pauli.

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>Vstup

### <a name="paulis--pauli"></a>Pauls: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Pole operátorů Pauli, které se mají znázornit jako celé číslo.



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Celé číslo $x $ s binární reprezentací $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, kde $p _i = $0, pokud je `paulis[i]` `PauliI` nebo `PauliZ` a kde $p _i = $1, pokud `paulis[i]` je `PauliX` nebo `PauliY` .

## <a name="remarks"></a>Poznámky

Funkce bude vyvolána, pokud `paulis` je délka pole větší než 63.

## <a name="see-also"></a>Viz také

- [Microsoft... bitový. ZBits](xref:Microsoft.Quantum.Bitwise.ZBits)