---
uid: Microsoft.Quantum.Arrays.Unique
title: Unique – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: b3aa03d20195bdd8bb64783a9b68cafac29e68f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850909"
---
# <a name="unique-function"></a>Unique – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí nové pole, které nemá stejné sousedící prvky.

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a>Popis

V případě určitého pole prvků a funkce pro otestování rovnosti vrátí tato funkce nové pole, ve kterém je zachováno relativní pořadí prvků, ale všechny sousední prvky, které jsou stejné, jsou filtrovány pouze na jeden prvek.

## <a name="input"></a>Vstup

### <a name="equal--tt---bool"></a>EQUAL: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funkce, která porovnává dva prvky, jako jsou `a` považovány za, `b` Pokud `equal(a, b)` je `true` .


### <a name="array--t"></a>Array: t []

Pole, které má být filtrováno pro jedinečné prvky.



## <a name="output--t"></a>Výstup: t []

Pole, které nemá stejné sousedící prvky.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ každého prvku `array` .

## <a name="example"></a>Příklad

```qsharp
let unique1 = Unique(EqualI, [1, 1, 3, 3, 2, 5, 5, 5, 7]);
// same as [1, 3, 2, 5, 7]
let unique2 = Unique(EqualI, [2, 2, 1, 1, 2, 2, 1, 1]);
// same as [2, 1, 2, 1];
let unique3 = Unique(EqualI, Sorted(LessThanOrEqualI, [2, 2, 1, 1, 2, 2, 1, 1]));
// same as [1, 2];
```

## <a name="remarks"></a>Poznámky

Pokud existuje více prvků, které jsou stejné, ale nejsou vedle sebe, bude ve výstupním poli více výskytů.  Tuto funkci lze použít společně s `Sorted` k získání pole s celkovými jedinečnými prvky.