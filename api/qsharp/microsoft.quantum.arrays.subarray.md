---
uid: Microsoft.Quantum.Arrays.Subarray
title: Subarray – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: be7b6ee1a396d67ebc311d8d97f4bd751a32d171
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705760"
---
# <a name="subarray-function"></a>Subarray – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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