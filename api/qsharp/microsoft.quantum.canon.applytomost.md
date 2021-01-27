---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: Operace ApplyToMost
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a3918233e101f3d8956601dcc7d85edcf6196ac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850594"
---
# <a name="applytomost-operation"></a>Operace ApplyToMost

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Příklad

Následující fragmenty Q # jsou ekvivalentní:

```qsharp
ApplyToMost(ApplyCNOTChain, register);
ApplyCNOTChain(Most(register));
```

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToMostA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [Microsoft. proApplyToMostC. Canon.](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [Microsoft. proApplyToMostCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToMostCA)