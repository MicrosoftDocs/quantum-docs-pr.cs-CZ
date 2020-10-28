---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: Operace MaybeChooseElement
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 12640d9dc3aad301146eff7bcbbaae33d3ccd420
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707864"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="93168-102">Operace MaybeChooseElement</span><span class="sxs-lookup"><span data-stu-id="93168-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="93168-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="93168-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="93168-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="93168-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="93168-105">V případě pole dat a distribuce v rámci indexů se pokusí zvolit element náhodně.</span><span class="sxs-lookup"><span data-stu-id="93168-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="93168-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="93168-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="93168-107">data: t []</span><span class="sxs-lookup"><span data-stu-id="93168-107">data : 'T[]</span></span>

<span data-ttu-id="93168-108">Pole, ze kterého se má vybrat element</span><span class="sxs-lookup"><span data-stu-id="93168-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="93168-109">indexDistribution: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="93168-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="93168-110">Rozdělení na indexy `data` .</span><span class="sxs-lookup"><span data-stu-id="93168-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="93168-111">Výstup: ([bool](xref:microsoft.quantum.lang-ref.bool), t)</span><span class="sxs-lookup"><span data-stu-id="93168-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="93168-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="93168-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="93168-113">'S</span><span class="sxs-lookup"><span data-stu-id="93168-113">'T</span></span>

