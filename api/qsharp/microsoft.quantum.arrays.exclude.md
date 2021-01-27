---
uid: Microsoft.Quantum.Arrays.Exclude
title: Funkce Exclude
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 76cdee56e84951c63e80babfdca6a3de33583cab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848676"
---
# <a name="exclude-function"></a>Funkce Exclude

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí pole obsahující prvky jiného pole, kromě prvků v daném seznamu indexů.

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>Vstup

### <a name="remove--int"></a>Remove: [int](xref:microsoft.quantum.lang-ref.int)[]

Pole indexů označuje, které prvky by měly být vyloučeny z výstupu.


### <a name="array--t"></a>Array: t []

Pole, ze kterého jsou pořízeny hodnoty ve výstupním poli.



## <a name="output--t"></a>Výstup: t []

Pole `output` , jako `output[0]` je první prvek, `array` jehož index se nezobrazuje v `remove` , jako `output[1]` je například druhý takový prvek a tak dále.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ prvků pole.

## <a name="example"></a>Příklad

```qsharp
let array = [10, 11, 12, 13, 14, 15];
// The following line returns [10, 12, 15].
let subarray = Exclude([1, 3, 4], array);
```