---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: 8c6b83d78e3b22ea1a17a48de66592950bf905a3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850106"
---
# <a name="rangeasintarray-function"></a>RangeAsIntArray – funkce

Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vytvoří pole celých čísel, která jsou vyhodnocena spuštěním `arr` .. krok.. účelu.

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a>Vstup

### <a name="range--range"></a>Rozsah: [Rozsah](xref:microsoft.quantum.lang-ref.range)

`Range`Hodnoty, `start..step..end` které mají být převedeny na pole.



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]

Nové pole celých čísel odpovídající hodnotám, které prochází `range` .

## <a name="example"></a>Příklad

```qsharp
// The following returns [1,3,5,7];
let array = RangeAsIntArray(1..2..8);
```