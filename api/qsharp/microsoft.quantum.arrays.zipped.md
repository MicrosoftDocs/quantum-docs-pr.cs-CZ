---
uid: Microsoft.Quantum.Arrays.Zipped
title: Funkce zip
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 5177ab0ade5a9ad7788e60c1028befb84b0191d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845333"
---
# <a name="zipped-function"></a>Funkce zip

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zadaná dvě pole, vrátí nové pole párů tak, aby každá dvojice obsahovala element z každého původního pole.

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a>Vstup

### <a name="left--t"></a>Left: t []

Pole obsahující hodnoty pro první prvek řazené kolekce členů.


### <a name="right--u"></a>Right: ' U []

Pole obsahující hodnoty pro druhý prvek každé řazené kolekce členů.



## <a name="output--tu"></a>Výstup: (ne, ' U) []

Pole obsahující páry formuláře `(left[idx], right[idx])` pro každý `idx` . Pokud tato dvě pole nemají stejnou délku, výstup bude až na kratší dobu.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ levého prvku pole.
### <a name="u"></a>U

Typ pravého pole prvků.

## <a name="example"></a>Příklad

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zipped(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a>Viz také

- [Microsoft.Quantum.Arrays.Zipped3](xref:Microsoft.Quantum.Arrays.Zipped3)
- [Microsoft.Quantum.Arrays.Zipped4](xref:Microsoft.Quantum.Arrays.Zipped4)
- [Microsoft. Forms. Arrays. Unzip](xref:Microsoft.Quantum.Arrays.Unzipped)