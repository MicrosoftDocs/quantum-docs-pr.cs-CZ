---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifier
title: Operace TrainSequentialClassifier
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifier
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set.
ms.openlocfilehash: d0b0587ffa93141739bcd6f39324571ffc28dacc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228657"
---
# <a name="trainsequentialclassifier-operation"></a><span data-ttu-id="ec242-102">Operace TrainSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="ec242-102">TrainSequentialClassifier operation</span></span>

<span data-ttu-id="ec242-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ec242-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="ec242-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ec242-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="ec242-105">Vzhledem k struktuře sekvenčního klasifikátoru vlaky zajišťují třídění na dané sadě školení s označením.</span><span class="sxs-lookup"><span data-stu-id="ec242-105">Given the structure of a sequential classifier, trains the classifier on a given labeled training set.</span></span>

```qsharp
operation TrainSequentialClassifier (models : Microsoft.Quantum.MachineLearning.SequentialModel[], samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a><span data-ttu-id="ec242-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ec242-106">Input</span></span>

### <a name="models--sequentialmodel"></a><span data-ttu-id="ec242-107">modely: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]</span><span class="sxs-lookup"><span data-stu-id="ec242-107">models : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]</span></span>

<span data-ttu-id="ec242-108">Pole modelů, které se mají použít jako počáteční body během školení.</span><span class="sxs-lookup"><span data-stu-id="ec242-108">An array of models to be used as starting points during training.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="ec242-109">Ukázky: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="ec242-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="ec242-110">Sada přidaných školicích dat, která se budou používat k provádění školení.</span><span class="sxs-lookup"><span data-stu-id="ec242-110">A set of labeled training data that will be used to perform training.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="ec242-111">možnosti: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="ec242-111">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="ec242-112">Konfigurace, která se má použít při školení; Další podrobnosti najdete v tématu @"microsoft.quantum.machinelearning.trainingoptions" a @"microsoft.quantum.machinelearning.defaulttrainingoptions" .</span><span class="sxs-lookup"><span data-stu-id="ec242-112">Configuration to be used when training; see @"microsoft.quantum.machinelearning.trainingoptions" and @"microsoft.quantum.machinelearning.defaulttrainingoptions" for more details.</span></span>


### <a name="trainingschedule--samplingschedule"></a><span data-ttu-id="ec242-113">trainingSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="ec242-113">trainingSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="ec242-114">Plán vzorkování, který se má použít při výběru ukázek z školicích dat během postupu školení.</span><span class="sxs-lookup"><span data-stu-id="ec242-114">A sampling schedule to use when selecting samples from the training data during training steps.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="ec242-115">validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="ec242-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="ec242-116">Plán vzorkování, který se má použít při výběru ukázek z školicích dat při výběru počátečního bodu, který vedlo k nejlepšímu skóre třídění.</span><span class="sxs-lookup"><span data-stu-id="ec242-116">A sampling schedule to use when selecting samples from the training data when selecting which start point resulted in the best classifier score.</span></span>



## <a name="output--sequentialmodelint"></a><span data-ttu-id="ec242-117">Výstup: ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="ec242-117">Output : ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

- <span data-ttu-id="ec242-118">Parametrizace daného klasifikátoru a bias mezi dvěma třídami, společně odpovídající nejlepšímu výsledku z každého z daných počátečních bodů.</span><span class="sxs-lookup"><span data-stu-id="ec242-118">A parameterization of the given classifier and a bias between the two classes, together corresponding to the best result from each of the given start points.</span></span>
- <span data-ttu-id="ec242-119">Počet neúspěšných přístupů zjištěných v nejlepším modelu třídění.</span><span class="sxs-lookup"><span data-stu-id="ec242-119">The number of misses observed at the best classifier model.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec242-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="ec242-120">See Also</span></span>

- [<span data-ttu-id="ec242-121">Microsoft. MachineLearning. TrainSequentialClassifierAtModel</span><span class="sxs-lookup"><span data-stu-id="ec242-121">Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel</span></span>](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel)
- [<span data-ttu-id="ec242-122">Microsoft. MachineLearning. ValidateSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="ec242-122">Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier</span></span>](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)