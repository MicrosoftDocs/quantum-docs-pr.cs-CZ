---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 965f2f3d4f8b366abb27287ce0d27a3b7d7b8fb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706192"
---
# <a name="_swapordertopermutearray-function"></a>_SwapOrderToPermuteArray funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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