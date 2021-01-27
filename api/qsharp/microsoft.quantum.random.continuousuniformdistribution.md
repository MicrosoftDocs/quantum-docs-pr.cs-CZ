---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: c81eb433f50277c677756ee70d916f4856260c6d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842320"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="3e457-102">ContinuousUniformDistribution – funkce</span><span class="sxs-lookup"><span data-stu-id="3e457-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="3e457-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="3e457-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="3e457-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3e457-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3e457-105">Vrátí jednotnou distribuci v rámci daného intervalu zahrnujícího interval.</span><span class="sxs-lookup"><span data-stu-id="3e457-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="3e457-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="3e457-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="3e457-107">min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3e457-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3e457-108">Nejmenší reálné číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="3e457-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="3e457-109">Max: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3e457-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3e457-110">Největší reálné číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="3e457-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="3e457-111">Výstup: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="3e457-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="3e457-112">Distribuce, jejíž náhodná variates jsou skutečná čísla v intervalu zahrnujícím, od `min` do `max` s jednotnou pravděpodobností.</span><span class="sxs-lookup"><span data-stu-id="3e457-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="3e457-113">Příklad</span><span class="sxs-lookup"><span data-stu-id="3e457-113">Example</span></span>

<span data-ttu-id="3e457-114">Následující fragment Q # náhodně vykreslí úhel mezi $0 $ a $2 \pi $:</span><span class="sxs-lookup"><span data-stu-id="3e457-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angleDistribution = ContinuousUniformDistribution(0.0, 2.0 * PI());
let angle = angleDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="3e457-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="3e457-115">Remarks</span></span>

<span data-ttu-id="3e457-116">Dojde k chybě `max <= min` , pokud.</span><span class="sxs-lookup"><span data-stu-id="3e457-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e457-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="3e457-117">See Also</span></span>

- [<span data-ttu-id="3e457-118">Microsoft. DrawRandomDouble.</span><span class="sxs-lookup"><span data-stu-id="3e457-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)