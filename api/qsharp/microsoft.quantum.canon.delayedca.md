---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 8ee55e2ca7ec2cff9618b5dc66e19d88779d39ce
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704200"
---
# <a name="delayedca-function"></a>DelayedCA – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Vrátí operaci, která aplikuje danou operaci s daným argumentem.

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a>Vstup

### <a name="op--t--unit-ctl--adj"></a>op: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL a ADJ

Operace, která se má použít v důsledku použití návratové hodnoty


### <a name="arg--t"></a>ARG: t

Vstup, na který se operace `op` používá



## <a name="output--unit--unit-ctl--adj"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL a ADJ

Nová operace, která se vztahuje na `op` vstup `arg`

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která se má zpozdit

## <a name="see-also"></a>Viz také

- [Microsoft. prodoby. Canon. zpoždění](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft... Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)