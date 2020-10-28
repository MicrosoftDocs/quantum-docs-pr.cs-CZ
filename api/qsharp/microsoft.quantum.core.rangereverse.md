---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698225"
---
# <a name="rangereverse-function"></a>RangeReverse – funkce

Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)

Balíček [](https://nuget.org/packages/)


Vrátí nový rozsah, který je zpětným rozsahem vstupu.

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a>Vstup

### <a name="r--range"></a>r: [Rozsah](xref:microsoft.quantum.lang-ref.range)

Vstupní rozsah



## <a name="output--range"></a>Výstup: [Rozsah](xref:microsoft.quantum.lang-ref.range)

Nový rozsah, který je opačnou barvou daného rozsahu.

## <a name="remarks"></a>Poznámky

Všimněte si, že obrácený rozsah není jednoduše `end` .. `-step` .. `start` , protože skutečný poslední prvek rozsahu nemůže být stejný jako `end` .