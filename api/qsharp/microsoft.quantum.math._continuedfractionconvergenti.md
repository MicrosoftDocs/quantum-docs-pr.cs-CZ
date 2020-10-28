---
uid: Microsoft.Quantum.Math._ContinuedFractionConvergentI
title: _ContinuedFractionConvergentI funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: _ContinuedFractionConvergentI
qsharp.summary: Internal recursive call to calculate the GCD with a bound
ms.openlocfilehash: 849c3f72fe4c82d7256e91f07af284217f998a63
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708398"
---
# <a name="_continuedfractionconvergenti-function"></a><span data-ttu-id="98fb5-102">_ContinuedFractionConvergentI funkce</span><span class="sxs-lookup"><span data-stu-id="98fb5-102">_ContinuedFractionConvergentI function</span></span>

<span data-ttu-id="98fb5-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="98fb5-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="98fb5-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="98fb5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="98fb5-105">Vnitřní rekurzivní volání pro výpočet GCDu s vazbou</span><span class="sxs-lookup"><span data-stu-id="98fb5-105">Internal recursive call to calculate the GCD with a bound</span></span>

```qsharp
function _ContinuedFractionConvergentI (signA : Int, signB : Int, r : (Int, Int), s : (Int, Int), t : (Int, Int), denominatorBound : Int) : Microsoft.Quantum.Math.Fraction
```


## <a name="input"></a><span data-ttu-id="98fb5-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="98fb5-106">Input</span></span>

### <a name="signa--int"></a><span data-ttu-id="98fb5-107">signA: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="98fb5-107">signA : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="signb--int"></a><span data-ttu-id="98fb5-108">signB: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="98fb5-108">signB : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="r--intint"></a><span data-ttu-id="98fb5-109">r: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="98fb5-109">r : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>




### <a name="s--intint"></a><span data-ttu-id="98fb5-110">s: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="98fb5-110">s : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>




### <a name="t--intint"></a><span data-ttu-id="98fb5-111">t: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="98fb5-111">t : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>




### <a name="denominatorbound--int"></a><span data-ttu-id="98fb5-112">denominatorBound: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="98fb5-112">denominatorBound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--fraction"></a><span data-ttu-id="98fb5-113">Výstup: [zlomek](xref:Microsoft.Quantum.Math.Fraction)</span><span class="sxs-lookup"><span data-stu-id="98fb5-113">Output : [Fraction](xref:Microsoft.Quantum.Math.Fraction)</span></span>

