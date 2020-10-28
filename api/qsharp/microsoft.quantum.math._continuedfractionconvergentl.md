---
uid: Microsoft.Quantum.Math._ContinuedFractionConvergentL
title: _ContinuedFractionConvergentL funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: _ContinuedFractionConvergentL
qsharp.summary: Internal recursive call to calculate the GCD with a bound
ms.openlocfilehash: b8a7d17df9c1c7e36bfca0e529694ccf0979c2ee
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708397"
---
# <a name="_continuedfractionconvergentl-function"></a><span data-ttu-id="f3fa3-102">_ContinuedFractionConvergentL funkce</span><span class="sxs-lookup"><span data-stu-id="f3fa3-102">_ContinuedFractionConvergentL function</span></span>

<span data-ttu-id="f3fa3-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f3fa3-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f3fa3-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f3fa3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f3fa3-105">Vnitřní rekurzivní volání pro výpočet GCDu s vazbou</span><span class="sxs-lookup"><span data-stu-id="f3fa3-105">Internal recursive call to calculate the GCD with a bound</span></span>

```qsharp
function _ContinuedFractionConvergentL (signA : Int, signB : Int, r : (BigInt, BigInt), s : (BigInt, BigInt), t : (BigInt, BigInt), denominatorBound : BigInt) : Microsoft.Quantum.Math.BigFraction
```


## <a name="input"></a><span data-ttu-id="f3fa3-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f3fa3-106">Input</span></span>

### <a name="signa--int"></a><span data-ttu-id="f3fa3-107">signA: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f3fa3-107">signA : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="signb--int"></a><span data-ttu-id="f3fa3-108">signB: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f3fa3-108">signB : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="r--bigintbigint"></a><span data-ttu-id="f3fa3-109">r: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[bigint](xref:microsoft.quantum.lang-ref.bigint))</span><span class="sxs-lookup"><span data-stu-id="f3fa3-109">r : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>




### <a name="s--bigintbigint"></a><span data-ttu-id="f3fa3-110">s: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[bigint](xref:microsoft.quantum.lang-ref.bigint))</span><span class="sxs-lookup"><span data-stu-id="f3fa3-110">s : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>




### <a name="t--bigintbigint"></a><span data-ttu-id="f3fa3-111">t: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[bigint](xref:microsoft.quantum.lang-ref.bigint))</span><span class="sxs-lookup"><span data-stu-id="f3fa3-111">t : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>




### <a name="denominatorbound--bigint"></a><span data-ttu-id="f3fa3-112">denominatorBound: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f3fa3-112">denominatorBound : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigfraction"></a><span data-ttu-id="f3fa3-113">Výstup: [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span><span class="sxs-lookup"><span data-stu-id="f3fa3-113">Output : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span></span>

