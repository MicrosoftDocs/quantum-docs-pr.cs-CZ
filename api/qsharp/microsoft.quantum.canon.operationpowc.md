---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 05b0d5b286e16c308d8c3df8fb8fa1ac8c9868ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852338"
---
# <a name="operationpowc-function"></a>OperationPowC – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vyvolá operaci s napájením.
Modifikátor `C` označuje, že operace je ovladatelné.

To znamená, že vzhledem k operaci, která představuje bránu $U $, vrátí novou operaci $U ^ m $ pro $m pro napájení $.

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a>Vstup

### <a name="op--t--unit--is-ctl"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL

Operace $U $ představuje bránu, která se má opakovat.


### <a name="power--int"></a>napájení: [int](xref:microsoft.quantum.lang-ref.int)

Počet opakování $U $.



## <a name="output--t--unit--is-ctl"></a>Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL

Nová operace představující $U ^ m $, kde $m = \texttt{Power} $.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ operace, která má být zapnuta.

## <a name="see-also"></a>Viz také

- [Microsoft. proOperationPow. Canon.](xref:Microsoft.Quantum.Canon.OperationPow)