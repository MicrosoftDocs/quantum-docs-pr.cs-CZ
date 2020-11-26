---
uid: Microsoft.Quantum.Convert.BoolArrayAsBigInt
title: BoolArrayAsBigInt – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsBigInt
qsharp.summary: Converts a given array of Booleans to an equivalent big integer. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 5a85fd9f81cec0f2de7e7807622aab9604a4db7c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214309"
---
# <a name="boolarrayasbigint-function"></a>BoolArrayAsBigInt – funkce

Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Převede dané pole logických hodnot na ekvivalentní velké celé číslo.
Element 0 pole je nejméně významným bitem velkých celých čísel.

```qsharp
function BoolArrayAsBigInt (a : Bool[]) : BigInt
```


## <a name="input"></a>Vstup

### <a name="a--bool"></a>Odpověď: [bool](xref:microsoft.quantum.lang-ref.bool)[]





## <a name="output--bigint"></a>Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)



## <a name="remarks"></a>Poznámky

Další podrobnosti najdete v tématu [konstruktor C# BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) .