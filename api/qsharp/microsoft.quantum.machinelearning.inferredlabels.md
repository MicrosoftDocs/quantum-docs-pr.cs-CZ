---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 874d1a2f7cc6d67567e0d2baa70b0d26b639a029
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708001"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="f39c5-102">InferredLabels – funkce</span><span class="sxs-lookup"><span data-stu-id="f39c5-102">InferredLabels function</span></span>

<span data-ttu-id="f39c5-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f39c5-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="f39c5-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f39c5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f39c5-105">Vzhledem k poli pravděpodobnosti klasifikace a posunu vrátí popisek odvozený od každé pravděpodobnosti.</span><span class="sxs-lookup"><span data-stu-id="f39c5-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="f39c5-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f39c5-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="f39c5-107">bias: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f39c5-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f39c5-108">Posun mezi dvěma třídami, obvykle výsledek školení klasifikátoru.</span><span class="sxs-lookup"><span data-stu-id="f39c5-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="f39c5-109">pravděpodobnost: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f39c5-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="f39c5-110">Pole pravděpodobnosti klasifikace pro sadu vzorků, která obvykle vede k odhadování frekvencí klasifikace.</span><span class="sxs-lookup"><span data-stu-id="f39c5-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="f39c5-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f39c5-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f39c5-112">Popisek odvozený od každé pravděpodobnosti klasifikace</span><span class="sxs-lookup"><span data-stu-id="f39c5-112">The label inferred from each classification probability.</span></span>