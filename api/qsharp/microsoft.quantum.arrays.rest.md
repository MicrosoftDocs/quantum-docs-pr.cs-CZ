---
uid: Microsoft.Quantum.Arrays.Rest
title: REST – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: c14e4b2902741d7ea70c895aa715cbcaa849af3e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705808"
---
# <a name="rest-function"></a>REST – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


Vytvoří pole, které je rovno vstupnímu poli s výjimkou toho, že první prvek pole je vyřazen.

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Vstup

### <a name="array--t"></a>Array: t []

Pole, jehož druhý k poslednímu prvku, je vytvoření výstupního pole.



## <a name="output--t"></a>Výstup: t []

Pole obsahující prvky `array[1..Length(array) - 1]` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ prvků pole.