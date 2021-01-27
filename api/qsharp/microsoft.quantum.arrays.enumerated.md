---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Funkce výčtu
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848127"
---
# <a name="enumerated-function"></a>Funkce výčtu

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


V případě pole, vrátí nové pole obsahující prvky původního pole spolu s indexy každého prvku.

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a>Vstup

### <a name="array--telement"></a>Array: ' TElement []

Pole, jehož prvky mají být vyčísleny.



## <a name="output--inttelement"></a>Výstup: ([int](xref:microsoft.quantum.lang-ref.int), ' TElement) []

Nové pole obsahující prvky původního pole spolu s jejich indexy.

## <a name="type-parameters"></a>Parametry typu

### <a name="telement"></a>'TElement

Typ prvků pole.

## <a name="example"></a>Příklad

Následující `for` smyčky jsou ekvivalentní:

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```