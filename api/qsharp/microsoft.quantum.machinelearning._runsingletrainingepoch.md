---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingEpoch
title: Operace _RunSingleTrainingEpoch
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingEpoch
qsharp.summary: Perform one epoch of sequential classifier training on a subset of data samples.
ms.openlocfilehash: a8ae35fdd6c4e219444e7d6f7587ea31603b9999
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856183"
---
# <a name="_runsingletrainingepoch-operation"></a><span data-ttu-id="333f8-102">Operace _RunSingleTrainingEpoch</span><span class="sxs-lookup"><span data-stu-id="333f8-102">_RunSingleTrainingEpoch operation</span></span>

<span data-ttu-id="333f8-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="333f8-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="333f8-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="333f8-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="333f8-105">Proveďte jednu epocha sekvenčního školení třídění na podmnožinu ukázek dat.</span><span class="sxs-lookup"><span data-stu-id="333f8-105">Perform one epoch of sequential classifier training on a subset of data samples.</span></span>

```qsharp
operation _RunSingleTrainingEpoch (encodedSamples : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, periodScore : Int, options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel, nPreviousBestMisses : Int) : (Int, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a><span data-ttu-id="333f8-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="333f8-106">Input</span></span>

### <a name="encodedsamples--labeledsamplestategenerator"></a><span data-ttu-id="333f8-107">encodedSamples: ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []</span><span class="sxs-lookup"><span data-stu-id="333f8-107">encodedSamples : ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator))[]</span></span>




### <a name="schedule--samplingschedule"></a><span data-ttu-id="333f8-108">plán: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="333f8-108">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>




### <a name="periodscore--int"></a><span data-ttu-id="333f8-109">periodScore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="333f8-109">periodScore : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="333f8-110">Počet kroků přechodu mezi body bodování.</span><span class="sxs-lookup"><span data-stu-id="333f8-110">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="333f8-111">Pro nejlepší přesnost nastavte na hodnotu 1.</span><span class="sxs-lookup"><span data-stu-id="333f8-111">For best accuracy, set to 1.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="333f8-112">možnosti: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="333f8-112">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="333f8-113">Možnosti, které se mají použít při školení</span><span class="sxs-lookup"><span data-stu-id="333f8-113">Options to be used in training.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="333f8-114">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="333f8-114">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="333f8-115">Sekvenční model, který se má vyškolet</span><span class="sxs-lookup"><span data-stu-id="333f8-115">The sequential model to be trained.</span></span>


### <a name="npreviousbestmisses--int"></a><span data-ttu-id="333f8-116">nPreviousBestMisses: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="333f8-116">nPreviousBestMisses : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="333f8-117">Nejlepší počet chybných klasifikací zjištěných v předchozích epochs.</span><span class="sxs-lookup"><span data-stu-id="333f8-117">The best number of misclassifications observed in previous epochs.</span></span>



## <a name="output--intsequentialmodel"></a><span data-ttu-id="333f8-118">Výstup: ([int](xref:microsoft.quantum.lang-ref.int);[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span><span class="sxs-lookup"><span data-stu-id="333f8-118">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span></span>

- <span data-ttu-id="333f8-119">Nejmenší počet chybných klasifikací pozorovaných do tohoto epocha.</span><span class="sxs-lookup"><span data-stu-id="333f8-119">The smallest number of misclassifications observed through to this epoch.</span></span>
- <span data-ttu-id="333f8-120">Byl nalezen nový nejlepší sekvenční model.</span><span class="sxs-lookup"><span data-stu-id="333f8-120">The new best sequential model found.</span></span>