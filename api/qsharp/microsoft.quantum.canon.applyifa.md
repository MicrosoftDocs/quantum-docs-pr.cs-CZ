---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: Operace ApplyIfA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: d2880bbb95ebaf621ef9e5885051b94f32a3f1cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218763"
---
# <a name="applyifa-operation"></a>Operace ApplyIfA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje v klasickém bitu operaci s sousedním objektem.

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit is Adj
```


## <a name="description"></a>Popis

`op`Pokud je zadaná operace a bitová hodnota `bit` , platí `op` pro `target` if `bit` `true` . `false`V případě, že se nic nestane s `target` .
Přípona `A` označuje, že operace, která se má použít, je sousední.

## <a name="input"></a>Vstup

### <a name="op--t--unit--is-adj"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

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