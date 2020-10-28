---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 7cfd77b0bb2d91c5a1c4bb5bc84e052421d733a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704193"
---
# <a name="delayedc-function"></a>DelayedC – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Vrátí operaci, která aplikuje danou operaci s daným argumentem.

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a>Vstup

### <a name="op--t--unit-ctl"></a>op: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL

Operace, která se má použít v důsledku použití návratové hodnoty


### <a name="arg--t"></a>ARG: t

Vstup, na který se operace `op` používá



## <a name="output--unit--unit-ctl"></a>Výstup: [jednotky](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL v jednotce

Nová operace, která se vztahuje na `op` vstup `arg`

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která se má zpozdit

## <a name="see-also"></a>Viz také

- [Microsoft. prodoby. Canon. zpoždění](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft... Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)