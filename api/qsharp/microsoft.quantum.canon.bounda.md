---
uid: Microsoft.Quantum.Canon.BoundA
title: Bounda funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 40c112d0572dc4eebfc284c9ef29f43706e20c64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704465"
---
# <a name="bounda-function"></a>Bounda funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Vzhledem k poli operací, které fungují na jednom vstupu, vytvoří nová operace, která provede každou danou operaci v pořadí.
Modifikátor `A` označuje, že všechny operace v poli jsou sousední.

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a>Vstup

### <a name="operations--t--unit-adj"></a>operace: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ []

Posloupnost operací, které mají být provedeny na daném vstupu.



## <a name="output--t--unit-adj"></a>Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ

Nová operace, která každou danou operaci provede v pořadí podle jeho vstupu.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Cíl, na kterém každá z operací v poli působí.

## <a name="see-also"></a>Viz také

- [Microsoft. prodoby. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)