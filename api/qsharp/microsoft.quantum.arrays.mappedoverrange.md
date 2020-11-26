---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: b1d73c2503e63ed09a3d6a56421760ca29eb0c3f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220684"
---
# <a name="mappedoverrange-function"></a>MappedOverRange – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Pro rozsah a funkci, která přijímá jako vstup celé číslo, vrátí nové pole, které se skládá z obrázků hodnot rozsahu pod funkcí.

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a>Vstup

### <a name="mapper--int---t"></a>Mapovač: [int](xref:microsoft.quantum.lang-ref.int) -> 't

Funkce z `Int` `'T` , která se používá k mapování hodnot rozsahu.


### <a name="range--range"></a>Rozsah: [Rozsah](xref:microsoft.quantum.lang-ref.range)

Rozsah celých čísel.



## <a name="output--t"></a>Výstup: t []

Pole `'T[]` prvků, které jsou mapovány `mapper` funkcí.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ výsledku `mapper` funkce

## <a name="remarks"></a>Poznámky

Funkce je definována pro obecné typy, tj. kdykoli máme funkci, `mapper: Int -> 'T` můžeme namapovat hodnoty rozsahu a vytvořit pole typu `'T[]` .

## <a name="see-also"></a>Viz také

- [Microsoft. Forms. Arrays. mapované](xref:Microsoft.Quantum.Arrays.Mapped)