---
uid: Microsoft.Quantum.Arrays.Zipped3
title: Zipped3 – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped3
qsharp.summary: Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: 6a4ffaeff8e6248a708ab9f8f9a6ff0c2e9e08d1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842178"
---
# <a name="zipped3-function"></a>Zipped3 – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zadaná tři pole vrací nové pole tří řazených kolekcí členů, aby každá 3-řazená kolekce členů obsahovala element z každého původního pole.

```qsharp
function Zipped3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a>Vstup

### <a name="first--t1"></a>First: t 1 []

Pole obsahující hodnoty pro první prvek řazené kolekce členů.


### <a name="second--t2"></a>sekundy: t 2 []

Pole obsahující hodnoty pro druhý prvek každé řazené kolekce členů.


### <a name="third--t3"></a>třetí: t 3 []

Pole obsahující hodnoty třetího prvku každé řazené kolekce členů.



## <a name="output--t1t2t3"></a>Výstup: (ne 1, t 2, t 3) []

Pole obsahující 3 – řazené kolekce členů formuláře `(first[idx], second[idx], third[idx])` pro každý `idx` . Pokud se tři pole neshodují, bude výstup, který je kratší než tento počet vstupů.

## <a name="type-parameters"></a>Parametry typu

### <a name="t1"></a>Ne 1

Typ prvních prvků pole.
### <a name="t2"></a>Ne 2

Typ druhých prvků pole.
### <a name="t3"></a>Ne 3

Typ elementů třetího pole.

## <a name="see-also"></a>Viz také

- [Microsoft.Quantum.Arrays.Zipped](xref:Microsoft.Quantum.Arrays.Zipped)
- [Microsoft.Quantum.Arrays.Zipped4](xref:Microsoft.Quantum.Arrays.Zipped4)