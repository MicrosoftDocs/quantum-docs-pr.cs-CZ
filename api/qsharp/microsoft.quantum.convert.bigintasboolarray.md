---
uid: Microsoft.Quantum.Convert.BigIntAsBoolArray
title: BigIntAsBoolArray – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BigIntAsBoolArray
qsharp.summary: Converts a given big integer to an array of Booleans. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 593fad99ef22d3c906b9f10adc07638bed227509
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224543"
---
# <a name="bigintasboolarray-function"></a>BigIntAsBoolArray – funkce

Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Převede dané velké celé číslo na pole logických hodnot.
Element 0 pole je nejméně významným bitem velkých celých čísel.

```qsharp
function BigIntAsBoolArray (a : BigInt) : Bool[]
```


## <a name="input"></a>Vstup

### <a name="a--bigint"></a>a: [bigint](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)[]



## <a name="remarks"></a>Poznámky

Další podrobnosti najdete v tématu [konstruktor C# BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) .