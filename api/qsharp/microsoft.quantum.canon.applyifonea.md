---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: Operace ApplyIfOneA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 200908f2958b74e4823c891ef901474d75d18336
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218542"
---
# <a name="applyifonea-operation"></a>Operace ApplyIfOneA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje na jednu operaci sousedících hodnot s hodnotou klasického výsledku.

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit is Adj
```


## <a name="description"></a>Popis

`op`Pokud je zadaná operace a výsledná hodnota `result` , platí `op` pro pravidlo `target` if `result` `One` . `Zero`V případě, že se nic nestane s `target` .
Přípona `A` označuje, že operace, která se má použít, je sousední.

## <a name="input"></a>Vstup

### <a name="result--__invalidresult__"></a>výsledek: __neplatné <Result>__

Výsledek měření, který určuje, zda je použita možnost op nebo ne.


### <a name="op--t--unit--is-adj"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Operace, která se má podmíněně použít


### <a name="target--t"></a>cíl: t

Vstup, na který se operace používá



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která se má podmíněně použít.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyIfOneC. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [Microsoft. proApplyIfOneA. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [Microsoft. proApplyIfOneCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)