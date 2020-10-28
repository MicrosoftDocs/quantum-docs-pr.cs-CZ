---
uid: Microsoft.Quantum.Arrays.Zipped
title: Funkce zip
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 67170fa005675f0e5d788c9c3b350fb9a961a597
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705672"
---
# <a name="zipped-function"></a>Funkce zip

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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

## <a name="see-also"></a>Viz také

- [Microsoft.Quantum.Arrays.Zipped3](xref:Microsoft.Quantum.Arrays.Zipped3)
- [Microsoft.Quantum.Arrays.Zipped4](xref:Microsoft.Quantum.Arrays.Zipped4)
- [Microsoft. Forms. Arrays. Unzip](xref:Microsoft.Quantum.Arrays.Unzipped)