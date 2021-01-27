---
uid: Microsoft.Quantum.Arrays.ElementsAt
title: ElementsAt – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementsAt
qsharp.summary: Returns the array's elements at a given range of indices.
ms.openlocfilehash: 295aa4e2d79857405186b835d9788f59db83d1c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842796"
---
# <a name="elementsat-function"></a>ElementsAt – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí prvky pole v zadaném rozsahu indexů.

```qsharp
function ElementsAt<'T> (range : Range, array : 'T[]) : 'T[]
```


## <a name="input"></a>Vstup

### <a name="range--range"></a>Rozsah: [Rozsah](xref:microsoft.quantum.lang-ref.range)

Rozsah indexů pole


### <a name="array--t"></a>Array: t []

Pole



## <a name="output--t"></a>Výstup: t []



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ každého prvku `array` .

## <a name="example"></a>Příklad

Získá liché indexy v slavných celočíselných sekvencích. (Všimněte si, že index 0 odpovídá _první_ hodnotě sekvence.)

```qsharp
let lucas = [2, 1, 3, 4, 7, 11, 18, 29, 47, 76];
let prime = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29];
let fibonacci = [0, 1, 1, 2, 3, 5, 8, 13, 21, 34];
let catalan = [1, 1, 2, 5, 14, 42, 132, 429, 1430, 4862];
let famousOdd = Mapped(ElementsAt<Int>(0..2..9, _), [lucas, prime, fibonacci, catalan]);
// same as: famousOdd = [[2, 3, 7, 18, 47], [2, 5, 11, 17, 23], [0, 1, 3, 8, 21], [1, 2, 14, 132, 1430]]
```

## <a name="see-also"></a>Viz také

- [Microsoft. Forms. Arrays. ElementAt](xref:Microsoft.Quantum.Arrays.ElementAt)
- [Microsoft. Forms. Arrays. LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)