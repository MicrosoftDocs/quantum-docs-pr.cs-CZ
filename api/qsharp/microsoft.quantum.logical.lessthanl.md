---
uid: Microsoft.Quantum.Logical.LessThanL
title: LessThanL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: d5753f9e1447fc1bd433703037fe44c86aaa659c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849154"
---
# <a name="lessthanl-function"></a>LessThanL – funkce

Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí hodnotu true pouze v případě, že je číslo menší než jiné číslo.

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a>Vstup

### <a name="a--bigint"></a>a: [bigint](xref:microsoft.quantum.lang-ref.bigint)

První hodnota, která se má porovnat.


### <a name="b--bigint"></a>b: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Druhá hodnota, která se má porovnat.



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` pouze v případě, že `a` je pouze striktně menší než `b` .

## <a name="remarks"></a>Poznámky

Následují ekvivalenty:

```qsharp
let cond = a < b;
let cond = LessThanL(a, b);
```