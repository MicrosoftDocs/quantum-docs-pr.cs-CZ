---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: b64bb1ec52d2456ee1b627b920890223d173533b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211776"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="7746e-102">InferredLabel – funkce</span><span class="sxs-lookup"><span data-stu-id="7746e-102">InferredLabel function</span></span>

<span data-ttu-id="7746e-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7746e-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="7746e-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7746e-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="7746e-105">S ohledem na pravděpodobnost klasifikace a bias vrátí popisek odvozený z této pravděpodobnosti.</span><span class="sxs-lookup"><span data-stu-id="7746e-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="7746e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="7746e-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="7746e-107">bias: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7746e-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7746e-108">Posun mezi dvěma třídami, obvykle výsledek školení klasifikátoru.</span><span class="sxs-lookup"><span data-stu-id="7746e-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="7746e-109">pravděpodobnost: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7746e-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7746e-110">Pravděpodobnost klasifikace pro konkrétní vzorek, obvykle vyplývají z odhadu jeho četnosti klasifikace.</span><span class="sxs-lookup"><span data-stu-id="7746e-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="7746e-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7746e-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7746e-112">Popisek odvozený od zadané pravděpodobnosti klasifikace.</span><span class="sxs-lookup"><span data-stu-id="7746e-112">The label inferred from the given classification probability.</span></span>