---
uid: Microsoft.Quantum.Random.SampleTransformedContinuousDistribution
title: Operace SampleTransformedContinuousDistribution
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: SampleTransformedContinuousDistribution
qsharp.summary: Internal-only operation for sampling from transformed distributions. Should only be used via partial application.
ms.openlocfilehash: dc93022e53199cd8ef794da9c1590d6997a0fda1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708638"
---
# <a name="sampletransformedcontinuousdistribution-operation"></a><span data-ttu-id="851d3-102">Operace SampleTransformedContinuousDistribution</span><span class="sxs-lookup"><span data-stu-id="851d3-102">SampleTransformedContinuousDistribution operation</span></span>

<span data-ttu-id="851d3-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="851d3-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="851d3-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="851d3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="851d3-105">Operace pouze interní pro vzorkování z transformovaných distribucí.</span><span class="sxs-lookup"><span data-stu-id="851d3-105">Internal-only operation for sampling from transformed distributions.</span></span>
<span data-ttu-id="851d3-106">By měla být použita pouze prostřednictvím částečné aplikace.</span><span class="sxs-lookup"><span data-stu-id="851d3-106">Should only be used via partial application.</span></span>

```qsharp
operation SampleTransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Double
```


## <a name="input"></a><span data-ttu-id="851d3-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="851d3-107">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="851d3-108">Transform: [Dvojitá](xref:microsoft.quantum.lang-ref.double) -> [Dvojitá přesnost](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="851d3-108">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="distribution--continuousdistribution"></a><span data-ttu-id="851d3-109">distribuce: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="851d3-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>





## <a name="output--double"></a><span data-ttu-id="851d3-110">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="851d3-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

