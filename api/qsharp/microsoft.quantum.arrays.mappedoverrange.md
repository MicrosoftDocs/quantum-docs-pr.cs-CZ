---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: 7093043e2a290e6132774b8fe154d3627a254f27
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845641"
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

## <a name="example"></a>Příklad

Tento příklad přidá 1 do rozsahu sudých čísel:

```qsharp
let numbers = MappedOverRange(PlusI(1, _), 0..2..10);
// numbers = [1, 3, 5, 7, 9, 11]
```

## <a name="remarks"></a>Poznámky

Funkce je definována pro obecné typy, tj. kdykoli máme funkci, `mapper: Int -> 'T` můžeme namapovat hodnoty rozsahu a vytvořit pole typu `'T[]` .

## <a name="see-also"></a>Viz také

- [Microsoft. Forms. Arrays. mapované](xref:Microsoft.Quantum.Arrays.Mapped)