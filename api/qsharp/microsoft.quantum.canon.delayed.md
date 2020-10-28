---
uid: Microsoft.Quantum.Canon.Delayed
title: Opožděná funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 820a38c2b4de2e0151d55bd88fb4f69567182f6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704217"
---
# <a name="delayed-function"></a>Opožděná funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


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