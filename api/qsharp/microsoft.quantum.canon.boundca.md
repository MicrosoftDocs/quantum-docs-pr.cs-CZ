---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 391183829a3cc8b7aa8051767dcfc6bec9638223
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844518"
---
# <a name="boundca-function"></a>BoundCA – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vzhledem k poli operací, které fungují na jednom vstupu, vytvoří nová operace, která provede každou danou operaci v pořadí.
Modifikátor `CA` označuje, že všechny operace v poli jsou sousedící a ovladatelné.

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a>Vstup

### <a name="operations--t--unit--is-adj--ctl"></a>operace: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL []

Posloupnost operací, které mají být provedeny na daném vstupu.



## <a name="output--t--unit--is-adj--ctl"></a>Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Nová operace, která každou danou operaci provede v pořadí podle jeho vstupu.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Cíl, na kterém každá z operací v poli působí.

## <a name="example"></a>Příklad

Následují ekvivalenty:

```qsharp
let bound = BoundCA([U, V]);
bound(x);
```

a

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Viz také

- [Microsoft. prodoby. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)