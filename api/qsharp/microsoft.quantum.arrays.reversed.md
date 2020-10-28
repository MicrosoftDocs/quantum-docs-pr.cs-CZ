---
uid: Microsoft.Quantum.Arrays.Reversed
title: Obrácená funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 99244195e581dc00db24b938f5aa1c541cd4433a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705801"
---
# <a name="reversed-function"></a>Obrácená funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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