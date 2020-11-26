---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingEpoch
title: Operace _RunSingleTrainingEpoch
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingEpoch
qsharp.summary: Perform one epoch of sequential classifier training on a subset of data samples.
ms.openlocfilehash: 71780645a025972f11f32f8ba8fd94d098604f9e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196748"
---
# <a name="_runsingletrainingepoch-operation"></a><span data-ttu-id="e1547-102">Operace _RunSingleTrainingEpoch</span><span class="sxs-lookup"><span data-stu-id="e1547-102">_RunSingleTrainingEpoch operation</span></span>

<span data-ttu-id="e1547-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e1547-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="e1547-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e1547-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="e1547-105">Proveďte jednu epocha sekvenčního školení třídění na podmnožinu ukázek dat.</span><span class="sxs-lookup"><span data-stu-id="e1547-105">Perform one epoch of sequential classifier training on a subset of data samples.</span></span>

```qsharp
operation _RunSingleTrainingEpoch (encodedSamples : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, periodScore : Int, options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel, nPreviousBestMisses : Int) : (Int, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a><span data-ttu-id="e1547-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e1547-106">Input</span></span>

### <a name="encodedsamples--labeledsamplestategenerator"></a><span data-ttu-id="e1547-107">encodedSamples: ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []</span><span class="sxs-lookup"><span data-stu-id="e1547-107">encodedSamples : ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator))[]</span></span>




### <a name="schedule--samplingschedule"></a><span data-ttu-id="e1547-108">plán: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="e1547-108">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>




### <a name="periodscore--int"></a><span data-ttu-id="e1547-109">periodScore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e1547-109">periodScore : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e1547-110">Počet kroků přechodu mezi body bodování.</span><span class="sxs-lookup"><span data-stu-id="e1547-110">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="e1547-111">Pro nejlepší přesnost nastavte na hodnotu 1.</span><span class="sxs-lookup"><span data-stu-id="e1547-111">For best accuracy, set to 1.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="e1547-112">možnosti: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="e1547-112">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="e1547-113">Možnosti, které se mají použít při školení</span><span class="sxs-lookup"><span data-stu-id="e1547-113">Options to be used in training.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="e1547-114">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="e1547-114">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="e1547-115">Sekvenční model, který se má vyškolet</span><span class="sxs-lookup"><span data-stu-id="e1547-115">The sequential model to be trained.</span></span>


### <a name="npreviousbestmisses--int"></a><span data-ttu-id="e1547-116">nPreviousBestMisses: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e1547-116">nPreviousBestMisses : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e1547-117">Nejlepší počet chybných klasifikací zjištěných v předchozích epochs.</span><span class="sxs-lookup"><span data-stu-id="e1547-117">The best number of misclassifications observed in previous epochs.</span></span>



## <a name="output--intsequentialmodel"></a><span data-ttu-id="e1547-118">Výstup: ([int](xref:microsoft.quantum.lang-ref.int);[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span><span class="sxs-lookup"><span data-stu-id="e1547-118">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span></span>

- <span data-ttu-id="e1547-119">Nejmenší počet chybných klasifikací pozorovaných do tohoto epocha.</span><span class="sxs-lookup"><span data-stu-id="e1547-119">The smallest number of misclassifications observed through to this epoch.</span></span>
- <span data-ttu-id="e1547-120">Byl nalezen nový nejlepší sekvenční model.</span><span class="sxs-lookup"><span data-stu-id="e1547-120">The new best sequential model found.</span></span>