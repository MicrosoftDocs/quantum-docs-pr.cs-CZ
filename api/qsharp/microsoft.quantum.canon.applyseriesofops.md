---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: Operace ApplySeriesOfOps
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: aff0bcb831960153166e88aef1f05e000125d5d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705025"
---
# <a name="applyseriesofops-operation"></a>Operace ApplySeriesOfOps

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje seznam operací OPS a jejich cílů postupně na pole.

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="listofops--t--unit-"></a>listOfOps: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit) []

Seznam operací, přičemž každý z nich vezme pole, které se má použít. Jsou aplikované postupně, nejnižšími indexy jako první.


### <a name="targets--int"></a>cíle: [int](xref:microsoft.quantum.lang-ref.int)[] []

Vnořená pole popisující cíle pro op. Každé pole by mělo obsahovat seznam čísla popisujících indexy, které se mají použít.


### <a name="register--t"></a>registr: t []

Qubit registrace, na které se má pracovat.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S



## <a name="see-also"></a>Viz také

- [Microsoft. proApplyOpRepeatedlyOver. Canon.](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)