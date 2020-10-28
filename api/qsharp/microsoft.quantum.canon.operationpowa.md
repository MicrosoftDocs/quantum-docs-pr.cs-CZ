---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 66df354c6de7e48624712276882759043b78466c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698936"
---
# <a name="operationpowa-function"></a>OperationPowA – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Vyvolá operaci s napájením.
Modifikátor `A` označuje, že operace je sousední.

To znamená, že vzhledem k operaci, která představuje bránu $U $, vrátí novou operaci $U ^ m $ pro $m pro napájení $.

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a>Vstup

### <a name="op--t--unit-adj"></a>op: t => ADJ. [Unit](xref:microsoft.quantum.lang-ref.unit)

Operace $U $ představuje bránu, která se má opakovat.


### <a name="power--int"></a>napájení: [int](xref:microsoft.quantum.lang-ref.int)

Počet opakování $U $.



## <a name="output--t--unit-adj"></a>Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ

Nová operace představující $U ^ m $, kde $m = \texttt{Power} $.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ operace, která má být zapnuta.

## <a name="see-also"></a>Viz také

- [Microsoft. proOperationPow. Canon.](xref:Microsoft.Quantum.Canon.OperationPow)