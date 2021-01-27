---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: 22b56bb7e9f03ebc5b2225efb2e6450d56022664
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845702"
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