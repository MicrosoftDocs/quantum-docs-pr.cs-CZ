---
uid: Microsoft.Quantum.Canon.DelayC
title: Operace DelayC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayC
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: acb817c3322063353dc08c5d6f8c539391b3bf39
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704240"
---
# <a name="delayc-operation"></a>Operace DelayC

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje danou operaci na zpoždění.

```qsharp
operation DelayC<'T> (op : ('T => Unit is Ctl), arg : 'T, aux : Unit) : Unit
```


## <a name="description"></a>Popis

Po předané operaci a vstupu k této operaci se operace aplikuje, jakmile bude poskytnut další vstup.
Konkrétně výraz `Delay(op, arg, _)` je operace, která se vztahuje `op` na `arg` při volání metody.
Výraz `Delay(op,arg,_)` umožňuje zpožděnou aplikaci `op` .

## <a name="input"></a>Vstup

### <a name="op--t--unit-ctl"></a>op: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL

Operace, která se má použít.


### <a name="arg--t"></a>ARG: t

Vstup, na který se operace používá


### <a name="aux--unit"></a>AUX: [jednotka](xref:microsoft.quantum.lang-ref.unit)

Argument použitý ke zpoždění použití operace pomocí částečné aplikace



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která se má zpozdit

## <a name="see-also"></a>Viz také

- [Microsoft... Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)
- [Microsoft. prodoby. Canon. zpoždění](xref:Microsoft.Quantum.Canon.Delayed)