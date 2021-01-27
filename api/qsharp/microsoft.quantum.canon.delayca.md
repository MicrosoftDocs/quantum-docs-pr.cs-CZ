---
uid: Microsoft.Quantum.Canon.DelayCA
title: Operace DelayCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayCA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: a8606cde976882bba0eb23467932b9ee0ed36696
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840617"
---
# <a name="delayca-operation"></a>Operace DelayCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje danou operaci na zpoždění.

```qsharp
operation DelayCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T, aux : Unit) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Po předané operaci a vstupu k této operaci se operace aplikuje, jakmile bude poskytnut další vstup.
Konkrétně výraz `Delay(op, arg, _)` je operace, která se vztahuje `op` na `arg` při volání metody.
Výraz `Delay(op,arg,_)` umožňuje zpožděnou aplikaci `op` .

## <a name="input"></a>Vstup

### <a name="op--t--unit--is-adj--ctl"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

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