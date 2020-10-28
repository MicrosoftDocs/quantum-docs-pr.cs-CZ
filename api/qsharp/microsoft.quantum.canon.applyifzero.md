---
uid: Microsoft.Quantum.Canon.ApplyIfZero
title: Operace ApplyIfZero
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZero
qsharp.summary: Applies an operation conditioned on a classical result value being zero.
ms.openlocfilehash: 7435150937143a8d1a67afe334b683932a9655de
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705249"
---
# <a name="applyifzero-operation"></a>Operace ApplyIfZero

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje operaci s podmíněnou hodnotou pro klasický výsledek nula.

```qsharp
operation ApplyIfZero<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a>Popis

`op`Pokud je zadaná operace a výsledná hodnota `result` , platí `op` pro pravidlo `target` if `result` `Zero` . `One`V případě, že se nic nestane s `target` .

## <a name="input"></a>Vstup

### <a name="result--__invalidresult__"></a>výsledek: __neplatné <Result>__

Výsledek měření, který určuje, zda je použita možnost op nebo ne.


### <a name="op--t--unit"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace, která se má podmíněně použít


### <a name="target--t"></a>cíl: t

Vstup, na který se operace používá



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která se má podmíněně použít.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyIfZeroC. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [Microsoft. proApplyIfZeroA. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [Microsoft. proApplyIfZeroCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)