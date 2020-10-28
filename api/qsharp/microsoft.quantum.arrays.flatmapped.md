---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: 3e75c7703471a2986812df660c2f9328f1536d22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706032"
---
# <a name="flatmapped-function"></a>FlatMapped – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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