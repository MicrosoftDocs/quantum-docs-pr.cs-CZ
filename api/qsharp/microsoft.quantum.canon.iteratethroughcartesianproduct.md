---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: Operace IterateThroughCartesianProduct
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: e4fc71f6f707639f6f89eece8546ec2fb434a15a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704096"
---
# <a name="iteratethroughcartesianproduct-operation"></a>Operace IterateThroughCartesianProduct

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


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



## <a name="see-also"></a>Viz také

- [Microsoft. proIterateThroughCartesianPower. Canon.](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)