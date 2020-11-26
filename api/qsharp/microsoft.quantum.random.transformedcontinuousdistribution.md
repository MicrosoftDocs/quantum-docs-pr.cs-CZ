---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: b317eaaa0ff0180ea5d240464c96d1c6b59c9c70
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226260"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="c8791-102">TransformedContinuousDistribution – funkce</span><span class="sxs-lookup"><span data-stu-id="c8791-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="c8791-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="c8791-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="c8791-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c8791-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c8791-105">S ohledem na průběžnou distribuci vrátí novou distribuci, která transformuje originál pomocí dané funkce.</span><span class="sxs-lookup"><span data-stu-id="c8791-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="c8791-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c8791-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="c8791-107">Transform: [Dvojitá](xref:microsoft.quantum.lang-ref.double) -> [Dvojitá přesnost](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c8791-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c8791-108">Funkce, která transformuje variates původního rozdělení do transformované distribuce.</span><span class="sxs-lookup"><span data-stu-id="c8791-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="c8791-109">distribuce: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="c8791-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="c8791-110">Původní distribuce, která se má transformovat.</span><span class="sxs-lookup"><span data-stu-id="c8791-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="c8791-111">Výstup: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="c8791-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="c8791-112">Nové rozdělení související s transformací, kterou `distribution` předává `transform` .</span><span class="sxs-lookup"><span data-stu-id="c8791-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>