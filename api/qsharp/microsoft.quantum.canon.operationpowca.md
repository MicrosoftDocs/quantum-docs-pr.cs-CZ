---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 753063452616747309e3e228ce8a702f4378c61f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698924"
---
# <a name="operationpowca-function"></a>OperationPowCA – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Vyvolá operaci s napájením.
Modifikátor `A` označuje, že operace je ovladatelné a s sousedními poli.

To znamená, že vzhledem k operaci, která představuje bránu $U $, vrátí novou operaci $U ^ m $ pro $m pro napájení $.

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a>Vstup

### <a name="op--t--unit-ctl--adj"></a>op: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL a ADJ

Operace $U $ představuje bránu, která se má opakovat.


### <a name="power--int"></a>napájení: [int](xref:microsoft.quantum.lang-ref.int)

Počet opakování $U $.



## <a name="output--t--unit-ctl--adj"></a>Výstup: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL a ADJ

Nová operace představující $U ^ m $, kde $m = \texttt{Power} $.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ operace, která má být zapnuta.

## <a name="see-also"></a>Viz také

- [Microsoft. proOperationPow. Canon.](xref:Microsoft.Quantum.Canon.OperationPow)