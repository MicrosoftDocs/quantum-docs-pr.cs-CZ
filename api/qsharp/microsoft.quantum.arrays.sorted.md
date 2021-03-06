---
uid: Microsoft.Quantum.Arrays.Sorted
title: Seřazená funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: cb8a1ef438d798c8201ed9f52677e253770df1d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845448"
---
# <a name="sorted-function"></a>Seřazená funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Příklad

Následující fragment kódu seřadí pole celých čísel, která se mají objevit ve vzestupném pořadí:

```qsharp
let sortedArray = Sorted(LessThanOrEqualI, [3, 17, 11, -201, -11]);
```

## <a name="remarks"></a>Poznámky

Tato funkce `comparison` je považována za přenositelný, takže pokud `comparison(a, b)` a `comparison(b, c)` , pak `comparison(a, c)` se předpokládá. Pokud tato vlastnost není uložena, bude výstup této funkce pravděpodobně nesprávný.

Vzhledem k tomu, že je to funkce, jsou výsledky zcela deterministickáy i v případě, že se dva prvky považují za stejné jako v rámci `comparison` `comparison(a, b)` a `comparison(b, a)` `true` .
Konkrétně je zaručeno, že řazení prováděné touto funkcí je stabilní, aby v případě, že dva prvky `a` a `b` výskyty v tomto pořadí v `array` a jsou považovány za stejné `comparison` , pak se `a` zobrazí také před `b` ve výstupu.

Příklad:

```qsharp
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