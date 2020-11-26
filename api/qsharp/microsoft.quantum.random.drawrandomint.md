---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Operace DrawRandomInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: f7b6cb75f761e4c45295245ed4bd4fb82c592809
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192906"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="cf842-102">Operace DrawRandomInt</span><span class="sxs-lookup"><span data-stu-id="cf842-102">DrawRandomInt operation</span></span>

<span data-ttu-id="cf842-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="cf842-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="cf842-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="cf842-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="cf842-105">Vykreslí náhodné celé číslo v daném rozsahu.</span><span class="sxs-lookup"><span data-stu-id="cf842-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="cf842-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="cf842-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="cf842-107">minimum: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cf842-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cf842-108">Nejmenší celé číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="cf842-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="cf842-109">maximum: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cf842-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cf842-110">Největší celé číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="cf842-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="cf842-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cf842-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cf842-112">Celé číslo v rozsahu v rozsahu od `min` do `max` s jednotnou pravděpodobností.</span><span class="sxs-lookup"><span data-stu-id="cf842-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="cf842-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="cf842-113">Remarks</span></span>

<span data-ttu-id="cf842-114">Dojde k chybě `max <= min` , pokud.</span><span class="sxs-lookup"><span data-stu-id="cf842-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf842-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="cf842-115">See Also</span></span>

- [<span data-ttu-id="cf842-116">Microsoft. DiscreteUniformDistribution.</span><span class="sxs-lookup"><span data-stu-id="cf842-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)