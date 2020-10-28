---
uid: Microsoft.Quantum.Arrays.Sorted
title: Seřazená funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: 14ac5325b81aec4ba0bf94a83cf00e086a075a7c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705785"
---
# <a name="sorted-function"></a>Seřazená funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


Předanému poli vrátí prvky tohoto pole seřazené podle dané funkce porovnání.

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a>Vstup

### <a name="comparison--tt---bool"></a>porovnání: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funkce, která porovná dva prvky, například, že jsou `a` považovány za menší nebo rovny, `b` Pokud `comparison(a, b)` je `true` .


### <a name="array--t"></a>Array: t []

Pole, které má být seřazeno.



## <a name="output--t"></a>Výstup: t []



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ každého prvku `array` .

## <a name="remarks"></a>Poznámky

Tato funkce `comparison` je považována za přenositelný, takže pokud `comparison(a, b)` a `comparison(b, c)` , pak `comparison(a, c)` se předpokládá. Pokud tato vlastnost není uložena, bude výstup této funkce pravděpodobně nesprávný.

Vzhledem k tomu, že je to funkce, jsou výsledky zcela deterministickáy i v případě, že se dva prvky považují za stejné jako v rámci `comparison` `comparison(a, b)` a `comparison(b, a)` `true` .
Konkrétně je zaručeno, že řazení prováděné touto funkcí je stabilní, aby v případě, že dva prvky `a` a `b` výskyty v tomto pořadí v `array` a jsou považovány za stejné `comparison` , pak se `a` zobrazí také před `b` ve výstupu.

Příklad:

```Q#
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```