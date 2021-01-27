---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 754ada71078bd5446f78885ace31d92dce6bf1a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842348"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="55b9a-102">CategoricalDistribution – funkce</span><span class="sxs-lookup"><span data-stu-id="55b9a-102">CategoricalDistribution function</span></span>

<span data-ttu-id="55b9a-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="55b9a-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="55b9a-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="55b9a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="55b9a-105">Vrátí samostatnou distribuci kategorií, ve které je explicitně určena pravděpodobnost pro každý konečný seznam daných výsledků.</span><span class="sxs-lookup"><span data-stu-id="55b9a-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="55b9a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="55b9a-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="55b9a-107">sondy: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="55b9a-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="55b9a-108">Pravděpodobnost pro každý výsledek kategorií rozdělení.</span><span class="sxs-lookup"><span data-stu-id="55b9a-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="55b9a-109">Tyto pravděpodobnosti nemusí být normalizovány, ale musí být všechny nezáporné.</span><span class="sxs-lookup"><span data-stu-id="55b9a-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="55b9a-110">Výstup: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="55b9a-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="55b9a-111">Index `i` s pravděpodobností `probs[i] / sum` , kde `sum` je součet `probs` vydaný pomocí `Fold(PlusD, 0.0, probs)` .</span><span class="sxs-lookup"><span data-stu-id="55b9a-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>

## <a name="example"></a><span data-ttu-id="55b9a-112">Příklad</span><span class="sxs-lookup"><span data-stu-id="55b9a-112">Example</span></span>

<span data-ttu-id="55b9a-113">Následující kód Q # bude zobrazovat 0 s pravděpodobností 30% a 1 s pravděpodobností 70%:</span><span class="sxs-lookup"><span data-stu-id="55b9a-113">The following Q# code will display 0 with probability 30% and 1 with probability 70%:</span></span>

```qsharp
let dist = CategoricalDistribution([0.3, 0.7]);
Message($"Got sample: {dist::Sample()}");
```