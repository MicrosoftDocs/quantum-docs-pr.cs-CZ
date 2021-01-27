---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 338c40f8eb9d6f1782989f2a91c86df561d480bf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852307"
---
# <a name="operationpowca-function"></a>OperationPowCA – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vyvolá operaci s napájením.
Modifikátor `A` označuje, že operace je ovladatelné a s sousedními poli.

To znamená, že vzhledem k operaci, která představuje bránu $U $, vrátí novou operaci $U ^ m $ pro $m pro napájení $.

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a>Vstup

### <a name="op--t--unit--is-adj--ctl"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Operace $U $ představuje bránu, která se má opakovat.


### <a name="power--int"></a>napájení: [int](xref:microsoft.quantum.lang-ref.int)

Počet opakování $U $.



## <a name="output--t--unit--is-adj--ctl"></a>Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Nová operace představující $U ^ m $, kde $m = \texttt{Power} $.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ operace, která má být zapnuta.

## <a name="see-also"></a>Viz také

- [Microsoft. proOperationPow. Canon.](xref:Microsoft.Quantum.Canon.OperationPow)