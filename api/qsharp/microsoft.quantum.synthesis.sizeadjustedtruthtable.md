---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: c53ac3f2c46bca955847fc7b380337e3910390ac
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202919"
---
# <a name="sizeadjustedtruthtable-function"></a>SizeAdjustedTruthTable – funkce

Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Upraví tabulku pravdy z pole logických hodnot podle počtu proměnných.

Je vráceno nové pole o délce `2^numVars` , pravděpodobně vyžadovat, aby `table` se velikost rozšířila na `false` položky nebo zkrácení na `2^numVars` prvky.

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a>Vstup

### <a name="table--bool"></a>Tabulka: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Tabulka pravdy jako pole hodnot hodnoty pravdy


### <a name="numvars--int"></a>numVars: [int](xref:microsoft.quantum.lang-ref.int)

Počet proměnných



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Velikost upravená tabulka pravdy