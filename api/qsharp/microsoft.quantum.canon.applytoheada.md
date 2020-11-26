---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: Operace ApplyToHeadA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3397c059706c48ff8ca47dd2312cfa9565aacaba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208631"
---
# <a name="applytoheada-operation"></a>Operace ApplyToHeadA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Použije operaci na první prvek pole.

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a>Popis

Daná operace `op` a pole cílů `targets` platí `op(Head(targets))` .

## <a name="input"></a>Vstup

### <a name="op--t--unit--is-adj"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Operace, která se má použít.


### <a name="targets--t"></a>cíle: t []

Pole cílů, na které se první použije `op` .



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která má být použita.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToHead. Canon.](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [Microsoft. proApplyToHeadC. Canon.](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [Microsoft. proApplyToHeadCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)