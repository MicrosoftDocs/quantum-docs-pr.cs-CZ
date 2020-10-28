---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: f8e4c42330f2d6afdc1c0a9bdde36081ccab2f94
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698205"
---
# <a name="rangestep-function"></a>RangeStep – funkce

Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)

Balíček [](https://nuget.org/packages/)


Vrátí celé číslo, které určuje, jak se počítá další hodnota rozsahu.

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a>Vstup

### <a name="range--range"></a>Rozsah: [Rozsah](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Definovaná hodnota kroku daného rozsahu.

## <a name="remarks"></a>Poznámky

První prvek výrazu rozsahu je `start` , jeho druhý prvek je, `start+step` třetí prvek je `start+step+step` atd., dokud `end` není předán.