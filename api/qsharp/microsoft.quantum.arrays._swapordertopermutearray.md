---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 9df2ec00d91c1124fae960efd15d576b15b0223c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221704"
---
# <a name="_swapordertopermutearray-function"></a>_SwapOrderToPermuteArray funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí prvky Order v poli musí být zaměněny, aby vytvořilo seřazené pole.
Předpokládá, že probíhají zahození.

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a>Vstup

### <a name="neworder--int"></a>newOrder: [int](xref:microsoft.quantum.lang-ref.int)[]

Pole s permutací indexů nového pole. Mělo by se jednat o $n $ prvky, přičemž každý z nich bude mít jedinečné celé číslo od $0 $ do $n-$1.



## <a name="output--intint"></a>Výstup: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

Řazená kolekce členů představuje dva indexy, které se mají prohodit. Zahození začíná na nejnižším indexu.

## <a name="remarks"></a>Poznámky

## <a name="psuedocode"></a>Psuedocode

for (Indexing 0.. Length (newOrder)-1) {while [index]! = index {Switch newOrder [index] with newOrder [newOrder [index]]}}