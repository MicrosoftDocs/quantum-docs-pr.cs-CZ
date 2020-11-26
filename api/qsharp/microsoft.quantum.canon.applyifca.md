---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: Operace ApplyIfCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: b0ac469d6dea51951e0d9b2cfceb54253d4b4c5d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209617"
---
# <a name="applyifca-operation"></a>Operace ApplyIfCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje jednotnou operaci s podmíněným klasickým bitem.

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

`op`Pokud je zadaná operace a bitová hodnota `bit` , platí `op` pro `target` if `bit` `true` . `false`V případě, že se nic nestane s `target` .
Přípona `CA` označuje, že operace, která se má použít, je jednotná (přivedená a přiléhající).

## <a name="input"></a>Vstup

### <a name="op--t--unit--is-adj--ctl"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

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