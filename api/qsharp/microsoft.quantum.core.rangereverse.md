---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: f3b94d3c6fa6350a2c337f8bc8d889d24d87a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853660"
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