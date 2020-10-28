---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: d96d33781def10940479ba2eafdcc6711a0c05a5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704433"
---
# <a name="boundca-function"></a>BoundCA – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Vzhledem k poli operací, které fungují na jednom vstupu, vytvoří nová operace, která provede každou danou operaci v pořadí.
Modifikátor `CA` označuje, že všechny operace v poli jsou sousedící a ovladatelné.

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a>Vstup

### <a name="operations--t--unit-adj--ctl"></a>operace: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL []

Posloupnost operací, které mají být provedeny na daném vstupu.



## <a name="output--t--unit-adj--ctl"></a>Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Nová operace, která každou danou operaci provede v pořadí podle jeho vstupu.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Cíl, na kterém každá z operací v poli působí.

## <a name="see-also"></a>Viz také

- [Microsoft. prodoby. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)