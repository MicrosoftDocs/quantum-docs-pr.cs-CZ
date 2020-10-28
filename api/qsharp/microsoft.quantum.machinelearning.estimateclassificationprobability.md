---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: Operace EstimateClassificationProbability
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 79e40bc4bc0954dc6742307122609950bf22ec71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697237"
---
# <a name="estimateclassificationprobability-operation"></a><span data-ttu-id="0bdc8-102">Operace EstimateClassificationProbability</span><span class="sxs-lookup"><span data-stu-id="0bdc8-102">EstimateClassificationProbability operation</span></span>

<span data-ttu-id="0bdc8-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0bdc8-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="0bdc8-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0bdc8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0bdc8-105">Vzhledem k ukázce a sekvenčnímu třídění odhadne pravděpodobnost klasifikace pro tento vzorek opakovaným měřením výstupu klasifikátoru v dané ukázce.</span><span class="sxs-lookup"><span data-stu-id="0bdc8-105">Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.</span></span>

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="0bdc8-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="0bdc8-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="0bdc8-107">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0bdc8-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0bdc8-108">Tolerance, která umožňuje v kódování vzorku do operace přípravy stavu.</span><span class="sxs-lookup"><span data-stu-id="0bdc8-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="0bdc8-109">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="0bdc8-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="0bdc8-110">Sekvenční model, který má být použit k odhadu pravděpodobnosti klasifikace pro danou ukázku.</span><span class="sxs-lookup"><span data-stu-id="0bdc8-110">The sequential model to be used to estimate the classification probability for the given sample.</span></span>


### <a name="sample--double"></a><span data-ttu-id="0bdc8-111">Ukázka: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="0bdc8-111">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="0bdc8-112">Vektor funkce pro ukázku, která má být klasifikována</span><span class="sxs-lookup"><span data-stu-id="0bdc8-112">The feature vector for the sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="0bdc8-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0bdc8-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0bdc8-114">Počet měření, která se mají použít při odhadu pravděpodobnosti klasifikace.</span><span class="sxs-lookup"><span data-stu-id="0bdc8-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="0bdc8-115">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0bdc8-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0bdc8-116">Odhad pravděpodobnosti klasifikace pro danou ukázku.</span><span class="sxs-lookup"><span data-stu-id="0bdc8-116">An estimate of the classification probability for the given sample.</span></span>