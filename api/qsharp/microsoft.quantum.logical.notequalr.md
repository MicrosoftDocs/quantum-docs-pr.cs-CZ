---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 39601396a75d8c1b9193d4b8f34fa05466beff06
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848501"
---
# <a name="notequalr-function"></a>NotEqualR – funkce

Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let cond = a != b;
let cond = NotEqualR(a, b);
```