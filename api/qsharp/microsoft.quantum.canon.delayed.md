---
uid: Microsoft.Quantum.Canon.Delayed
title: Opožděná funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 40fcc7d0a178fdb18437b4d6c96542db593347b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840589"
---
# <a name="delayed-function"></a>Opožděná funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí operaci, která aplikuje danou operaci s daným argumentem.

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a>Vstup

### <a name="op--t--u"></a>op: t => ' U 

Operace, která se má použít.


### <a name="arg--t"></a>ARG: t

Vstup, na který se operace používá



## <a name="output--unit--u"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit) => ' U 

Nová operace, která se vztahuje na `op` vstup `arg`

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která se má zpozdit
### <a name="u"></a>U

Návratový typ operace, která se má zpozdit.

## <a name="see-also"></a>Viz také

- [Microsoft. proDelayedC. Canon.](xref:Microsoft.Quantum.Canon.DelayedC)
- [Microsoft. prodoby. Canon. zpoždění](xref:Microsoft.Quantum.Canon.DelayedA)
- [Microsoft. proDelayedCA. Canon.](xref:Microsoft.Quantum.Canon.DelayedCA)
- [Microsoft... Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)