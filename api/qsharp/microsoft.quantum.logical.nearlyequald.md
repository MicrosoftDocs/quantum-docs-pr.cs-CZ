---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: NearlyEqualD – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: fbbf1f7a59600ecc4a0a59d1c08cd0e1310d2d20
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814366"
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

```qsharp
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```