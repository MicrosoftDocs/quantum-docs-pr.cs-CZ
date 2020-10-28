---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: Operace ApplyIfC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: e16254154909eb844164538acb7b82fedc11f86a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705353"
---
# <a name="applyifc-operation"></a>Operace ApplyIfC

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje naovladatelné operace s podmíněným klasickým bitem.

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a>Popis

`op`Pokud je zadaná operace a bitová hodnota `bit` , platí `op` pro `target` if `bit` `true` . `false`V případě, že se nic nestane s `target` .
Přípona `C` označuje, že operace, která se má použít, je ovladatelné.

## <a name="input"></a>Vstup

### <a name="op--t--unit-ctl"></a>op: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL

Operace, která se má podmíněně použít


### <a name="bit--bool"></a>bitová hodnota: [bool](xref:microsoft.quantum.lang-ref.bool)

logická hodnota, která určuje, zda je použita možnost op.


### <a name="target--t"></a>cíl: t

Vstup, na který se operace používá



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která se má podmíněně použít.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyIfC. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [Microsoft. proApplyIfA. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [Microsoft. proApplyIfCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfCA)