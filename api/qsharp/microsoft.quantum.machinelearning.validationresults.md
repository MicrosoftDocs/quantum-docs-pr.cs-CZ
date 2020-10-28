---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: Uživatelem definovaný typ ValidationResults
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 1e54a5a086035f5f8d36d777badb306156d99600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706816"
---
# <a name="validationresults-user-defined-type"></a><span data-ttu-id="7e09e-102">Uživatelem definovaný typ ValidationResults</span><span class="sxs-lookup"><span data-stu-id="7e09e-102">ValidationResults user defined type</span></span>

<span data-ttu-id="7e09e-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7e09e-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="7e09e-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7e09e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7e09e-105">Výsledky z ověření klasifikátoru proti sadě vzorků.</span><span class="sxs-lookup"><span data-stu-id="7e09e-105">The results from having validated a classifier against a set of samples.</span></span>

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a><span data-ttu-id="7e09e-106">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="7e09e-106">Named Items</span></span>

### <a name="nmisclassifications--int"></a><span data-ttu-id="7e09e-107">NMisclassifications: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7e09e-107">NMisclassifications : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7e09e-108">Počet chybných klasifikací zjištěných během ověřování.</span><span class="sxs-lookup"><span data-stu-id="7e09e-108">The number of misclassifications observed during validation.</span></span>
### <a name="nvalidationsamples--int"></a><span data-ttu-id="7e09e-109">NValidationSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7e09e-109">NValidationSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

