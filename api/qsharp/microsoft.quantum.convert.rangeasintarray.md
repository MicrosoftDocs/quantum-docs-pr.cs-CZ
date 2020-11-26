---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: f756e42aef7dc600e1fc6943a02513ac791f2320
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214003"
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