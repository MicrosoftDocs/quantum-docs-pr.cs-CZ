---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697572"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="8abd1-102">TransformedContinuousDistribution – funkce</span><span class="sxs-lookup"><span data-stu-id="8abd1-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="8abd1-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="8abd1-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="8abd1-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8abd1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8abd1-105">S ohledem na průběžnou distribuci vrátí novou distribuci, která transformuje originál pomocí dané funkce.</span><span class="sxs-lookup"><span data-stu-id="8abd1-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="8abd1-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="8abd1-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="8abd1-107">Transform: [Dvojitá](xref:microsoft.quantum.lang-ref.double) -> [Dvojitá přesnost](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8abd1-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8abd1-108">Funkce, která transformuje variates původního rozdělení do transformované distribuce.</span><span class="sxs-lookup"><span data-stu-id="8abd1-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="8abd1-109">distribuce: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="8abd1-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="8abd1-110">Původní distribuce, která se má transformovat.</span><span class="sxs-lookup"><span data-stu-id="8abd1-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="8abd1-111">Výstup: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="8abd1-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="8abd1-112">Nové rozdělení související s transformací, kterou `distribution` předává `transform` .</span><span class="sxs-lookup"><span data-stu-id="8abd1-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>