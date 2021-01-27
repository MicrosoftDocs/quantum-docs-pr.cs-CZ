---
uid: Microsoft.Quantum.Logical.LessThanI
title: LessThanI – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 69c3d7c414967b830c15189c895a2b34f409c7b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815835"
---
# <a name="lessthani-function"></a>LessThanI – funkce

Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí hodnotu true pouze v případě, že je číslo menší než jiné číslo.

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Vstup

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

První hodnota, která se má porovnat.


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

Druhá hodnota, která se má porovnat.



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` pouze v případě, že `a` je pouze striktně menší než `b` .

## <a name="remarks"></a>Poznámky

Následují ekvivalenty:

```qsharp
let cond = a < b;
let cond = LessThanI(a, b);
```