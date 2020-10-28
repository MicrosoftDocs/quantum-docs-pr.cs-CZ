---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 2929ba58b636847257391930e1019769fd2c2580
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705577"
---
# <a name="rightshiftedl-function"></a>RightShiftedL – funkce

Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)

Balíček [](https://nuget.org/packages/)


Posune bitovou reprezentaci čísla přímo podle zadaného počtu bitů.

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>Vstup

### <a name="value--bigint"></a>hodnota: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Číslo, jehož bitová reprezentace má být posunuta doprava (méně významná).


### <a name="amount--int"></a>částka: [int](xref:microsoft.quantum.lang-ref.int)

Počet bitů, které `value` mají být posunuty doprava.



## <a name="output--bigint"></a>Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Hodnota, která `value` se posouvá doprava po `amount` bitech.

## <a name="remarks"></a>Poznámky

Následují ekvivalenty:

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```