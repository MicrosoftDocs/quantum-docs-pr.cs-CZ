---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b0ca7d3cb84c58429e9b3a29893a6140a717006b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705584"
---
# <a name="rightshiftedi-function"></a>RightShiftedI – funkce

Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)

Balíček [](https://nuget.org/packages/)


Posune bitovou reprezentaci čísla přímo podle zadaného počtu bitů.

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>Vstup

### <a name="value--int"></a>hodnota: [int](xref:microsoft.quantum.lang-ref.int)

Číslo, jehož bitová reprezentace má být posunuta doprava (méně významná).


### <a name="amount--int"></a>částka: [int](xref:microsoft.quantum.lang-ref.int)

Počet bitů, které `value` mají být posunuty doprava.



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Hodnota, která `value` se posouvá doprava po `amount` bitech.

## <a name="remarks"></a>Poznámky

Následují ekvivalenty:

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```