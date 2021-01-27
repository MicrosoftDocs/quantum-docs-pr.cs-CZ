---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: Operace IterateThroughCartesianPower
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 3a303d13c4a6f102dab92d814e24df9d90213fbe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840301"
---
# <a name="iteratethroughcartesianpower-operation"></a>Operace IterateThroughCartesianPower

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje operaci pro každý index v kartézském výkonu rozsahu celého čísla.

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>Popis

Iterativní postupně aplikuje operaci pro každý prvek kartézském výkonu rozsahu `0..(bound - 1)` .

## <a name="input"></a>Vstup

### <a name="power--int"></a>napájení: [int](xref:microsoft.quantum.lang-ref.int)

Kartézském napájení, na které `0..(bound - 1)` by měl být rozsah vyvolán.


### <a name="bound--int"></a>Bound: [int](xref:microsoft.quantum.lang-ref.int)

Specifikace rozsahu, který se má iterovat, zadaný jako délka rozsahu


### <a name="op--int--unit"></a>op: [int](xref:microsoft.quantum.lang-ref.int)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace, která má být volána pro každý prvek daného kartézském napájení.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Příklad

Vzhledem k operaci `op` jsou tyto dva fragmenty ekvivalentní:

```qsharp
IterateThroughCartesianPower(2, 3, op);
```

```qsharp
op([0, 0]);
op([1, 0]);
op([2, 0]);
op([0, 1]);
// ..
op([2, 2]);
```

## <a name="see-also"></a>Viz také

- [Microsoft. proIterateThroughCartesianProduct. Canon.](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)