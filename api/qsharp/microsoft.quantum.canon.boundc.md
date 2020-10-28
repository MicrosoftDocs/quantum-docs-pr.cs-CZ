---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 04dca4ff317bf3cee053f7c3903112f4e05a3973
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704456"
---
# <a name="boundc-function"></a>BoundC – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Vzhledem k poli operací, které fungují na jednom vstupu, vytvoří nová operace, která provede každou danou operaci v pořadí.
Modifikátor `C` označuje, že všechny operace v poli jsou ovladatelné.

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a>Vstup

### <a name="operations--t--unit-ctl"></a>operace: t [=> CTL](xref:microsoft.quantum.lang-ref.unit) []

Posloupnost operací, které mají být provedeny na daném vstupu.



## <a name="output--t--unit-ctl"></a>Výstup: t => seznam CTL pro [jednotku](xref:microsoft.quantum.lang-ref.unit)

Nová operace, která každou danou operaci provede v pořadí podle jeho vstupu.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Cíl, na kterém každá z operací v poli působí.

## <a name="see-also"></a>Viz také

- [Microsoft. prodoby. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)