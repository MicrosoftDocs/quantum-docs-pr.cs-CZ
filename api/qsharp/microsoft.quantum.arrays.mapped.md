---
uid: Microsoft.Quantum.Arrays.Mapped
title: Mapovaná funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 00ea0803faf6e8edfa748af63dd6c7e217b1de41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845674"
---
# <a name="mapped-function"></a>Mapovaná funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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