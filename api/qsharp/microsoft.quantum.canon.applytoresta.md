---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: Operace ApplyToRestA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 69001f6c8d65806e7259f2d2f2741d48866daa84
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841267"
---
# <a name="applytoresta-operation"></a>Operace ApplyToRestA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje operaci na všechny, ale na první prvek pole.

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a>Popis

Daná operace `op` a pole cílů `targets` platí `op(Rest(targets))` .

## <a name="input"></a>Vstup

### <a name="op--t--unit--is-adj"></a>op: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Operace, která se má použít.


### <a name="targets--t"></a>cíle: t []

Pole cílů, z nichž všechny kromě prvního budou aplikovány na `op` .



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která má být použita.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToRest. Canon.](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [Microsoft. proApplyToRestC. Canon.](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [Microsoft. proApplyToRestCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToRestCA)