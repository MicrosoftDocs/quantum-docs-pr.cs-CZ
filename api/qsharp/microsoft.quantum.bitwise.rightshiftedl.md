---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 3d941e1a0bcd96fe54ab01019293d883f11547a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219511"
---
# <a name="rightshiftedl-function"></a>RightShiftedL – funkce

Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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