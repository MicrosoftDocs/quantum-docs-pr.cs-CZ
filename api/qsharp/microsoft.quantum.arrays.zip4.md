---
uid: Microsoft.Quantum.Arrays.Zip4
title: Zip4 – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip4
qsharp.summary: >-
  > [!WARNING]

  > Zip4 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.


  Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: d42b3b6db059163f6c766d4f133551be293c153d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705664"
---
# <a name="zip4-function"></a>Zip4 – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


> [!WARNING]
> Zip4 se už nepoužívá. <xref:Microsoft.Quantum.Arrays.Zipped4>Místo toho ho použijte.

U čtyř polí vrátí nové pole se 4 řazenými kolekcemi členů tak, aby každá 4 řazená kolekce členů obsahovala element z každého původního pole.

```qsharp
function Zip4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
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

- [Microsoft.Quantum.Arrays.Zip](xref:Microsoft.Quantum.Arrays.Zip)
- [Microsoft.Quantum.Arrays.Zip3](xref:Microsoft.Quantum.Arrays.Zip3)