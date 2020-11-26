---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Funkce reklasifikace
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: e13a9b9b65931678d5d87878e81fa172329a28ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211674"
---
# <a name="misclassifications-function"></a><span data-ttu-id="ebe90-102">Funkce reklasifikace</span><span class="sxs-lookup"><span data-stu-id="ebe90-102">Misclassifications function</span></span>

<span data-ttu-id="ebe90-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ebe90-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="ebe90-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ebe90-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="ebe90-105">Vzhledem k sadě odvozených popisků a sadě správných popisků vrátí indexy pro, kde se každá sada popisků liší.</span><span class="sxs-lookup"><span data-stu-id="ebe90-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="ebe90-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ebe90-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="ebe90-107">inferredLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ebe90-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ebe90-108">Popisky odvoditelné pro danou sadu školení nebo ověření.</span><span class="sxs-lookup"><span data-stu-id="ebe90-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="ebe90-109">actualLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ebe90-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ebe90-110">Značky true pro danou sadu školení nebo ověření.</span><span class="sxs-lookup"><span data-stu-id="ebe90-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="ebe90-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ebe90-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ebe90-112">Pole indexů `idx` , jako např `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="ebe90-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>