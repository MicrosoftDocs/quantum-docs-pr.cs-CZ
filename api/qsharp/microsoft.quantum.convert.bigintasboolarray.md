---
uid: Microsoft.Quantum.Convert.BigIntAsBoolArray
title: BigIntAsBoolArray – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BigIntAsBoolArray
qsharp.summary: Converts a given big integer to an array of Booleans. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 13ba5b6dbf477dd1a02f24da5b7aca9bdb30ad2b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698337"
---
# <a name="bigintasboolarray-function"></a><span data-ttu-id="984f4-102">BigIntAsBoolArray – funkce</span><span class="sxs-lookup"><span data-stu-id="984f4-102">BigIntAsBoolArray function</span></span>

<span data-ttu-id="984f4-103">Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="984f4-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="984f4-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="984f4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="984f4-105">Převede dané velké celé číslo na pole logických hodnot.</span><span class="sxs-lookup"><span data-stu-id="984f4-105">Converts a given big integer to an array of Booleans.</span></span>
<span data-ttu-id="984f4-106">Element 0 pole je nejméně významným bitem velkých celých čísel.</span><span class="sxs-lookup"><span data-stu-id="984f4-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BigIntAsBoolArray (a : BigInt) : Bool[]
```


## <a name="input"></a><span data-ttu-id="984f4-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="984f4-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="984f4-108">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="984f4-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bool"></a><span data-ttu-id="984f4-109">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="984f4-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="984f4-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="984f4-110">Remarks</span></span>

<span data-ttu-id="984f4-111">Další podrobnosti najdete v tématu [konstruktor C# BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) .</span><span class="sxs-lookup"><span data-stu-id="984f4-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>