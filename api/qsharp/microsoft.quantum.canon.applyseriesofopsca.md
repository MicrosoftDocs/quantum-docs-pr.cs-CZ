---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: Operace ApplySeriesOfOpsCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 9a1f6189428b086c38b1d0f289afb18c2cf1be40
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850865"
---
# <a name="applyseriesofopsca-operation"></a>Operace ApplySeriesOfOpsCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje seznam operací OPS a jejich cílů postupně na pole. (Sousední a řízený)

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="listofops--t--unit--is-adj--ctl"></a>listOfOps: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL []

Seznam operací, přičemž každý z nich vezme pole, které se má použít. Jsou aplikované postupně, nejnižšími indexy jako první.
Každá z nich musí mít sousední i řízený funktor.


### <a name="targets--int"></a>cíle: [int](xref:microsoft.quantum.lang-ref.int)[] []

Vnořená pole popisující cíle pro op. Každé pole by mělo obsahovat seznam čísla popisujících indexy, které se mají použít.


### <a name="register--t"></a>registr: t []

Qubit registrace, na které se má pracovat.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S



## <a name="example"></a>Příklad

Následující příkaz použije EXP ([PauliX, PauliY], 0,5) na qubits 0, 1//then X na qubit 2 let OPS = [exp ([PauliX, PauliY], 0,5, _), ApplyToFirstQubitCA (X, _)]; Povolit indexy = [[0, 1], [2]]; ApplySeriesOfOpsCA (OPS; Indexes; qubitArray);

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyOpRepeatedlyOver. Canon.](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)