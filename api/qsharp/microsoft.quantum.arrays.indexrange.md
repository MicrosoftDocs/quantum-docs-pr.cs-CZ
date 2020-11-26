---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 5afd4cc260ac3e384d2736bf7b43d941afd9ef73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220939"
---
# <a name="indexrange-function"></a>IndexRange – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


V poli, vrátí rozsah v rámci indexů tohoto pole, který je vhodný pro použití ve smyčce for.

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a>Vstup

### <a name="array--telement"></a>Array: ' TElement []

Pole, pro které by měl být vrácen rozsah indexů.



## <a name="output--range"></a>Výstup: [Rozsah](xref:microsoft.quantum.lang-ref.range)

Rozsah ve všech indexech pole.

## <a name="type-parameters"></a>Parametry typu

### <a name="telement"></a>'TElement

Typ prvků pole.