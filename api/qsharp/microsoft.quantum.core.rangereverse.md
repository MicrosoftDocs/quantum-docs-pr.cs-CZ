---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: 7bd7c55abe0b56b9d30b4c6e91f7175101dd2948
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213833"
---
# <a name="rangereverse-function"></a>RangeReverse – funkce

Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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