---
uid: Microsoft.Quantum.Arrays.Reversed
title: Obrácená funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 50699465711de45ff994095e6c098550d637d608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845461"
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