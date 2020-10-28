---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Funkce výčtu
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 0a591025a4eef79e08b47527c0bdb556f5645334
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706065"
---
# <a name="enumerated-function"></a>Funkce výčtu

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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