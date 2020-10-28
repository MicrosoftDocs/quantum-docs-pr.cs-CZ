---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Funkce unzip
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 37c960dc5dbdb8099fbebe1ad63cb44ce642733c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705721"
---
# <a name="unzipped-function"></a>Funkce unzip

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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

## <a name="see-also"></a>Viz také

- [Microsoft.Quantum.Arrays.Zipped](xref:Microsoft.Quantum.Arrays.Zipped)