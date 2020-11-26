---
uid: Microsoft.Quantum.Canon.ApplyIf
title: Operace ApplyIf
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c5a1012328fa012ee02707aa59c94ac9c44b8e87
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218831"
---
# <a name="applyif-operation"></a>Operace ApplyIf

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Použije operaci s podmíněným klasickým bitem.

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a>Popis

`op`Pokud je zadaná operace a bitová hodnota `bit` , platí `op` pro `target` if `bit` `true` . `false`V případě, že se nic nestane s `target` .

## <a name="input"></a>Vstup

### <a name="op--t--unit"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

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