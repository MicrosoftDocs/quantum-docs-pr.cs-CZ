---
uid: Microsoft.Quantum.Canon.ApplyToRestCA
title: Operace ApplyToRestCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestCA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: d2dc10803044980d53f80f0577d16cb14a2eb301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704681"
---
# <a name="applytorestca-operation"></a>Operace ApplyToRestCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje operaci na všechny, ale na první prvek pole.

```qsharp
operation ApplyToRestCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a>Popis

Daná operace `op` a pole cílů `targets` platí `op(Rest(targets))` .

## <a name="input"></a>Vstup

### <a name="op--t--unit-adj--ctl"></a>op: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operace, která se má použít.


### <a name="targets--t"></a>cíle: t []

Pole cílů, z nichž všechny kromě prvního budou aplikovány na `op` .



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která má být použita.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToRest. Canon.](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [Microsoft. proApplyToRestA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [Microsoft. proApplyToRestC. Canon.](xref:Microsoft.Quantum.Canon.ApplyToRestC)