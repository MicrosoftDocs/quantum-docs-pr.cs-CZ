---
uid: Microsoft.Quantum.Logical.EqualD
title: EQUAL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f8a24d7bfb9b4f7b8b0e1f68a94bfb341716b024
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816872"
---
# <a name="equald-function"></a>EQUAL – funkce

Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí hodnotu true pouze v případě, že jsou dva vstupy stejné.

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Vstup

### <a name="a--double"></a>Odpověď: [Double](xref:microsoft.quantum.lang-ref.double)

První hodnota, která se má porovnat.


### <a name="b--double"></a>b: [Double](xref:microsoft.quantum.lang-ref.double)

Druhá hodnota, která se má porovnat.



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` pouze v případě, že `a` je rovno `b` .

## <a name="remarks"></a>Poznámky

Následují ekvivalenty:

```qsharp
let cond = a == b;
let cond = EqualD(a, b);
```