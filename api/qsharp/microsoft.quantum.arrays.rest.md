---
uid: Microsoft.Quantum.Arrays.Rest
title: REST – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: b6c579df354185a2defb08cd78bce816d8cc5959
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845478"
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