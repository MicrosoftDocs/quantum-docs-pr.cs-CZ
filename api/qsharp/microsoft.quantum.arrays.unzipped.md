---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Funkce unzip
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845372"
---
# <a name="unzipped-function"></a>Funkce unzip

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


V případě pole se dvěma řazenými kolekcemi členů vrátí řazenou kolekci členů dvou polí, z nichž každý obsahuje prvky pro vstupní pole.

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a>Vstup

### <a name="arr--tu"></a>Šipka: (t, ' U) []

Pole obsahující 2 – řazené kolekce členů



## <a name="output--tu"></a>Výstup: (ne [], ' U [])

Dvě pole, první obsahující všechny první prvky vstupních řazených kolekcí členů, druhý, který obsahuje všechny druhé prvky vstupních řazených kolekcí členů.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ prvního prvku v každé řazené kolekci členů
### <a name="u"></a>U

Typ druhého prvku v každé řazené kolekci členů

## <a name="example"></a>Příklad

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a>Viz také

- [Microsoft.Quantum.Arrays.Zipped](xref:Microsoft.Quantum.Arrays.Zipped)