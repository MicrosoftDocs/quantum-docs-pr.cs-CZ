---
uid: Microsoft.Quantum.Canon.BoundA
title: Bounda funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3d0a5ba5d3d9c76289ed29e59a9c226358b83797
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844544"
---
# <a name="bounda-function"></a>Bounda funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vzhledem k poli operací, které fungují na jednom vstupu, vytvoří nová operace, která provede každou danou operaci v pořadí.
Modifikátor `A` označuje, že všechny operace v poli jsou sousední.

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a>Vstup

### <a name="operations--t--unit--is-adj"></a>operace: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ []

Posloupnost operací, které mají být provedeny na daném vstupu.



## <a name="output--t--unit--is-adj"></a>Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Nová operace, která každou danou operaci provede v pořadí podle jeho vstupu.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Cíl, na kterém každá z operací v poli působí.

## <a name="example"></a>Příklad

Následují ekvivalenty:

```qsharp
let bound = BoundA([U, V]);
bound(x);
```

a

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Viz také

- [Microsoft. prodoby. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)