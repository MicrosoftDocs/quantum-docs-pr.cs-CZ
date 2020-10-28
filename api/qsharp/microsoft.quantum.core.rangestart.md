---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 3e4b0cebe34b4c98cb1d582a9cd11b46ff778517
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698208"
---
# <a name="rangestart-function"></a>RangeStart – funkce

Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)

Balíček [](https://nuget.org/packages/)


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