---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 576b4b1f11fc21476bbb019d4b0326981294528c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848396"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="db328-102">InferredLabels – funkce</span><span class="sxs-lookup"><span data-stu-id="db328-102">InferredLabels function</span></span>

<span data-ttu-id="db328-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="db328-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="db328-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="db328-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="db328-105">Vzhledem k poli pravděpodobnosti klasifikace a posunu vrátí popisek odvozený od každé pravděpodobnosti.</span><span class="sxs-lookup"><span data-stu-id="db328-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="db328-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="db328-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="db328-107">bias: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="db328-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="db328-108">Posun mezi dvěma třídami, obvykle výsledek školení klasifikátoru.</span><span class="sxs-lookup"><span data-stu-id="db328-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="db328-109">pravděpodobnost: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="db328-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="db328-110">Pole pravděpodobnosti klasifikace pro sadu vzorků, která obvykle vede k odhadování frekvencí klasifikace.</span><span class="sxs-lookup"><span data-stu-id="db328-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="db328-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="db328-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="db328-112">Popisek odvozený od každé pravděpodobnosti klasifikace</span><span class="sxs-lookup"><span data-stu-id="db328-112">The label inferred from each classification probability.</span></span>