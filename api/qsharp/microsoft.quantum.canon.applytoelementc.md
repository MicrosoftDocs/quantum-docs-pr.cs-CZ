---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: Operace ApplyToElementC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: c8d7841e3846ab435671f7959c724f987d8ad5a0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217573"
---
# <a name="applytoelementc-operation"></a>Operace ApplyToElementC

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Použije operaci na daný prvek pole.

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a>Popis

Pro danou operaci se `op` použije index `index` a pole cílů `targets` `op(targets[index])` .

## <a name="input"></a>Vstup

### <a name="op--t--unit--is-ctl"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL

Operace, která se má použít.


### <a name="index--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)

Index do pole cílů.


### <a name="targets--t"></a>cíle: t []

Pole možných cílů pro `op` .



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která má být použita.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToElement. Canon.](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [Microsoft. proApplyToElementA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [Microsoft. proApplyToElementCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToElementCA)