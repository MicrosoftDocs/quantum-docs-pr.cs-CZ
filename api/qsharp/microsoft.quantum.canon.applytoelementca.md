---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: Operace ApplyToElementCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 599a8afe1ab97b0ab0d6621cabd7707faaeddda3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704897"
---
# <a name="applytoelementca-operation"></a>Operace ApplyToElementCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Použije operaci na daný prvek pole.

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a>Popis

Pro danou operaci se `op` použije index `index` a pole cílů `targets` `op(targets[index])` .

## <a name="input"></a>Vstup

### <a name="op--t--unit-adj--ctl"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

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
- [Microsoft. proApplyToElementC. Canon.](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [Microsoft. proApplyToElementA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToElementA)