---
uid: Microsoft.Quantum.Arrays.Mapped
title: Mapovaná funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 1abb9d6fb1a921b49554bef968442f4f2b346b71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705913"
---
# <a name="mapped-function"></a>Mapovaná funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


Předané pole a funkce, které jsou definovány pro prvky pole, vrátí nové pole, které se skládá z obrázků původního pole pod funkcí.

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Vstup

### <a name="mapper--t---u"></a>Mapper: t-> ' U

Funkce z `'T` `'U` , která se používá k mapování prvků.


### <a name="array--t"></a>Array: t []

Pole prvků nad `'T` .



## <a name="output--u"></a>Výstup: U []

Pole `'U[]` prvků, které jsou mapovány `mapper` funkcí.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ `array` prvků.
### <a name="u"></a>U

Typ výsledku `mapper` funkce

## <a name="remarks"></a>Poznámky

Funkce je definována pro obecné typy, tj., kdykoli máme pole `'T[]` a funkci, `mapper: 'T -> 'U` můžeme namapovat prvky pole a vytvořit nové pole typu `'U[]` .