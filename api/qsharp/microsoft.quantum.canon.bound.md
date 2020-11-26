---
uid: Microsoft.Quantum.Canon.Bound
title: Vázaná funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: c12ce37054ddde1b98778888e90916c6e4725814
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207594"
---
# <a name="bound-function"></a>Vázaná funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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