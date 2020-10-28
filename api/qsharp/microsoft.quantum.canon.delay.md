---
uid: Microsoft.Quantum.Canon.Delay
title: Operace zpoždění
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: f9f0e5c3120eb69bd7431d52d6cde5e846ffbe4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704256"
---
# <a name="delay-operation"></a>Operace zpoždění

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje danou operaci na zpoždění.

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a>Popis

Po předané operaci a vstupu k této operaci se operace aplikuje, jakmile bude poskytnut další vstup.
Konkrétně výraz `Delay(op, arg, _)` je operace, která se vztahuje `op` na `arg` při volání metody.
Výraz `Delay(op,arg,_)` umožňuje zpožděnou aplikaci `op` .

## <a name="input"></a>Vstup

### <a name="op--t--u"></a>op: t => ' U 

Operace, která se má použít.


### <a name="arg--t"></a>ARG: t

Vstup, na který se operace používá


### <a name="aux--unit"></a>AUX: [jednotka](xref:microsoft.quantum.lang-ref.unit)

Argument použitý ke zpoždění použití operace pomocí částečné aplikace



## <a name="output--u"></a>Výstup: ' U



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která se má zpozdit
### <a name="u"></a>U

Návratový typ operace, která se má zpozdit.

## <a name="see-also"></a>Viz také

- [Microsoft. proDelayC. Canon.](xref:Microsoft.Quantum.Canon.DelayC)
- [Microsoft. nečinnosti. Canon. Delay](xref:Microsoft.Quantum.Canon.DelayA)
- [Microsoft. proDelayCA. Canon.](xref:Microsoft.Quantum.Canon.DelayCA)
- [Microsoft. prodoby. Canon. zpoždění](xref:Microsoft.Quantum.Canon.Delayed)