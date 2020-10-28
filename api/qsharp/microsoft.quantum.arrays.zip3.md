---
uid: Microsoft.Quantum.Arrays.Zip3
title: Zip3 – – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: f4b1a769614ee9434b2141b8fcb91f34cd071bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705680"
---
# <a name="zip3-function"></a>Zip3 – – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


> [!WARNING]
> Zip3 – se už nepoužívá. <xref:Microsoft.Quantum.Arrays.Zipped3>Místo toho ho použijte.

Zadaná tři pole vrací nové pole tří řazených kolekcí členů, aby každá 3-řazená kolekce členů obsahovala element z každého původního pole.

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
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

- [Microsoft.Quantum.Arrays.Zip](xref:Microsoft.Quantum.Arrays.Zip)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)