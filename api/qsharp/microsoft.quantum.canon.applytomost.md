---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: Operace ApplyToMost
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 2c6c8873859439e71436f6beb0de40dfd1e21f43
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704776"
---
# <a name="applytomost-operation"></a>Operace ApplyToMost

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje operaci na všechny, ale na poslední prvek pole.

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a>Popis

Daná operace `op` a pole cílů `targets` platí `op(Most(targets))` .

## <a name="input"></a>Vstup

### <a name="op--t--unit"></a>op: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace, která se má použít.


### <a name="targets--t"></a>cíle: t []

Pole cílů, z nichž všechny kromě posledního budou aplikovány na `op` .



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která má být použita.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToMostA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [Microsoft. proApplyToMostC. Canon.](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [Microsoft. proApplyToMostCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToMostCA)