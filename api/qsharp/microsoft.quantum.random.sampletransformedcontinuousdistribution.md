---
uid: Microsoft.Quantum.Random.SampleTransformedContinuousDistribution
title: Operace SampleTransformedContinuousDistribution
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: SampleTransformedContinuousDistribution
qsharp.summary: Internal-only operation for sampling from transformed distributions. Should only be used via partial application.
ms.openlocfilehash: f9f2b3cbbb4423f267758976cd066abbfec93a77
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192685"
---
# <a name="sampletransformedcontinuousdistribution-operation"></a><span data-ttu-id="c561e-102">Operace SampleTransformedContinuousDistribution</span><span class="sxs-lookup"><span data-stu-id="c561e-102">SampleTransformedContinuousDistribution operation</span></span>

<span data-ttu-id="c561e-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="c561e-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="c561e-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c561e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c561e-105">Operace pouze interní pro vzorkování z transformovaných distribucí.</span><span class="sxs-lookup"><span data-stu-id="c561e-105">Internal-only operation for sampling from transformed distributions.</span></span>
<span data-ttu-id="c561e-106">By měla být použita pouze prostřednictvím částečné aplikace.</span><span class="sxs-lookup"><span data-stu-id="c561e-106">Should only be used via partial application.</span></span>

```qsharp
operation SampleTransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Double
```


## <a name="input"></a><span data-ttu-id="c561e-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="c561e-107">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="c561e-108">Transform: [Dvojitá](xref:microsoft.quantum.lang-ref.double) -> [Dvojitá přesnost](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c561e-108">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="distribution--continuousdistribution"></a><span data-ttu-id="c561e-109">distribuce: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="c561e-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>





## <a name="output--double"></a><span data-ttu-id="c561e-110">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c561e-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

