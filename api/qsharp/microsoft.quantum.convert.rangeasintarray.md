---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: bd3ac51d2925d7a4450b2bc5e6f7899fcab18f2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698264"
---
# <a name="rangeasintarray-function"></a>RangeAsIntArray – funkce

Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)

Balíček [](https://nuget.org/packages/)


Vytvoří pole celých čísel, která jsou vyhodnocena spuštěním `arr` .. krok.. účelu.

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a>Vstup

### <a name="range--range"></a>Rozsah: [Rozsah](xref:microsoft.quantum.lang-ref.range)

`Range`Hodnoty, `start..step..end` které mají být převedeny na pole.



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]

Nové pole celých čísel odpovídající hodnotám, které prochází `range` .