---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: a3911fe9962ce18daa239de0272c53d83344134a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193076"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="b5b5c-102">ContinuousUniformDistribution – funkce</span><span class="sxs-lookup"><span data-stu-id="b5b5c-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="b5b5c-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="b5b5c-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="b5b5c-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b5b5c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b5b5c-105">Vrátí jednotnou distribuci v rámci daného intervalu zahrnujícího interval.</span><span class="sxs-lookup"><span data-stu-id="b5b5c-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="b5b5c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="b5b5c-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="b5b5c-107">min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b5b5c-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b5b5c-108">Nejmenší reálné číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="b5b5c-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="b5b5c-109">Max: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b5b5c-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b5b5c-110">Největší reálné číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="b5b5c-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="b5b5c-111">Výstup: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="b5b5c-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="b5b5c-112">Distribuce, jejíž náhodná variates jsou skutečná čísla v intervalu zahrnujícím, od `min` do `max` s jednotnou pravděpodobností.</span><span class="sxs-lookup"><span data-stu-id="b5b5c-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="b5b5c-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b5b5c-113">Remarks</span></span>

<span data-ttu-id="b5b5c-114">Dojde k chybě `max <= min` , pokud.</span><span class="sxs-lookup"><span data-stu-id="b5b5c-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5b5c-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="b5b5c-115">See Also</span></span>

- [<span data-ttu-id="b5b5c-116">Microsoft. DrawRandomDouble.</span><span class="sxs-lookup"><span data-stu-id="b5b5c-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)