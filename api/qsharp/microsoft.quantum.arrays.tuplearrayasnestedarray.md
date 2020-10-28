---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 917f35db949790ab3ae6e7a2184bcfcf5ed50be6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705736"
---
# <a name="tuplearrayasnestedarray-function"></a>TupleArrayAsNestedArray – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


Zapíná seznam dvou řazených kolekcí členů do vnořeného pole.

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a>Vstup

### <a name="tuplelist--tt"></a>tupleList: (t, t) []

Seznam dvou-řazených kolekcí členů, které mají být zaměněny do vnořeného pole.



## <a name="output--t"></a>Výstup: t [] []

Vnořené pole s délkou, která odpovídá tupleList.

## <a name="example"></a>Příklad

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

