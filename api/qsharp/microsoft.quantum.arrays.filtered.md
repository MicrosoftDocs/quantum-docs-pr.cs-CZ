---
uid: Microsoft.Quantum.Arrays.Filtered
title: Filtrovaná funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 83336b7001ce1d8ab1f5340b194abdcf93588c31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847166"
---
# <a name="filtered-function"></a>Filtrovaná funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Předané pole a predikát, který je definován pro prvky pole, vrátí pole, které se skládá z prvků, které odpovídají predikátu.

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a>Vstup

### <a name="predicate--t---bool"></a>predikát: t-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funkce z `'T` na logickou hodnotu, která slouží k filtrování prvků.


### <a name="array--t"></a>Array: t []

Pole prvků nad `'T` .



## <a name="output--t"></a>Výstup: t []

Pole `'T[]` prvků, které odpovídají predikátu.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ `array` prvků.

## <a name="example"></a>Příklad

Následující kód demonstruje funkci "Filtered".
Predikát je definován pomocí @"microsoft.quantum.logical.greaterthani" funkce:

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function FilteredDemo() : Unit {
   let predicate = GreaterThanI(_, 5);
   let filteredArray = Filtered(predicate, [2, 5, 9, 1, 8]);
   Message($"{filteredArray}");
}
```

Výsledek, který by měl být z tohoto příkladu očekáván, bude pole čísel větší než 5.

## <a name="remarks"></a>Poznámky

Funkce je definována pro obecné typy, tj., kdykoli máme pole `'T[]` a predikát `'T -> Bool` můžeme filtrovat prvky.