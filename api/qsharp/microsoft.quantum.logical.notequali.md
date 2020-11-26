---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: dc132cbab556bd4b5d5c557ad267f1839e8039fc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197207"
---
# <a name="notequali-function"></a>NotEqualI – funkce

Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí hodnotu true pouze v případě, že se neshodují dva vstupy.

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Vstup

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

První hodnota, která se má porovnat.


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

Druhá hodnota, která se má porovnat.



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` pouze pokud `a` se nerovná `b` .

## <a name="remarks"></a>Poznámky

Následují ekvivalenty:

```Q#
let cond = a != b;
let cond = NotEqualI(a, b);
```