---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 9783a49a77bdc39ffe8c7725196eb620f4cd0100
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698289"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray – funkce

Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)

Balíček [](https://nuget.org/packages/)


Vytvoří binární reprezentace kladného celého čísla s použitím reprezentace Little-endian pro vrácené pole.

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>Vstup

### <a name="number--int"></a>číslo: [int](xref:microsoft.quantum.lang-ref.int)

Kladné celé číslo, které má být převedeno na pole logických hodnot.


### <a name="bits--int"></a>bity: [int](xref:microsoft.quantum.lang-ref.int)

Počet bitů v binárním vyjádření `number` .



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Pole logických hodnot, které představují `number` .

## <a name="remarks"></a>Poznámky

Vstup `bits` musí být v rozmezí od 0 do 63.
Vstup `number` musí být mezi 0 a $2 ^ {\texttt{BITS}}-$1.