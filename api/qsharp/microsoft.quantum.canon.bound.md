---
uid: Microsoft.Quantum.Canon.Bound
title: Vázaná funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 041f654c14f6e926d60038fee698b2b829fab8b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841051"
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

## <a name="example"></a>Příklad

Následují ekvivalenty:

```qsharp
let bound = Bound([U, V]);
bound(x);
```

a

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Viz také

- [Microsoft. proBoundC. Canon.](xref:Microsoft.Quantum.Canon.BoundC)
- [Microsoft. prodoby. Canon. Bound.](xref:Microsoft.Quantum.Canon.BoundA)
- [Microsoft. proBoundCA. Canon.](xref:Microsoft.Quantum.Canon.BoundCA)