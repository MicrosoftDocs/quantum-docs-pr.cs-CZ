---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 9af4ba48a21d3cdf932b2f702051a70a6108db1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705984"
---
# <a name="headandrest-function"></a>HeadAndRest – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


Vrátí řazenou kolekci členů prvního a všech zbývajících prvků pole.

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a>Vstup

### <a name="array--a"></a>pole: ' A []

Pole s alespoň jedním prvkem.



## <a name="output--aa"></a>Výstup: (' A, ' A [])

Řazená kolekce členů prvního a všech zbývajících prvků pole.

## <a name="type-parameters"></a>Parametry typu

### <a name="a"></a>A

Typ prvků pole.