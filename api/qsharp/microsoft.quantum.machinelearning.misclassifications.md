---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Funkce reklasifikace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 500c2910f7c5616c88ff6c70ab3cc16680e199fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708470"
---
# <a name="misclassifications-function"></a><span data-ttu-id="b0546-102">Funkce reklasifikace</span><span class="sxs-lookup"><span data-stu-id="b0546-102">Misclassifications function</span></span>

<span data-ttu-id="b0546-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b0546-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b0546-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b0546-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b0546-105">Vzhledem k sadě odvozených popisků a sadě správných popisků vrátí indexy pro, kde se každá sada popisků liší.</span><span class="sxs-lookup"><span data-stu-id="b0546-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="b0546-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="b0546-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="b0546-107">inferredLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b0546-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b0546-108">Popisky odvoditelné pro danou sadu školení nebo ověření.</span><span class="sxs-lookup"><span data-stu-id="b0546-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="b0546-109">actualLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b0546-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b0546-110">Značky true pro danou sadu školení nebo ověření.</span><span class="sxs-lookup"><span data-stu-id="b0546-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="b0546-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b0546-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b0546-112">Pole indexů `idx` , jako např `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="b0546-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>