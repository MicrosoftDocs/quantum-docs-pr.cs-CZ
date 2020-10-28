---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: ExtendedGreatestCommonDivisorI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 8cb21ae5052ae6c5a8aed8be71d6bd3d32034272
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708530"
---
# <a name="extendedgreatestcommondivisori-function"></a><span data-ttu-id="3fea5-102">ExtendedGreatestCommonDivisorI – funkce</span><span class="sxs-lookup"><span data-stu-id="3fea5-102">ExtendedGreatestCommonDivisorI function</span></span>

<span data-ttu-id="3fea5-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="3fea5-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="3fea5-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3fea5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3fea5-105">Vypočítá řazenou kolekci členů $ (u, v) $, což $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, kde $ \operatorname{GCD} $ je $a $ největší společný dělitel $a $ a $b $.</span><span class="sxs-lookup"><span data-stu-id="3fea5-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="3fea5-106">GCD je vždy pozitivní.</span><span class="sxs-lookup"><span data-stu-id="3fea5-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a><span data-ttu-id="3fea5-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="3fea5-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="3fea5-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3fea5-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3fea5-109">první číslo, které je vypočítáno jako největšího nejdelšího společného dělitele</span><span class="sxs-lookup"><span data-stu-id="3fea5-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="3fea5-110">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3fea5-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3fea5-111">druhý počet, od kterého se počítá rozšířený největší dělitel</span><span class="sxs-lookup"><span data-stu-id="3fea5-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--intint"></a><span data-ttu-id="3fea5-112">Výstup: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="3fea5-112">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="3fea5-113">Řazená kolekce členů $ (u, v) $ s vlastností $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $.</span><span class="sxs-lookup"><span data-stu-id="3fea5-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="3fea5-114">Odkazy</span><span class="sxs-lookup"><span data-stu-id="3fea5-114">References</span></span>

- <span data-ttu-id="3fea5-115">Tato implementace je podle https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="3fea5-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>