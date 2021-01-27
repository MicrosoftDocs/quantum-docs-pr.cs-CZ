---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: Operace EstimateGradient
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: 38edcb67e7dcc5d2e971fb507a792937774a702c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844381"
---
# <a name="estimategradient-operation"></a><span data-ttu-id="ed83f-102">Operace EstimateGradient</span><span class="sxs-lookup"><span data-stu-id="ed83f-102">EstimateGradient operation</span></span>

<span data-ttu-id="ed83f-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ed83f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="ed83f-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ed83f-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="ed83f-105">Odhadne školicí přechod pro sekvenční třídění na konkrétním modelu a pro daný kódovaný vstup.</span><span class="sxs-lookup"><span data-stu-id="ed83f-105">Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.</span></span>

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="ed83f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ed83f-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="ed83f-107">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="ed83f-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="ed83f-108">Sekvenční model, jehož přechod má být odhadnut.</span><span class="sxs-lookup"><span data-stu-id="ed83f-108">The sequential model whose gradient is to be estimated.</span></span>


### <a name="encodedinput--stategenerator"></a><span data-ttu-id="ed83f-109">encodedInput: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="ed83f-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="ed83f-110">Vstup do sekvenčního třídění, který je kódovaný na operaci přípravy stavu.</span><span class="sxs-lookup"><span data-stu-id="ed83f-110">An input to the sequential classifier, encoded into a state preparation operation.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="ed83f-111">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ed83f-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ed83f-112">Počet měření, která se mají použít při odhadování přechodu.</span><span class="sxs-lookup"><span data-stu-id="ed83f-112">The number of measurements to use in estimating the gradient.</span></span>



## <a name="output--double"></a><span data-ttu-id="ed83f-113">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ed83f-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ed83f-114">Odhad školicího přechodu v daných parametrech vstupu a modelu.</span><span class="sxs-lookup"><span data-stu-id="ed83f-114">An estimate of the training gradient at the given input and model parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="ed83f-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ed83f-115">Remarks</span></span>

<span data-ttu-id="ed83f-116">Tato operace používá Hadamard test a parametr Shift pohromadě k odhadu přechodu.</span><span class="sxs-lookup"><span data-stu-id="ed83f-116">This operation uses a Hadamard test and the parameter shift technique together to estimate the gradient.</span></span>