---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 4dbcf517c4dc17775040444c77deb0e449082390
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698229"
---
# <a name="rangeend-function"></a>RangeEnd – funkce

Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)

Balíček [](https://nuget.org/packages/)


Vrátí definovanou koncovou hodnotu daného rozsahu, což není nutně poslední prvek v sekvenci.

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a>Vstup

### <a name="range--range"></a>Rozsah: [Rozsah](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Definovaná koncová hodnota daného rozsahu.

## <a name="remarks"></a>Poznámky

První prvek výrazu rozsahu je `start` , jeho druhý prvek je, `start+step` třetí prvek je `start+step+step` atd., dokud `end` není předán.

Všimněte si, že definovaná koncová hodnota rozsahu se může lišit od posledního prvku v pořadí určeném rozsahem. například v rozsahu 0.. 2... 5 poslední prvek je 4, ale koncová hodnota je 5.