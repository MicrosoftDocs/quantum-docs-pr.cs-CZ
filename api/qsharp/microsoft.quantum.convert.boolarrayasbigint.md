---
uid: Microsoft.Quantum.Convert.BoolArrayAsBigInt
title: BoolArrayAsBigInt – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsBigInt
qsharp.summary: Converts a given array of Booleans to an equivalent big integer. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 75656ba188a1b822eb42e98412365bf5873bf46e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698336"
---
# <a name="boolarrayasbigint-function"></a><span data-ttu-id="be8e3-102">BoolArrayAsBigInt – funkce</span><span class="sxs-lookup"><span data-stu-id="be8e3-102">BoolArrayAsBigInt function</span></span>

<span data-ttu-id="be8e3-103">Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="be8e3-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="be8e3-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="be8e3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="be8e3-105">Převede dané pole logických hodnot na ekvivalentní velké celé číslo.</span><span class="sxs-lookup"><span data-stu-id="be8e3-105">Converts a given array of Booleans to an equivalent big integer.</span></span>
<span data-ttu-id="be8e3-106">Element 0 pole je nejméně významným bitem velkých celých čísel.</span><span class="sxs-lookup"><span data-stu-id="be8e3-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BoolArrayAsBigInt (a : Bool[]) : BigInt
```


## <a name="input"></a><span data-ttu-id="be8e3-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="be8e3-107">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="be8e3-108">Odpověď: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="be8e3-108">a : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>





## <a name="output--bigint"></a><span data-ttu-id="be8e3-109">Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="be8e3-109">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="be8e3-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="be8e3-110">Remarks</span></span>

<span data-ttu-id="be8e3-111">Další podrobnosti najdete v tématu [konstruktor C# BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) .</span><span class="sxs-lookup"><span data-stu-id="be8e3-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>