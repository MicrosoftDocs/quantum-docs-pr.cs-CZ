---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: ce68311adf211169c2fb499bb189332370a6d6ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705640"
---
# <a name="leftshiftedi-function"></a>LeftShiftedI – funkce

Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)

Balíček [](https://nuget.org/packages/)


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