---
uid: Microsoft.Quantum.Arrays.Subarray
title: Subarray – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: cf72f04421b277ce64354d1eccec11cbc61d78cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220157"
---
# <a name="subarray-function"></a>Subarray – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Převezme pole a seznam umístění a vytvoří nové pole vytvořené z prvků původního pole, které odpovídá zadaným umístěním.

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>Vstup

### <a name="indices--int"></a>indexy: [int](xref:microsoft.quantum.lang-ref.int)[]

Seznam celých čísel, která se používají k definování podpole.


### <a name="array--t"></a>Array: t []

Pole prvků nad `'T` .



## <a name="output--t"></a>Výstup: t []

Pole `out` prvků, jejichž indexy odpovídají podpoli, například `out[idx] == array[indices[idx]]` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ `array` prvků.

## <a name="remarks"></a>Poznámky

Funkce je definována pro obecné typy, tj., kdykoli máme pole `'T[]` a seznam umístění, které `Int[]` definují podpole.
Konstrukce podpole je založena na generování nové, hluboké kopie daného pole na rozdíl od udržování odkazů.

Pokud `Length(indices) < Length(array)` , tato funkce vrátí podmnožinu `array` . Na druhé straně, pokud `indices` obsahuje opakující se prvky, odpovídající prvky `array` se také opakují.
Pokud `indices` a `array` mají stejnou délku, tato funkce poskytuje permutace `array` .