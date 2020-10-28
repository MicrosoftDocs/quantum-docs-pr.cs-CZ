---
uid: Microsoft.Quantum.Convert.MaybeBigIntAsInt
title: MaybeBigIntAsInt – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: MaybeBigIntAsInt
qsharp.summary: Converts a given big integer to an equivalent integer, if possible. The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.
ms.openlocfilehash: b91912f6f669afad888e71174fef6e2e6f8e7156
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698284"
---
# <a name="maybebigintasint-function"></a><span data-ttu-id="1e4c1-102">MaybeBigIntAsInt – funkce</span><span class="sxs-lookup"><span data-stu-id="1e4c1-102">MaybeBigIntAsInt function</span></span>

<span data-ttu-id="1e4c1-103">Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="1e4c1-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="1e4c1-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1e4c1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1e4c1-105">Převede dané velké celé číslo na ekvivalentní celé číslo, pokud je to možné.</span><span class="sxs-lookup"><span data-stu-id="1e4c1-105">Converts a given big integer to an equivalent integer, if possible.</span></span>
<span data-ttu-id="1e4c1-106">Funkce vrátí dvojici výsledného celého čísla a logického příznaku, který je true, pokud a pouze v případě, že byl převod možný.</span><span class="sxs-lookup"><span data-stu-id="1e4c1-106">The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.</span></span>

```qsharp
function MaybeBigIntAsInt (a : BigInt) : (Int, Bool)
```


## <a name="input"></a><span data-ttu-id="1e4c1-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="1e4c1-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="1e4c1-108">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1e4c1-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--intbool"></a><span data-ttu-id="1e4c1-109">Výstup: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool))</span><span class="sxs-lookup"><span data-stu-id="1e4c1-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool))</span></span>



## <a name="remarks"></a><span data-ttu-id="1e4c1-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="1e4c1-110">Remarks</span></span>

<span data-ttu-id="1e4c1-111">Další podrobnosti najdete v tématu [konstruktor C# BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) .</span><span class="sxs-lookup"><span data-stu-id="1e4c1-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>