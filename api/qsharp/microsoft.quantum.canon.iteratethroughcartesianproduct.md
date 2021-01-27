---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: Operace IterateThroughCartesianProduct
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: a0aaa8ef6aa6798d31c810254c92820f8136800c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840280"
---
# <a name="iteratethroughcartesianproduct-operation"></a>Operace IterateThroughCartesianProduct

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje operaci pro každý index v kartézském produktu v několika oblastech.

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>Popis

Iterativní postupně aplikuje operaci pro každý prvek kartézském produktu `0..(bounds[0] - 1)` , `0..(bounds[1] - 1)` ,..., `0..(bounds[Length(bounds) - 1] - 1)`

## <a name="input"></a>Vstup

### <a name="bounds--int"></a>meze: [int](xref:microsoft.quantum.lang-ref.int)[]

Pole určující rozsahy, které se mají iterovat, přičemž každý rozsah je zadaný jako celočíselná délka.


### <a name="op--int--unit"></a>op: [int](xref:microsoft.quantum.lang-ref.int)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace, která má být volána pro každý prvek daného kartézském produktu.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Příklad

Vzhledem k operaci `op` jsou tyto dva fragmenty ekvivalentní:

```qsharp
IterateThroughCartesianProduct([3, 4, 5], op);
```

```qsharp
op([0, 0, 0]);
op([1, 0, 0]);
op([2, 0, 0]);
op([0, 1, 0]);
// ...
op([0, 3, 0]);
op([0, 0, 1]);
//
op([2, 3, 4]);
```

## <a name="see-also"></a>Viz také

- [Microsoft. proIterateThroughCartesianPower. Canon.](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)