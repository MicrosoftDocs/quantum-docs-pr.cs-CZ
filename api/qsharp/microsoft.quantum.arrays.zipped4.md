---
uid: Microsoft.Quantum.Arrays.Zipped4
title: Zipped4 – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped4
qsharp.summary: Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: e932cd4c266b39a3a88da48e649448d0028f61e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845316"
---
# <a name="zipped4-function"></a>Zipped4 – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


U čtyř polí vrátí nové pole se 4 řazenými kolekcemi členů tak, aby každá 4 řazená kolekce členů obsahovala element z každého původního pole.

```qsharp
function Zipped4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a>Vstup

### <a name="first--t1"></a>First: t 1 []

Pole obsahující hodnoty pro první prvek řazené kolekce členů.


### <a name="second--t2"></a>sekundy: t 2 []

Pole obsahující hodnoty pro druhý prvek každé řazené kolekce členů.


### <a name="third--t3"></a>třetí: t 3 []

Pole obsahující hodnoty třetího prvku každé řazené kolekce členů.


### <a name="fourth--t4"></a>čtvrté: t 4 []

Pole obsahující hodnoty pro čtvrtý prvek každé řazené kolekce členů.



## <a name="output--t1t2t3t4"></a>Výstup: (ne 1, t 2, t 3, t 4) []

Pole obsahující 4 – řazené kolekce členů formuláře `(first[idx], second[idx], third[idx], fourth[idx])` pro každý `idx` . Pokud se čtyři pole neshodují, bude výstup, který je kratší než tento počet vstupů.

## <a name="type-parameters"></a>Parametry typu

### <a name="t1"></a>Ne 1

Typ prvních prvků pole.
### <a name="t2"></a>Ne 2

Typ druhých prvků pole.
### <a name="t3"></a>Ne 3

Typ elementů třetího pole.
### <a name="t4"></a>NE4

Typ čtvrté prvky pole.

## <a name="see-also"></a>Viz také

- [Microsoft.Quantum.Arrays.Zipped](xref:Microsoft.Quantum.Arrays.Zipped)
- [Microsoft.Quantum.Arrays.Zipped3](xref:Microsoft.Quantum.Arrays.Zipped3)