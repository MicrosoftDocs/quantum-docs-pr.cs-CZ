---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: 74300efb10ba7b5aa006f0b1b6aafde0da840f00
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697140"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="ea7ef-102">ContinuousUniformDistribution – funkce</span><span class="sxs-lookup"><span data-stu-id="ea7ef-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="ea7ef-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="ea7ef-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="ea7ef-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ea7ef-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ea7ef-105">Vrátí jednotnou distribuci v rámci daného intervalu zahrnujícího interval.</span><span class="sxs-lookup"><span data-stu-id="ea7ef-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="ea7ef-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ea7ef-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="ea7ef-107">min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ea7ef-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ea7ef-108">Nejmenší reálné číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="ea7ef-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="ea7ef-109">Max: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ea7ef-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ea7ef-110">Největší reálné číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="ea7ef-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="ea7ef-111">Výstup: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="ea7ef-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="ea7ef-112">Distribuce, jejíž náhodná variates jsou skutečná čísla v intervalu zahrnujícím, od `min` do `max` s jednotnou pravděpodobností.</span><span class="sxs-lookup"><span data-stu-id="ea7ef-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="ea7ef-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ea7ef-113">Remarks</span></span>

<span data-ttu-id="ea7ef-114">Dojde k chybě `max <= min` , pokud.</span><span class="sxs-lookup"><span data-stu-id="ea7ef-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea7ef-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="ea7ef-115">See Also</span></span>

- [<span data-ttu-id="ea7ef-116">Microsoft. DrawRandomDouble.</span><span class="sxs-lookup"><span data-stu-id="ea7ef-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)