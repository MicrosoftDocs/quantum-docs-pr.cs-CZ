---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 756e9e95cac5554ab8f885dab7c47ac1b174c0f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708145"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="26601-102">CategoricalDistribution – funkce</span><span class="sxs-lookup"><span data-stu-id="26601-102">CategoricalDistribution function</span></span>

<span data-ttu-id="26601-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="26601-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="26601-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="26601-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="26601-105">Vrátí samostatnou distribuci kategorií, ve které je explicitně určena pravděpodobnost pro každý konečný seznam daných výsledků.</span><span class="sxs-lookup"><span data-stu-id="26601-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="26601-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="26601-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="26601-107">sondy: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="26601-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="26601-108">Pravděpodobnost pro každý výsledek kategorií rozdělení.</span><span class="sxs-lookup"><span data-stu-id="26601-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="26601-109">Tyto pravděpodobnosti nemusí být normalizovány, ale musí být všechny nezáporné.</span><span class="sxs-lookup"><span data-stu-id="26601-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="26601-110">Výstup: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="26601-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="26601-111">Index `i` s pravděpodobností `probs[i] / sum` , kde `sum` je součet `probs` vydaný pomocí `Fold(PlusD, 0.0, probs)` .</span><span class="sxs-lookup"><span data-stu-id="26601-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>