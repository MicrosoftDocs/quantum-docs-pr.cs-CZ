---
uid: Microsoft.Quantum.Arrays.Most
title: Většina funkcí
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 2b212b38ec55f3798eb9397f03b842573173eb88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845580"
---
# <a name="most-function"></a>Většina funkcí

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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