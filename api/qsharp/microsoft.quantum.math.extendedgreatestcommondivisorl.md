---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorL
title: ExtendedGreatestCommonDivisorL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorL
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: e671405045d6d2587a8c6ccbac4ae3402f92f722
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708529"
---
# <a name="extendedgreatestcommondivisorl-function"></a><span data-ttu-id="7dd50-102">ExtendedGreatestCommonDivisorL – funkce</span><span class="sxs-lookup"><span data-stu-id="7dd50-102">ExtendedGreatestCommonDivisorL function</span></span>

<span data-ttu-id="7dd50-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="7dd50-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="7dd50-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7dd50-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7dd50-105">Vypočítá řazenou kolekci členů $ (u, v) $, což $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, kde $ \operatorname{GCD} $ je $a $ největší společný dělitel $a $ a $b $.</span><span class="sxs-lookup"><span data-stu-id="7dd50-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="7dd50-106">GCD je vždy pozitivní.</span><span class="sxs-lookup"><span data-stu-id="7dd50-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorL (a : BigInt, b : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a><span data-ttu-id="7dd50-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="7dd50-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="7dd50-108">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7dd50-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="7dd50-109">první číslo, které je vypočítáno jako největšího nejdelšího společného dělitele</span><span class="sxs-lookup"><span data-stu-id="7dd50-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="7dd50-110">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7dd50-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="7dd50-111">druhý počet, od kterého se počítá rozšířený největší dělitel</span><span class="sxs-lookup"><span data-stu-id="7dd50-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigintbigint"></a><span data-ttu-id="7dd50-112">Výstup: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[bigint](xref:microsoft.quantum.lang-ref.bigint))</span><span class="sxs-lookup"><span data-stu-id="7dd50-112">Output : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>

<span data-ttu-id="7dd50-113">Řazená kolekce členů $ (u, v) $ s vlastností $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $.</span><span class="sxs-lookup"><span data-stu-id="7dd50-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="7dd50-114">Odkazy</span><span class="sxs-lookup"><span data-stu-id="7dd50-114">References</span></span>

- <span data-ttu-id="7dd50-115">Tato implementace je podle https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="7dd50-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>