---
uid: Microsoft.Quantum.Random.DrawCategorical
title: Operace DrawCategorical
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a5826aa5f658fea766db0ca5ccbb9c0d7d056d4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192991"
---
# <a name="drawcategorical-operation"></a><span data-ttu-id="a01b4-102">Operace DrawCategorical</span><span class="sxs-lookup"><span data-stu-id="a01b4-102">DrawCategorical operation</span></span>

<span data-ttu-id="a01b4-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="a01b4-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="a01b4-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a01b4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a01b4-105">Nakreslí náhodný vzorek z kategorií distribuce určené seznamem probablities.</span><span class="sxs-lookup"><span data-stu-id="a01b4-105">Draws a random sample from a categorical distribution specified by a list of probablities.</span></span>

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a><span data-ttu-id="a01b4-106">Popis</span><span class="sxs-lookup"><span data-stu-id="a01b4-106">Description</span></span>

<span data-ttu-id="a01b4-107">Pravděpodobnost výběru konkrétního indexu je úměrná hodnotě prvku pole v daném indexu.</span><span class="sxs-lookup"><span data-stu-id="a01b4-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span>
<span data-ttu-id="a01b4-108">Prvky pole, které jsou rovny nule, se ignorují a jejich indexy se nikdy nevrátí.</span><span class="sxs-lookup"><span data-stu-id="a01b4-108">Array elements that are equal to zero are ignored and their indices are never returned.</span></span> <span data-ttu-id="a01b4-109">Pokud je některý prvek pole menší než nula, nebo pokud žádný element pole není větší než nula, operace se nezdařila.</span><span class="sxs-lookup"><span data-stu-id="a01b4-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>

## <a name="input"></a><span data-ttu-id="a01b4-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="a01b4-110">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="a01b4-111">sondy: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a01b4-111">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a01b4-112">Pole čísel s plovoucí desetinnou čárkou, které je úměrné pravděpodobnosti výběru každého indexu.</span><span class="sxs-lookup"><span data-stu-id="a01b4-112">An array of floating-point numbers proportional to the probability of selecting each index.</span></span>



## <a name="output--int"></a><span data-ttu-id="a01b4-113">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a01b4-113">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a01b4-114">Celé číslo $i $ s pravděpodobností $ \Pr (i) = p_i/\ sum_i p_i $, kde $p _i $ je prvek $i $ th `probs` .</span><span class="sxs-lookup"><span data-stu-id="a01b4-114">An integer $i$ with probability $\Pr(i) = p_i / \sum_i p_i$, where $p_i$ is the $i$th element of `probs`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a01b4-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="a01b4-115">See Also</span></span>

- [<span data-ttu-id="a01b4-116">Microsoft. prohodilá. CategoricalDistribution</span><span class="sxs-lookup"><span data-stu-id="a01b4-116">Microsoft.Quantum.Random.CategoricalDistribution</span></span>](xref:Microsoft.Quantum.Random.CategoricalDistribution)