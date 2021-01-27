---
uid: Microsoft.Quantum.Random.NormalDistribution
title: NormalDistribution – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: NormalDistribution
qsharp.summary: Returns a normal distribution with a given mean and variance.
ms.openlocfilehash: 733a2763dca6d75f81d538f63c3084331a8e1d51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814187"
---
# <a name="normaldistribution-function"></a><span data-ttu-id="81234-102">NormalDistribution – funkce</span><span class="sxs-lookup"><span data-stu-id="81234-102">NormalDistribution function</span></span>

<span data-ttu-id="81234-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="81234-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="81234-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="81234-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="81234-105">Vrací normální rozdělení s daným významem a odchylkou.</span><span class="sxs-lookup"><span data-stu-id="81234-105">Returns a normal distribution with a given mean and variance.</span></span>

```qsharp
function NormalDistribution (mean : Double, variance : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="81234-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="81234-106">Input</span></span>

### <a name="mean--double"></a><span data-ttu-id="81234-107">střední hodnota: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="81234-107">mean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="variance--double"></a><span data-ttu-id="81234-108">Variance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="81234-108">variance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--continuousdistribution"></a><span data-ttu-id="81234-109">Výstup: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="81234-109">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>



## <a name="example"></a><span data-ttu-id="81234-110">Příklad</span><span class="sxs-lookup"><span data-stu-id="81234-110">Example</span></span>

<span data-ttu-id="81234-111">Následující kreslí 10 vzorků od normálního rozdělení se střední odchylkou 2 a směrodatnou odchylku 0,1:</span><span class="sxs-lookup"><span data-stu-id="81234-111">The following draws 10 samples from the normal distribution with mean 2 and standard deviation 0.1:</span></span>

```qsharp
let samples = DrawMany(
    (NormalDistribution(2.0, PowD(0.1, 2.0)))::Sample,
    10, ()
);
```

## <a name="see-also"></a><span data-ttu-id="81234-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="81234-112">See Also</span></span>

- [<span data-ttu-id="81234-113">Microsoft. prohodilá. StandardNormalDistribution</span><span class="sxs-lookup"><span data-stu-id="81234-113">Microsoft.Quantum.Random.StandardNormalDistribution</span></span>](xref:Microsoft.Quantum.Random.StandardNormalDistribution)