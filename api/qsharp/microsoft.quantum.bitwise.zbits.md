---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: d1ddc2a4cdbdfd3945885de856456b3108592594
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842062"
---
# <a name="zbits-function"></a>ZBits – funkce

Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Vrací celé číslo představující bity Z pole operátorů Pauli.

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>Vstup

### <a name="paulis--pauli"></a>Pauls: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Pole operátorů Pauli, které se mají znázornit jako celé číslo.



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Celé číslo $x $ s binární reprezentací $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, kde $p _i = $0, pokud je `paulis[i]` `PauliI` nebo `PauliX` a kde $p _i = $1, pokud `paulis[i]` je `PauliY` nebo `PauliZ` .

## <a name="remarks"></a>Poznámky

Funkce bude vyvolána, pokud `paulis` je délka pole větší než 63.

## <a name="see-also"></a>Viz také

- [Microsoft... bitový. XBits](xref:Microsoft.Quantum.Bitwise.XBits)