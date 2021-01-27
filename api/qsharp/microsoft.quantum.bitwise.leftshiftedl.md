---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 014653011574d0fabb4b9aa04cedf58b87ddf798
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842139"
---
# <a name="leftshiftedl-function"></a>LeftShiftedL – funkce

Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Posune bitovou reprezentaci čísla vlevo o daný počet bitů.

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>Vstup

### <a name="value--bigint"></a>hodnota: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Číslo, jehož bitová reprezentace má být posunuta doleva (důležitější).


### <a name="amount--int"></a>částka: [int](xref:microsoft.quantum.lang-ref.int)

Počet bitů, které `value` mají být posunuty doleva.



## <a name="output--bigint"></a>Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Hodnota, která `value` se posouvá vlevo od `amount` bitů.

## <a name="remarks"></a>Poznámky

Následují ekvivalenty:

```qsharp
let c = a <<< b;
let c = LeftShiftedL(a, b);
```