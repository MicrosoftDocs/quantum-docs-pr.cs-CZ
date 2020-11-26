---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: NearlyEqualD – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: 246fad15c691a53fcc5be10f2c713672e0b54e6b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197462"
---
# <a name="nearlyequald-function"></a>NearlyEqualD – funkce

Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí hodnotu true pouze v případě, že dva vstupy jsou téměř stejné (tj. v rámci tolerance 1E-12).

```qsharp
function NearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Vstup

### <a name="a--double"></a>Odpověď: [Double](xref:microsoft.quantum.lang-ref.double)

První hodnota, která se má porovnat.


### <a name="b--double"></a>b: [Double](xref:microsoft.quantum.lang-ref.double)

Druhá hodnota, která se má porovnat.



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` pouze pokud `a` je téměř rovno `b` .

## <a name="remarks"></a>Poznámky

Následují ekvivalenty:

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```