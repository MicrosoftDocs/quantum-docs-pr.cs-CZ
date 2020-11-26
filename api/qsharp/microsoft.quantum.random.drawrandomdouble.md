---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Operace DrawRandomDouble
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: d62416f4a222716edb9393fe4f43731d0e8aa9d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192940"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="2fce5-102">Operace DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="2fce5-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="2fce5-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="2fce5-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="2fce5-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2fce5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2fce5-105">Vykreslí náhodné reálné číslo v daném intervalu.</span><span class="sxs-lookup"><span data-stu-id="2fce5-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="2fce5-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2fce5-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="2fce5-107">min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2fce5-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2fce5-108">Nejmenší reálné číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="2fce5-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="2fce5-109">Max: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2fce5-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2fce5-110">Největší reálné číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="2fce5-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="2fce5-111">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2fce5-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2fce5-112">Náhodné reálné číslo v intervalu zahrnujícím v rámci `min` `max` s jednotnou pravděpodobností.</span><span class="sxs-lookup"><span data-stu-id="2fce5-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="2fce5-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2fce5-113">Remarks</span></span>

<span data-ttu-id="2fce5-114">Dojde k chybě `max <= min` , pokud.</span><span class="sxs-lookup"><span data-stu-id="2fce5-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2fce5-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="2fce5-115">See Also</span></span>

- [<span data-ttu-id="2fce5-116">Microsoft. ContinuousUniformDistribution.</span><span class="sxs-lookup"><span data-stu-id="2fce5-116">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)