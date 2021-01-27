---
uid: Microsoft.Quantum.Canon.ApplyToRestCA
title: Operace ApplyToRestCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestCA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: e64eeaae2151a28c289e3e71e47f897d6c378b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841245"
---
# <a name="applytorestca-operation"></a>Operace ApplyToRestCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje operaci na všechny, ale na první prvek pole.

```qsharp
operation ApplyToRestCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Daná operace `op` a pole cílů `targets` platí `op(Rest(targets))` .

## <a name="input"></a>Vstup

### <a name="op--t--unit--is-adj--ctl"></a>op: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

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