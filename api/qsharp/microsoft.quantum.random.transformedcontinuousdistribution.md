---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 353442a4245a9e20bb1e4c46d2e8a84d4c9534b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857776"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="8b36f-102">TransformedContinuousDistribution – funkce</span><span class="sxs-lookup"><span data-stu-id="8b36f-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="8b36f-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="8b36f-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="8b36f-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8b36f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8b36f-105">S ohledem na průběžnou distribuci vrátí novou distribuci, která transformuje originál pomocí dané funkce.</span><span class="sxs-lookup"><span data-stu-id="8b36f-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="8b36f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="8b36f-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="8b36f-107">Transform: [Dvojitá](xref:microsoft.quantum.lang-ref.double) -> [Dvojitá přesnost](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8b36f-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8b36f-108">Funkce, která transformuje variates původního rozdělení do transformované distribuce.</span><span class="sxs-lookup"><span data-stu-id="8b36f-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="8b36f-109">distribuce: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="8b36f-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="8b36f-110">Původní distribuce, která se má transformovat.</span><span class="sxs-lookup"><span data-stu-id="8b36f-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="8b36f-111">Výstup: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="8b36f-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="8b36f-112">Nové rozdělení související s transformací, kterou `distribution` předává `transform` .</span><span class="sxs-lookup"><span data-stu-id="8b36f-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>

## <a name="example"></a><span data-ttu-id="8b36f-113">Příklad</span><span class="sxs-lookup"><span data-stu-id="8b36f-113">Example</span></span>

<span data-ttu-id="8b36f-114">Následující dvě distribuce jsou identické:</span><span class="sxs-lookup"><span data-stu-id="8b36f-114">The following two distributions are identical:</span></span>

```qsharp
let dist1 = ContinuousUniformDistribution(1.0, 2.0);
let dist2 = TransformedContinuousDistribution(
    PlusD(1.0, _),
    ContinuousUniformDistribution(0.0, 1.0)
);
```