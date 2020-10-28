---
uid: Microsoft.Quantum.Canon.ApplyToTailC
title: Operace ApplyToTailC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailC
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 631e08666002d8077c6f8b78525b06b104dd4c7c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704625"
---
# <a name="applytotailc-operation"></a>Operace ApplyToTailC

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Použije operaci na poslední prvek pole.

```qsharp
operation ApplyToTailC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a>Popis

Daná operace `op` a pole cílů `targets` platí `op(Tail(targets))` .

## <a name="input"></a>Vstup

### <a name="op--t--unit-ctl"></a>op: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL

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
- [Microsoft. proApplyToTailCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToTailCA)