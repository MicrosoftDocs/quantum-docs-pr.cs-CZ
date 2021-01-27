---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: Operace MaybeChooseElement
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 86a69110fc92a2b6238cc757c09185c9fbcdb035
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856111"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="a9a31-102">Operace MaybeChooseElement</span><span class="sxs-lookup"><span data-stu-id="a9a31-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="a9a31-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="a9a31-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="a9a31-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a9a31-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a9a31-105">V případě pole dat a distribuce v rámci indexů se pokusí zvolit element náhodně.</span><span class="sxs-lookup"><span data-stu-id="a9a31-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="a9a31-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="a9a31-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="a9a31-107">data: t []</span><span class="sxs-lookup"><span data-stu-id="a9a31-107">data : 'T[]</span></span>

<span data-ttu-id="a9a31-108">Pole, ze kterého se má vybrat element</span><span class="sxs-lookup"><span data-stu-id="a9a31-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="a9a31-109">indexDistribution: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="a9a31-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="a9a31-110">Rozdělení na indexy `data` .</span><span class="sxs-lookup"><span data-stu-id="a9a31-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="a9a31-111">Výstup: ([bool](xref:microsoft.quantum.lang-ref.bool), t)</span><span class="sxs-lookup"><span data-stu-id="a9a31-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a9a31-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a9a31-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a9a31-113">'S</span><span class="sxs-lookup"><span data-stu-id="a9a31-113">'T</span></span>



## <a name="example"></a><span data-ttu-id="a9a31-114">Příklad</span><span class="sxs-lookup"><span data-stu-id="a9a31-114">Example</span></span>

<span data-ttu-id="a9a31-115">Následující fragment Q # vybírá element náhodně z pole:</span><span class="sxs-lookup"><span data-stu-id="a9a31-115">The following Q# snippet chooses an element at random from an array:</span></span>

```qsharp
let (succeeded, element) = MaybeChooseElement(
    data,
    DiscreteUniformDistribution(0, Length(data) - 1)
);
Fact(succeeded, "Index chosen by MaybeChooseElement was not valid.");
```