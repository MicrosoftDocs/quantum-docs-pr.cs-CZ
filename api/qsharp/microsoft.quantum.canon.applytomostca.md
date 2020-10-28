---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: Operace ApplyToMostCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 797cbd835446f31b2df60dbb184f888e6d0356aa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704737"
---
# <a name="applytomostca-operation"></a>Operace ApplyToMostCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje operaci na všechny, ale na poslední prvek pole.

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a>Popis

Daná operace `op` a pole cílů `targets` platí `op(Most(targets))` .

## <a name="input"></a>Vstup

### <a name="op--t--unit-adj--ctl"></a>op: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

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