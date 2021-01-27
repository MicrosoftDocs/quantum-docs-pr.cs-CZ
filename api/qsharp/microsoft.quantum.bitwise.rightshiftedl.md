---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 03ed69c7151e62b91c4a036e301f99b45ce5ab62
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842099"
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

```qsharp
let c = a >>> b;
let c = RightShiftedL(a, b);
```