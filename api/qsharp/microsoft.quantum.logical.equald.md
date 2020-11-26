---
uid: Microsoft.Quantum.Logical.EqualD
title: EQUAL – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: d6731b293ba402f5cd43591d3c2bcd258e8ebe32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198142"
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

```Q#
let cond = a == b;
let cond = EqualD(a, b);
```