---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 430495517974b641c249fa146aa9effec542e825
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209923"
---
# <a name="mappedbyindex-function"></a>MappedByIndex – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Pro pole a funkci, která je definována pro indexované prvky pole, vrátí nové pole, které se skládá z obrázků původního pole v rámci funkce.

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Vstup

### <a name="mapper--intt---u"></a>Mapper: ([int](xref:microsoft.quantum.lang-ref.int), t)-> ' U

Funkce z `(Int, 'T)` `'U` , která se používá k mapování prvků a jejich indexů.


### <a name="array--t"></a>Array: t []

Pole prvků nad `'T` .



## <a name="output--u"></a>Výstup: U []

Pole `'U[]` prvků, které jsou mapovány `mapper` funkcí.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ `array` prvků.
### <a name="u"></a>U

Typ výsledku `mapper` funkce

## <a name="see-also"></a>Viz také

- [Microsoft. Forms. Arrays. mapované](xref:Microsoft.Quantum.Arrays.Mapped)