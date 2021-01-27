---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 8b3d230605cc756a5da01e45e47f91c5b8e9f541
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833304"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray – funkce

Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vytvoří binární reprezentaci nezáporného čísla s použitím reprezentace Little-endian pro vrácené pole.

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>Vstup

### <a name="number--int"></a>číslo: [int](xref:microsoft.quantum.lang-ref.int)

Nezáporné celé číslo, které má být převedeno na pole logických hodnot.


### <a name="bits--int"></a>bity: [int](xref:microsoft.quantum.lang-ref.int)

Počet bitů v binárním vyjádření `number` .



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Pole logických hodnot, které představují `number` .

## <a name="remarks"></a>Poznámky

Vstup `bits` musí být v rozmezí od 0 do 63.
Vstup `number` musí být mezi 0 a $2 ^ {\texttt{BITS}}-$1.