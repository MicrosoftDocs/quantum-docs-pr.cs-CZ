---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 06615c7ffb6aafc296077990dfca0ce25e1e00fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697244"
---
# <a name="notequalr-function"></a>NotEqualR – funkce

Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)

Balíček [](https://nuget.org/packages/)


Vrátí hodnotu true pouze v případě, že se neshodují dva vstupy.

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>Vstup

### <a name="a--__invalidresult__"></a>Odpověď: __neplatné <Result>__

První hodnota, která se má porovnat.


### <a name="b--__invalidresult__"></a>b: __neplatné <Result>__

Druhá hodnota, která se má porovnat.



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` pouze pokud `a` se nerovná `b` .

## <a name="remarks"></a>Poznámky

Následují ekvivalenty:

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```