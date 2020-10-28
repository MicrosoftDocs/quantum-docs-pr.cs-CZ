---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Operace DrawRandomInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: d9d8d9fbb25587ac5ccbd4edf0e555649380375f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708932"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="11491-102">Operace DrawRandomInt</span><span class="sxs-lookup"><span data-stu-id="11491-102">DrawRandomInt operation</span></span>

<span data-ttu-id="11491-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="11491-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="11491-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="11491-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="11491-105">Vykreslí náhodné celé číslo v daném rozsahu.</span><span class="sxs-lookup"><span data-stu-id="11491-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="11491-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="11491-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="11491-107">minimum: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="11491-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="11491-108">Nejmenší celé číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="11491-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="11491-109">maximum: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="11491-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="11491-110">Největší celé číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="11491-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="11491-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="11491-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="11491-112">Celé číslo v rozsahu v rozsahu od `min` do `max` s jednotnou pravděpodobností.</span><span class="sxs-lookup"><span data-stu-id="11491-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="11491-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="11491-113">Remarks</span></span>

<span data-ttu-id="11491-114">Dojde k chybě `max <= min` , pokud.</span><span class="sxs-lookup"><span data-stu-id="11491-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="11491-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="11491-115">See Also</span></span>

- [<span data-ttu-id="11491-116">Microsoft. DiscreteUniformDistribution.</span><span class="sxs-lookup"><span data-stu-id="11491-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)