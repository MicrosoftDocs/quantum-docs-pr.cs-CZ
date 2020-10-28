---
uid: Microsoft.Quantum.Canon.Bound
title: Vázaná funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 34ca2b79d0ee09bd3b5b5b3f0c0b20420d5b3882
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704473"
---
# <a name="bound-function"></a>Vázaná funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Vzhledem k poli operací, které fungují na jednom vstupu, vytvoří nová operace, která provede každou danou operaci v pořadí.

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a>Vstup

### <a name="operations--t--unit-"></a>operace: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) []

Posloupnost operací, které mají být provedeny na daném vstupu.



## <a name="output--t--unit"></a>Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Nová operace, která každou danou operaci provede v pořadí podle jeho vstupu.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Cíl, na kterém každá z operací v poli působí.

## <a name="see-also"></a>Viz také

- [Microsoft. proBoundC. Canon.](xref:Microsoft.Quantum.Canon.BoundC)
- [Microsoft. prodoby. Canon. Bound.](xref:Microsoft.Quantum.Canon.BoundA)
- [Microsoft. proBoundCA. Canon.](xref:Microsoft.Quantum.Canon.BoundCA)