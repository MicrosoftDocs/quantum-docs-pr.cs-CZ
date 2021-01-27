---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: f909e7def5439ec0feef4ca4dc0cf8ed12374dfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853724"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="cc22c-102">DiscreteUniformDistribution – funkce</span><span class="sxs-lookup"><span data-stu-id="cc22c-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="cc22c-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="cc22c-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="cc22c-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="cc22c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="cc22c-105">Vrátí jednotnou distribuci v rámci daného celkového rozsahu.</span><span class="sxs-lookup"><span data-stu-id="cc22c-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="cc22c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="cc22c-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="cc22c-107">minimum: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cc22c-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cc22c-108">Nejmenší celé číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="cc22c-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="cc22c-109">maximum: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cc22c-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cc22c-110">Největší celé číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="cc22c-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="cc22c-111">Výstup: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="cc22c-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="cc22c-112">Distribuce, jejíž náhodná variates jsou celá čísla v rozsahu, od `min` do `max` s jednotnou pravděpodobností.</span><span class="sxs-lookup"><span data-stu-id="cc22c-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="cc22c-113">Příklad</span><span class="sxs-lookup"><span data-stu-id="cc22c-113">Example</span></span>

<span data-ttu-id="cc22c-114">Následující fragment Q # náhodně zavede na šestou kostku:</span><span class="sxs-lookup"><span data-stu-id="cc22c-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let dieDistribution = DiscreteUniformDistribution(1, 6);
let dieRoll = dieDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="cc22c-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="cc22c-115">Remarks</span></span>

<span data-ttu-id="cc22c-116">Dojde k chybě `max <= min` , pokud.</span><span class="sxs-lookup"><span data-stu-id="cc22c-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc22c-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="cc22c-117">See Also</span></span>

- [<span data-ttu-id="cc22c-118">Microsoft. DrawRandomDouble.</span><span class="sxs-lookup"><span data-stu-id="cc22c-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)