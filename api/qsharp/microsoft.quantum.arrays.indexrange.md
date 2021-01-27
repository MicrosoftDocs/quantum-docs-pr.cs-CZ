---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845783"
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

## <a name="example"></a>Příklad

Následující `for` smyčky jsou ekvivalentní:

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```