---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: Operace ApplyToTailCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 00755df80981a09ddfd8327ee9b35761d30af4f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704609"
---
# <a name="applytotailca-operation"></a>Operace ApplyToTailCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Použije operaci na poslední prvek pole.

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a>Popis

Daná operace `op` a pole cílů `targets` platí `op(Tail(targets))` .

## <a name="input"></a>Vstup

### <a name="op--t--unit-adj--ctl"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operace, která se má použít.


### <a name="targets--t"></a>cíle: t []

Pole cílů, z nichž poslední bude použito `op` .



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která má být použita.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToTail. Canon.](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [Microsoft. proApplyToTailA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [Microsoft. proApplyToTailC. Canon.](xref:Microsoft.Quantum.Canon.ApplyToTailC)