---
uid: Microsoft.Quantum.Arrays.Unique
title: Unique – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: 7964d5d41eb68cb05f9414164d69496c1f76eb08
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220004"
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

## <a name="remarks"></a>Poznámky

Pokud existuje více prvků, které jsou stejné, ale nejsou vedle sebe, bude ve výstupním poli více výskytů.  Tuto funkci lze použít společně s `Sorted` k získání pole s celkovými jedinečnými prvky.