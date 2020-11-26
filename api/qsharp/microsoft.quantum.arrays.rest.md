---
uid: Microsoft.Quantum.Arrays.Rest
title: REST – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: 4dd10b6e8839fd906ca9c2e36c89c626d5772149
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220383"
---
# <a name="rest-function"></a>REST – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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