---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b20a4a8c281a470af9a4828f8a5ca905a7918723
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209770"
---
# <a name="rightshiftedi-function"></a>RightShiftedI – funkce

Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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