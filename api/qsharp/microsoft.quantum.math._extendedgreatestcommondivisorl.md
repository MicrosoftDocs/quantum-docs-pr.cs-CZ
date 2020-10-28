---
uid: Microsoft.Quantum.Math._ExtendedGreatestCommonDivisorL
title: _ExtendedGreatestCommonDivisorL funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: _ExtendedGreatestCommonDivisorL
qsharp.summary: Internal recursive call to calculate the GCD.
ms.openlocfilehash: d6f3499377aeb633f42fbddef6840d7058a4066b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708607"
---
# <a name="_extendedgreatestcommondivisorl-function"></a><span data-ttu-id="51599-102">_ExtendedGreatestCommonDivisorL funkce</span><span class="sxs-lookup"><span data-stu-id="51599-102">_ExtendedGreatestCommonDivisorL function</span></span>

<span data-ttu-id="51599-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="51599-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="51599-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="51599-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="51599-105">Vnitřní rekurzivní volání pro výpočet GCDu.</span><span class="sxs-lookup"><span data-stu-id="51599-105">Internal recursive call to calculate the GCD.</span></span>

```qsharp
function _ExtendedGreatestCommonDivisorL (signA : Int, signB : Int, r : (BigInt, BigInt), s : (BigInt, BigInt), t : (BigInt, BigInt)) : (BigInt, BigInt)
```


## <a name="input"></a><span data-ttu-id="51599-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="51599-106">Input</span></span>

### <a name="signa--int"></a><span data-ttu-id="51599-107">signA: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="51599-107">signA : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="signb--int"></a><span data-ttu-id="51599-108">signB: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="51599-108">signB : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="r--bigintbigint"></a><span data-ttu-id="51599-109">r: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[bigint](xref:microsoft.quantum.lang-ref.bigint))</span><span class="sxs-lookup"><span data-stu-id="51599-109">r : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>




### <a name="s--bigintbigint"></a><span data-ttu-id="51599-110">s: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[bigint](xref:microsoft.quantum.lang-ref.bigint))</span><span class="sxs-lookup"><span data-stu-id="51599-110">s : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>




### <a name="t--bigintbigint"></a><span data-ttu-id="51599-111">t: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[bigint](xref:microsoft.quantum.lang-ref.bigint))</span><span class="sxs-lookup"><span data-stu-id="51599-111">t : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>





## <a name="output--bigintbigint"></a><span data-ttu-id="51599-112">Výstup: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[bigint](xref:microsoft.quantum.lang-ref.bigint))</span><span class="sxs-lookup"><span data-stu-id="51599-112">Output : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>

