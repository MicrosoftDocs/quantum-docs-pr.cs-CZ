---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: a1f2582668131816b774bf4a8b7476d9f1ee8cad
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840563"
---
# <a name="delayedc-function"></a>DelayedC – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí operaci, která aplikuje danou operaci s daným argumentem.

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a>Vstup

### <a name="op--t--unit--is-ctl"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL

Operace, která se má použít v důsledku použití návratové hodnoty


### <a name="arg--t"></a>ARG: t

Vstup, na který se operace `op` používá



## <a name="output--unit--unit--is-ctl"></a>Výstup: [jednotka jednotky](xref:microsoft.quantum.lang-ref.unit) => [](xref:microsoft.quantum.lang-ref.unit) je CTL

Nová operace, která se vztahuje na `op` vstup `arg`

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která se má zpozdit

## <a name="see-also"></a>Viz také

- [Microsoft. prodoby. Canon. zpoždění](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft... Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)