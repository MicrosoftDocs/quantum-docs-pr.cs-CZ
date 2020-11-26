---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: db20795719d11138cbdc5a38c0a19d0f247af059
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220769"
---
# <a name="lookupfunction-function"></a>LookupFunction – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Předanému poli vrátí funkci, která vrátí prvky daného pole.

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a>Vstup

### <a name="array--t"></a>Array: t []

Pole, které má být reprezentováno jako vyhledávací funkce.



## <a name="output--int---t"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int) -> 't

Funkce `f` , například `f(idx) == f[idx]` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ prvků pole reprezentovaných jako vyhledávací funkce.

## <a name="remarks"></a>Poznámky

Tato funkce je hlavně užitečná pro spolupráci s funkcemi a operacemi, které `Int -> 'T` jako argumenty přijímají funkce. To je běžné, například v knihovně reprezentace generátoru, kde jsou funkce použity pro zamezení nutnosti zaznamenat celé pole v paměti.