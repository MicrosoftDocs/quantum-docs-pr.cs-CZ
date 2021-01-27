---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: c082e0a917343c18e5f511f065b2e78f1e217ecc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848546"
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