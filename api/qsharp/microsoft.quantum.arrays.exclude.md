---
uid: Microsoft.Quantum.Arrays.Exclude
title: Funkce Exclude
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: e1fa7e728d4846db90872055454a8182a77a518b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706049"
---
# <a name="exclude-function"></a>Funkce Exclude

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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