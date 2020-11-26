---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Funkce unzip
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: aee1d48c9e0a1f104040bc56c78fdbb8bc4d34ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219953"
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

## <a name="see-also"></a>Viz také

- [Microsoft.Quantum.Arrays.Zipped](xref:Microsoft.Quantum.Arrays.Zipped)