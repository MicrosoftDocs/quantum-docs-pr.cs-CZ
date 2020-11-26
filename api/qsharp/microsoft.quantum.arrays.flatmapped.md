---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: e851e8503b3afcb4572f09fe39079247518c22c4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221245"
---
# <a name="flatmapped-function"></a>FlatMapped – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Pro pole a funkci, která mapuje prvek pole na některé výstupní pole, vrátí zřetězená výstupní pole pro každý prvek pole.

```qsharp
function FlatMapped<'TInput, 'TOutput> (mapper : ('TInput -> 'TOutput[]), array : 'TInput[]) : 'TOutput[]
```


## <a name="input"></a>Vstup

### <a name="mapper--tinput---toutput"></a>Mapper: ' TInput-> ' TOutput []

Funkce z `'TInput` `'TOutput[]` , která se používá k mapování prvků pole.


### <a name="array--tinput"></a>Array: ' TInput []

Pole prvků.



## <a name="output--toutput"></a>Výstup: ' TOutput []

Pole, `'TOutput[]` které je zřetězením všech polí generovaných funkcí Mapping.

## <a name="type-parameters"></a>Parametry typu

### <a name="tinput"></a>'TInput

Typ `array` prvků.
### <a name="toutput"></a>'TOutput

`mapper`Funkce vrátí pole tohoto typu.