---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: LessThanOrEqualD – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 7b0e9da379bd67eb78a80e7a535a15dcb8ba85c7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697288"
---
# <a name="lessthanorequald-function"></a>LessThanOrEqualD – funkce

Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)

Balíček [](https://nuget.org/packages/)


Vrátí hodnotu true pouze v případě, že je číslo menší nebo rovno jinému číslu.

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Vstup

### <a name="a--double"></a>Odpověď: [Double](xref:microsoft.quantum.lang-ref.double)

První hodnota, která se má porovnat.


### <a name="b--double"></a>b: [Double](xref:microsoft.quantum.lang-ref.double)

Druhá hodnota, která se má porovnat.



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` pouze pokud je a pouze v případě, že `a` je menší nebo rovno `b` .

## <a name="remarks"></a>Poznámky

Následují ekvivalenty:

```Q#
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```