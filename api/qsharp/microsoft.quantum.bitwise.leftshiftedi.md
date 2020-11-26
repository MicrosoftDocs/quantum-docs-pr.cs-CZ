---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3a7220489bfa241e2337df14291bafb1d6e0e19e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209855"
---
# <a name="leftshiftedi-function"></a>LeftShiftedI – funkce

Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Posune bitovou reprezentaci čísla vlevo o daný počet bitů.

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>Vstup

### <a name="value--int"></a>hodnota: [int](xref:microsoft.quantum.lang-ref.int)

Číslo, jehož bitová reprezentace má být posunuta doleva (důležitější).


### <a name="amount--int"></a>částka: [int](xref:microsoft.quantum.lang-ref.int)

Počet bitů, které `value` mají být posunuty doleva.



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Hodnota, která `value` se posouvá vlevo od `amount` bitů.

## <a name="remarks"></a>Poznámky

Následují ekvivalenty:

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```