---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 44683b204ecd469f5f5412a7ec06e98ec8a4f37e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223999"
---
# <a name="rangestart-function"></a>RangeStart – funkce

Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Vrátí definovanou počáteční hodnotu daného rozsahu.

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a>Vstup

### <a name="range--range"></a>Rozsah: [Rozsah](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Definovaná počáteční hodnota daného rozsahu.

## <a name="remarks"></a>Poznámky

První prvek výrazu rozsahu je `start` , jeho druhý prvek je, `start+step` třetí prvek je `start+step+step` atd., dokud `end` není předán.

Všimněte si, že definovaná počáteční hodnota rozsahu je shodná s prvním prvkem sekvence, pokud rozsah neurčuje prázdnou sekvenci (například 2.. 1).