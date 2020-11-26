---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: Operace ApplyToHeadC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 2b7321a6c385e2d98a0e91a8f58091ea8dc43ff4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208597"
---
# <a name="applytoheadc-operation"></a>Operace ApplyToHeadC

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Použije operaci na první prvek pole.

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a>Popis

Daná operace `op` a pole cílů `targets` platí `op(Head(targets))` .

## <a name="input"></a>Vstup

### <a name="op--t--unit--is-ctl"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL

Operace, která se má použít.


### <a name="targets--t"></a>cíle: t []

Pole cílů, na které se první použije `op` .



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která má být použita.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToHead. Canon.](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [Microsoft. proApplyToHeadA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [Microsoft. proApplyToHeadCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)