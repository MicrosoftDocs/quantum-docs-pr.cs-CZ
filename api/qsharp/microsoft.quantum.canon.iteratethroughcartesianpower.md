---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: Operace IterateThroughCartesianPower
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 526d28cbf3cd356b4f48eec02b3f032f70a868d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704088"
---
# <a name="iteratethroughcartesianpower-operation"></a>Operace IterateThroughCartesianPower

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


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



## <a name="see-also"></a>Viz také

- [Microsoft. proIterateThroughCartesianProduct. Canon.](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)