---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 39c8581fe795a1b76d2a6e81c238a271287c2c38
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213799"
---
# <a name="rangestep-function"></a>RangeStep – funkce

Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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