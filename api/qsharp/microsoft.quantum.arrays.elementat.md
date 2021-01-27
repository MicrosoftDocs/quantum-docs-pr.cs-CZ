---
uid: Microsoft.Quantum.Arrays.ElementAt
title: ElementAt – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementAt
qsharp.summary: Returns the at the given index of an array.
ms.openlocfilehash: 2d31c62a4a5ba3b273e7440b5dfe4482b47e3a8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842807"
---
# <a name="elementat-function"></a>ElementAt – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí hodnotu v daném indexu pole.

```qsharp
function ElementAt<'T> (index : Int, array : 'T[]) : 'T
```


## <a name="input"></a>Vstup

### <a name="index--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)

Index elementu


### <a name="array--t"></a>Array: t []

Pole, které se indexuje.



## <a name="output--t"></a>Výstup: 'T



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ každého prvku `array` .

## <a name="example"></a>Příklad

Získá třetí číslo ve čtyřech slavných celočíselných sekvencích. (Všimněte si, že index 0 odpovídá _první_ hodnotě sekvence.)

```qsharp
let lucas = [2, 1, 3, 4, 7, 11, 18, 29, 47, 76];
let prime = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29];
let fibonacci = [0, 1, 1, 2, 3, 5, 8, 13, 21, 34];
let catalan = [1, 1, 2, 5, 14, 42, 132, 429, 1430, 4862];
let famous2 = Mapped(ElementAt<Int>(2, _), [lucas, prime, fibonacci, catalan]);
// same as: famous2 = [3, 5, 1, 2]
```

## <a name="see-also"></a>Viz také

- [Microsoft. Forms. Arrays. LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)
- [Microsoft. Forms. Arrays. ElementsAt](xref:Microsoft.Quantum.Arrays.ElementsAt)