---
uid: Microsoft.Quantum.Arrays.Reversed
title: Obrácená funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 270f15c1d10b4397e258c750876095efc2b8e951
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220429"
---
# <a name="reversed-function"></a>Obrácená funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vytvoří pole, které obsahuje stejné prvky jako vstupní pole, ale v obráceném pořadí.

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Vstup

### <a name="array--t"></a>Array: t []

Pole, jehož prvky mají být zkopírovány v obráceném pořadí.



## <a name="output--t"></a>Výstup: t []

Pole obsahující prvky `array[Length(array) - 1]` .. `array[0]`.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ prvků pole.