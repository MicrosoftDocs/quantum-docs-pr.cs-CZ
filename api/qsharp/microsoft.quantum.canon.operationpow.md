---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 5cf9017175f44a8a0b8f865624a6c312d25aded1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698952"
---
# <a name="operationpow-function"></a>OperationPow – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Vyvolá operaci s napájením.

To znamená, že vzhledem k operaci, která představuje bránu $U $, vrátí novou operaci $U ^ m $ pro $m pro napájení $.

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a>Vstup

### <a name="op--t--unit"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace $U $ představuje bránu, která se má opakovat.


### <a name="power--int"></a>napájení: [int](xref:microsoft.quantum.lang-ref.int)

Počet opakování $U $.



## <a name="output--t--unit"></a>Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Nová operace představující $U ^ m $, kde $m = \texttt{Power} $.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ operace, která má být zapnuta.

## <a name="see-also"></a>Viz také

- [Microsoft. proOperationPowC. Canon.](xref:Microsoft.Quantum.Canon.OperationPowC)
- [Microsoft. proOperationPowA. Canon.](xref:Microsoft.Quantum.Canon.OperationPowA)
- [Microsoft. proOperationPowCA. Canon.](xref:Microsoft.Quantum.Canon.OperationPowCA)