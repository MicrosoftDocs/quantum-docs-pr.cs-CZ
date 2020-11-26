---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 08a62805f59df339ef6b91dff802c40c407808f4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193008"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="198aa-102">DiscreteUniformDistribution – funkce</span><span class="sxs-lookup"><span data-stu-id="198aa-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="198aa-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="198aa-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="198aa-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="198aa-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="198aa-105">Vrátí jednotnou distribuci v rámci daného celkového rozsahu.</span><span class="sxs-lookup"><span data-stu-id="198aa-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="198aa-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="198aa-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="198aa-107">minimum: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="198aa-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="198aa-108">Nejmenší celé číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="198aa-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="198aa-109">maximum: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="198aa-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="198aa-110">Největší celé číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="198aa-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="198aa-111">Výstup: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="198aa-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="198aa-112">Distribuce, jejíž náhodná variates jsou celá čísla v rozsahu, od `min` do `max` s jednotnou pravděpodobností.</span><span class="sxs-lookup"><span data-stu-id="198aa-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="198aa-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="198aa-113">Remarks</span></span>

<span data-ttu-id="198aa-114">Dojde k chybě `max <= min` , pokud.</span><span class="sxs-lookup"><span data-stu-id="198aa-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="198aa-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="198aa-115">See Also</span></span>

- [<span data-ttu-id="198aa-116">Microsoft. DrawRandomDouble.</span><span class="sxs-lookup"><span data-stu-id="198aa-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)