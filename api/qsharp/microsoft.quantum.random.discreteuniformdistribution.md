---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 5e93c66d891d9b6aec548c0cf266df35e6090c92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706728"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="5276f-102">DiscreteUniformDistribution – funkce</span><span class="sxs-lookup"><span data-stu-id="5276f-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="5276f-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="5276f-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="5276f-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5276f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5276f-105">Vrátí jednotnou distribuci v rámci daného celkového rozsahu.</span><span class="sxs-lookup"><span data-stu-id="5276f-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="5276f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5276f-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="5276f-107">minimum: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5276f-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5276f-108">Nejmenší celé číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="5276f-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="5276f-109">maximum: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5276f-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5276f-110">Největší celé číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="5276f-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="5276f-111">Výstup: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="5276f-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="5276f-112">Distribuce, jejíž náhodná variates jsou celá čísla v rozsahu, od `min` do `max` s jednotnou pravděpodobností.</span><span class="sxs-lookup"><span data-stu-id="5276f-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="5276f-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5276f-113">Remarks</span></span>

<span data-ttu-id="5276f-114">Dojde k chybě `max <= min` , pokud.</span><span class="sxs-lookup"><span data-stu-id="5276f-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="5276f-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="5276f-115">See Also</span></span>

- [<span data-ttu-id="5276f-116">Microsoft. DrawRandomDouble.</span><span class="sxs-lookup"><span data-stu-id="5276f-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)