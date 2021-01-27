---
uid: Microsoft.Quantum.MachineLearning.DefaultTrainingOptions
title: DefaultTrainingOptions – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: DefaultTrainingOptions
qsharp.summary: Returns a default set of options for training classifiers.
ms.openlocfilehash: 474683ce5b9ec22bec686fb29d87728afe24d23a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855992"
---
# <a name="defaulttrainingoptions-function"></a><span data-ttu-id="01ab2-102">DefaultTrainingOptions – funkce</span><span class="sxs-lookup"><span data-stu-id="01ab2-102">DefaultTrainingOptions function</span></span>

<span data-ttu-id="01ab2-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="01ab2-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="01ab2-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="01ab2-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="01ab2-105">Vrátí výchozí sadu možností pro účely školení klasifikátorů.</span><span class="sxs-lookup"><span data-stu-id="01ab2-105">Returns a default set of options for training classifiers.</span></span>

```qsharp
function DefaultTrainingOptions () : Microsoft.Quantum.MachineLearning.TrainingOptions
```


## <a name="output--trainingoptions"></a><span data-ttu-id="01ab2-106">Výstup: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="01ab2-106">Output : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="01ab2-107">Přiměřená sada výchozích možností školení pro použití při výuce klasifikátorů.</span><span class="sxs-lookup"><span data-stu-id="01ab2-107">A reasonable set of default training options for use when training classifiers.</span></span>

## <a name="example"></a><span data-ttu-id="01ab2-108">Příklad</span><span class="sxs-lookup"><span data-stu-id="01ab2-108">Example</span></span>

<span data-ttu-id="01ab2-109">Chcete-li použít výchozí možnosti, ale s dalšími měřeními, použijte `w/` operátor:</span><span class="sxs-lookup"><span data-stu-id="01ab2-109">To use the default options, but with additional measurements, use the `w/` operator:</span></span>

```qsharp
let options = DefaultTrainingOptions()
    w/ NMeasurements <- 1000000;
```