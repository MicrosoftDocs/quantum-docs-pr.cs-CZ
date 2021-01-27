---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: Uživatelem definovaný typ TrainingOptions
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 762d6853910832c6d4cda522c0c5df706d1ed195
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842769"
---
# <a name="trainingoptions-user-defined-type"></a><span data-ttu-id="213b4-102">Uživatelem definovaný typ TrainingOptions</span><span class="sxs-lookup"><span data-stu-id="213b4-102">TrainingOptions user defined type</span></span>

<span data-ttu-id="213b4-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="213b4-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="213b4-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="213b4-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="213b4-105">Kolekce možností, které se mají použít při výuce klasifikátorů</span><span class="sxs-lookup"><span data-stu-id="213b4-105">A collection of options to be used in training quantum classifiers.</span></span>

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a><span data-ttu-id="213b4-106">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="213b4-106">Named Items</span></span>

### <a name="learningrate--double"></a><span data-ttu-id="213b4-107">LearningRate: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="213b4-107">LearningRate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="213b4-108">Míra učení, podle které se při aktualizaci parametrů modelu během školicích kroků má změnit velikost přechodů.</span><span class="sxs-lookup"><span data-stu-id="213b4-108">The learning rate by which gradients should be rescaled when updating model parameters during training steps.</span></span>
### <a name="tolerance--double"></a><span data-ttu-id="213b4-109">Tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="213b4-109">Tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="213b4-110">Tolerance aproximace, která se má použít při přípravě ukázek jako stavové stavy.</span><span class="sxs-lookup"><span data-stu-id="213b4-110">The approximation tolerance to use when preparing samples as quantum states.</span></span>
### <a name="minibatchsize--int"></a><span data-ttu-id="213b4-111">MinibatchSize: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="213b4-111">MinibatchSize : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="213b4-112">Počet vzorků, které se mají použít při každém školení minibatch.</span><span class="sxs-lookup"><span data-stu-id="213b4-112">The number of samples to use in each training minibatch.</span></span>
### <a name="nmeasurements--int"></a><span data-ttu-id="213b4-113">NMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="213b4-113">NMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="213b4-114">Počet, kolikrát se má každý výsledek klasifikace změřit, aby se mohla odhadnout pravděpodobnost klasifikace</span><span class="sxs-lookup"><span data-stu-id="213b4-114">The number of times to measure each classification result in order to estimate the classification probability.</span></span>
### <a name="maxepochs--int"></a><span data-ttu-id="213b4-115">MaxEpochs: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="213b4-115">MaxEpochs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="213b4-116">Maximální počet epochs, pro které se mají vyškolit jednotlivé modely</span><span class="sxs-lookup"><span data-stu-id="213b4-116">The maximum number of epochs to train each model for.</span></span>
### <a name="maxstalls--int"></a><span data-ttu-id="213b4-117">MaxStalls: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="213b4-117">MaxStalls : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="213b4-118">Maximální počet pokusů, které epocha školení smí zablokovat (přibližně nula přechodu) před selháním.</span><span class="sxs-lookup"><span data-stu-id="213b4-118">The maximum number of times a training epoch is allowed to stall (approximately zero gradient) before failing.</span></span>
### <a name="stochasticrescalefactor--double"></a><span data-ttu-id="213b4-119">StochasticRescaleFactor: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="213b4-119">StochasticRescaleFactor : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="213b4-120">Množství, které má znovu škálovat zastavené modely, před opakováním aktualizace.</span><span class="sxs-lookup"><span data-stu-id="213b4-120">The amount to rescale stalled models by before retrying an update.</span></span>
### <a name="scoringperiod--int"></a><span data-ttu-id="213b4-121">ScoringPeriod: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="213b4-121">ScoringPeriod : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="213b4-122">Počet kroků přechodu mezi body bodování.</span><span class="sxs-lookup"><span data-stu-id="213b4-122">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="213b4-123">Pro nejlepší přesnost nastavte na hodnotu 1.</span><span class="sxs-lookup"><span data-stu-id="213b4-123">For best accuracy, set to 1.</span></span>
### <a name="verbosemessage--string---unit"></a><span data-ttu-id="213b4-124">VerboseMessage: [](xref:microsoft.quantum.lang-ref.string) -> [jednotka](xref:microsoft.quantum.lang-ref.unit) řetězce</span><span class="sxs-lookup"><span data-stu-id="213b4-124">VerboseMessage : [String](xref:microsoft.quantum.lang-ref.string) -> [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="213b4-125">Funkce, která může být použita k poskytnutí podrobné zpětné vazby.</span><span class="sxs-lookup"><span data-stu-id="213b4-125">A function that can be used to provide verbose feedback.</span></span>

## <a name="remarks"></a><span data-ttu-id="213b4-126">Poznámky</span><span class="sxs-lookup"><span data-stu-id="213b4-126">Remarks</span></span>

<span data-ttu-id="213b4-127">Tento parametr UDT by neměl být vytvořen přímo, ale je třeba jej zadat voláním @"microsoft.quantum.machinelearning.defaulttrainingoptions" a poté pomocí `w/` operátoru přepsat jiné výchozí hodnoty.</span><span class="sxs-lookup"><span data-stu-id="213b4-127">This UDT should not be created directly, but rather should be specified by calling @"microsoft.quantum.machinelearning.defaulttrainingoptions" and then using the `w/` operator to override different defaults.</span></span>

<span data-ttu-id="213b4-128">Například pro použití měření 100 000 a maximálně 8 školicích epochs:</span><span class="sxs-lookup"><span data-stu-id="213b4-128">For example, to use 100,000 measurements and at most 8 training epochs:</span></span>

```qsharp
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a><span data-ttu-id="213b4-129">Reference</span><span class="sxs-lookup"><span data-stu-id="213b4-129">References</span></span>

- [<span data-ttu-id="213b4-130">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="213b4-130">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)