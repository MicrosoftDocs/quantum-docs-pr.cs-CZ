---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: Operace ApplyToRestA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 99a18e835115491cc3451a4e3b44a6ff70e9dc6c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704689"
---
# <a name="applytoresta-operation"></a>Operace ApplyToRestA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje operaci na všechny, ale na první prvek pole.

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a>Popis

Daná operace `op` a pole cílů `targets` platí `op(Rest(targets))` .

## <a name="input"></a>Vstup

### <a name="op--t--unit-adj"></a>op: t [] => ADJ. [Unit](xref:microsoft.quantum.lang-ref.unit)

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