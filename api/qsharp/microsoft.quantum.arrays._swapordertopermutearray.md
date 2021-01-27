---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: ff8e4e23dde7d69f93054a275548ded49d5b0bfb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846299"
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

## <a name="example"></a>Příklad

```qsharp
// The following returns [(0, 5),(0, 4),(0, 1),(0, 3)];
let swapOrder = _SwapOrderToPermuteArray([5, 3, 2, 0, 1, 4]);
```

## <a name="remarks"></a>Poznámky

## <a name="psuedocode"></a>Psuedocode

for (Indexing 0.. Length (newOrder)-1) {while [index]! = index {Switch newOrder [index] with newOrder [newOrder [index]]}}