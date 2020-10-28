---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705961"
---
# <a name="indexrange-function"></a>IndexRange – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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