---
uid: Microsoft.Quantum.Convert.MaybeBigIntAsInt
title: MaybeBigIntAsInt – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: MaybeBigIntAsInt
qsharp.summary: Converts a given big integer to an equivalent integer, if possible. The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.
ms.openlocfilehash: 1f10ac027f8f289e5ea554a7804abeb33def4df8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832767"
---
# <a name="maybebigintasint-function"></a>MaybeBigIntAsInt – funkce

Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Převede dané velké celé číslo na ekvivalentní celé číslo, pokud je to možné.
Funkce vrátí dvojici výsledného celého čísla a logického příznaku, který je true, pokud a pouze v případě, že byl převod možný.

```qsharp
function MaybeBigIntAsInt (a : BigInt) : (Int, Bool)
```


## <a name="input"></a>Vstup

### <a name="a--bigint"></a>a: [bigint](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--intbool"></a>Výstup: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool))



## <a name="remarks"></a>Poznámky

Další podrobnosti najdete v tématu [konstruktor C# BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) .