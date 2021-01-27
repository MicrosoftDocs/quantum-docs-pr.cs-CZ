---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 584cabcb7b6059ae5d311f13f5f75bd1f87bdba5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845671"
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

## <a name="example"></a>Příklad

Následující dva řádky jsou ekvivalentní:

```qsharp
let arr = MapIndex(f, [x0, x1, x2]);
```

a

```qsharp
let arr = [f(0, x0), f(1, x1), f(2, x2)];
```

## <a name="see-also"></a>Viz také

- [Microsoft. Forms. Arrays. mapované](xref:Microsoft.Quantum.Arrays.Mapped)