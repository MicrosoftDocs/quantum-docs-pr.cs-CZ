---
uid: Microsoft.Quantum.Arrays.Most
title: Většina funkcí
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: ca89041a4e70472e9bf7a63ffcacccb35aad527c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705864"
---
# <a name="most-function"></a>Většina funkcí

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


Vytvoří pole, které se rovná vstupnímu poli s tím rozdílem, že poslední prvek pole je vyřazen.

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Vstup

### <a name="array--t"></a>Array: t []

Pole, jehož první až poslední prvky mají tvořit výstupní pole.



## <a name="output--t"></a>Výstup: t []

Pole obsahující prvky `array[0..Length(array) - 2]` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ prvků pole.