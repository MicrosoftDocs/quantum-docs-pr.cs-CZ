---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 1144e00227df1cd7d96bc76b118b0b556adbaa96
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221075"
---
# <a name="headandrest-function"></a>HeadAndRest – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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