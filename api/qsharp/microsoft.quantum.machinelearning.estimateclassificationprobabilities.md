---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: Operace EstimateClassificationProbabilities
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 1cd56f6a6483b00afb168f8d84301e73eae9af65
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211895"
---
# <a name="estimateclassificationprobabilities-operation"></a><span data-ttu-id="a498d-102">Operace EstimateClassificationProbabilities</span><span class="sxs-lookup"><span data-stu-id="a498d-102">EstimateClassificationProbabilities operation</span></span>

<span data-ttu-id="a498d-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a498d-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a498d-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a498d-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="a498d-105">Vzhledem k sadě vzorků a sekvenčnímu třídění odhadne pravděpodobnost klasifikace těchto vzorků opakovaným měřením výstupu klasifikátoru v každé ukázce.</span><span class="sxs-lookup"><span data-stu-id="a498d-105">Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.</span></span>

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="a498d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="a498d-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="a498d-107">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a498d-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a498d-108">Tolerance, která umožňuje v kódování vzorku do operace přípravy stavu.</span><span class="sxs-lookup"><span data-stu-id="a498d-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="a498d-109">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="a498d-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="a498d-110">Sekvenční model, který se použije k odhadu pravděpodobnosti klasifikace pro dané vzorky.</span><span class="sxs-lookup"><span data-stu-id="a498d-110">The sequential model to be used to estimate the classification probabilities for the given samples.</span></span>


### <a name="samples--double"></a><span data-ttu-id="a498d-111">Samples: [Double](xref:microsoft.quantum.lang-ref.double)[] []</span><span class="sxs-lookup"><span data-stu-id="a498d-111">samples : [Double](xref:microsoft.quantum.lang-ref.double)[][]</span></span>

<span data-ttu-id="a498d-112">Pole vektorů funkcí pro každý vzorek, který má být klasifikován.</span><span class="sxs-lookup"><span data-stu-id="a498d-112">An array of feature vectors for each sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="a498d-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a498d-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a498d-114">Počet měření, která se mají použít při odhadu pravděpodobnosti klasifikace.</span><span class="sxs-lookup"><span data-stu-id="a498d-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="a498d-115">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a498d-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a498d-116">Pole odhadů pravděpodobnosti klasifikace pro každou danou ukázku.</span><span class="sxs-lookup"><span data-stu-id="a498d-116">An array of estimates of the classification probability for each given sample.</span></span>