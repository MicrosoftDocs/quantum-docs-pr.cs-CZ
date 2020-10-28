---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: Operace EstimateGradient
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: f42cc30c98346a25f584d7527227a95cb413c32b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706512"
---
# <a name="estimategradient-operation"></a><span data-ttu-id="9fc21-102">Operace EstimateGradient</span><span class="sxs-lookup"><span data-stu-id="9fc21-102">EstimateGradient operation</span></span>

<span data-ttu-id="9fc21-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="9fc21-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="9fc21-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9fc21-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9fc21-105">Odhadne školicí přechod pro sekvenční třídění na konkrétním modelu a pro daný kódovaný vstup.</span><span class="sxs-lookup"><span data-stu-id="9fc21-105">Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.</span></span>

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="9fc21-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="9fc21-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="9fc21-107">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="9fc21-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="9fc21-108">Sekvenční model, jehož přechod má být odhadnut.</span><span class="sxs-lookup"><span data-stu-id="9fc21-108">The sequential model whose gradient is to be estimated.</span></span>


### <a name="encodedinput--stategenerator"></a><span data-ttu-id="9fc21-109">encodedInput: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="9fc21-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="9fc21-110">Vstup do sekvenčního třídění, který je kódovaný na operaci přípravy stavu.</span><span class="sxs-lookup"><span data-stu-id="9fc21-110">An input to the sequential classifier, encoded into a state preparation operation.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="9fc21-111">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9fc21-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9fc21-112">Počet měření, která se mají použít při odhadování přechodu.</span><span class="sxs-lookup"><span data-stu-id="9fc21-112">The number of measurements to use in estimating the gradient.</span></span>



## <a name="output--double"></a><span data-ttu-id="9fc21-113">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9fc21-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9fc21-114">Odhad školicího přechodu v daných parametrech vstupu a modelu.</span><span class="sxs-lookup"><span data-stu-id="9fc21-114">An estimate of the training gradient at the given input and model parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="9fc21-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="9fc21-115">Remarks</span></span>

<span data-ttu-id="9fc21-116">Tato operace používá Hadamard test a parametr Shift pohromadě k odhadu přechodu.</span><span class="sxs-lookup"><span data-stu-id="9fc21-116">This operation uses a Hadamard test and the parameter shift technique together to estimate the gradient.</span></span>