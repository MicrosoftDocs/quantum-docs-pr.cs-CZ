---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 1d6edec94f731fe96da797f0c3d77e6eba565149
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708014"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="d5b81-102">InferredLabel – funkce</span><span class="sxs-lookup"><span data-stu-id="d5b81-102">InferredLabel function</span></span>

<span data-ttu-id="d5b81-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d5b81-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="d5b81-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d5b81-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d5b81-105">S ohledem na pravděpodobnost klasifikace a bias vrátí popisek odvozený z této pravděpodobnosti.</span><span class="sxs-lookup"><span data-stu-id="d5b81-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="d5b81-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="d5b81-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="d5b81-107">bias: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d5b81-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d5b81-108">Posun mezi dvěma třídami, obvykle výsledek školení klasifikátoru.</span><span class="sxs-lookup"><span data-stu-id="d5b81-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="d5b81-109">pravděpodobnost: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d5b81-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d5b81-110">Pravděpodobnost klasifikace pro konkrétní vzorek, obvykle vyplývají z odhadu jeho četnosti klasifikace.</span><span class="sxs-lookup"><span data-stu-id="d5b81-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="d5b81-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d5b81-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d5b81-112">Popisek odvozený od zadané pravděpodobnosti klasifikace.</span><span class="sxs-lookup"><span data-stu-id="d5b81-112">The label inferred from the given classification probability.</span></span>