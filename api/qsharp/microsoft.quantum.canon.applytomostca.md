---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: Operace ApplyToMostCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 2ce76d2a86665fbfa5f5d91df23220c7c80981e3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208410"
---
# <a name="applytomostca-operation"></a>Operace ApplyToMostCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje operaci na všechny, ale na poslední prvek pole.

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Daná operace `op` a pole cílů `targets` platí `op(Most(targets))` .

## <a name="input"></a>Vstup

### <a name="op--t--unit--is-adj--ctl"></a>op: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Operace, která se má použít.


### <a name="targets--t"></a>cíle: t []

Pole cílů, z nichž všechny kromě posledního budou aplikovány na `op` .



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která má být použita.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToMost. Canon.](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [Microsoft. proApplyToMostA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [Microsoft. proApplyToMostC. Canon.](xref:Microsoft.Quantum.Canon.ApplyToMostC)