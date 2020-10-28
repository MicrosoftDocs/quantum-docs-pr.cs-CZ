---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: Operace ApplySeriesOfOpsC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: d909aadbfe86f6d1314e9be5434249c40932ae4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705016"
---
# <a name="applyseriesofopsc-operation"></a>Operace ApplySeriesOfOpsC

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje seznam operací OPS a jejich cílů postupně na pole. Kontrol

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="listofops--t--unit-ctl"></a>listOfOps: t [] [=> CTL](xref:microsoft.quantum.lang-ref.unit) []

Seznam operací, přičemž každý z nich vezme pole, které se má použít. Jsou aplikované postupně, nejnižšími indexy jako první.
Každý musí mít řízený funktor


### <a name="targets--int"></a>cíle: [int](xref:microsoft.quantum.lang-ref.int)[] []

Vnořená pole popisující cíle pro op. Každé pole by mělo obsahovat seznam čísla popisujících indexy, které se mají použít.


### <a name="register--t"></a>registr: t []

Qubit registrace, na které se má pracovat.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S



## <a name="see-also"></a>Viz také

- [Microsoft. proApplyOpRepeatedlyOver. Canon.](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)