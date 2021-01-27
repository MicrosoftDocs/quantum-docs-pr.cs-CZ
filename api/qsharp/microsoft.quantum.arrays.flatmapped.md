---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: bee7002c5a1e80cee7907ff9cb4ebaaedf8e9923
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848646"
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

## <a name="example"></a>Příklad

```qsharp
let Numbers = SequenceI(1, _); // generates numbers starting from 1
let values = FlatMapped(Numbers, [1, 2, 3]);
// values = [1, 1, 2, 1, 2, 3]
```