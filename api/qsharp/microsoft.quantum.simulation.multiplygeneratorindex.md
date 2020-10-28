---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: MultiplyGeneratorIndex – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: 9ee0568073b65b027cc98eb56934e9286b59c27f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708860"
---
# <a name="multiplygeneratorindex-function"></a><span data-ttu-id="8a5a5-102">MultiplyGeneratorIndex – funkce</span><span class="sxs-lookup"><span data-stu-id="8a5a5-102">MultiplyGeneratorIndex function</span></span>

<span data-ttu-id="8a5a5-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8a5a5-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8a5a5-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8a5a5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8a5a5-105">Vynásobí koeficient v `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="8a5a5-105">Multiplies the coefficient in a `GeneratorIndex`.</span></span>

```qsharp
function MultiplyGeneratorIndex (multiplier : Double, generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="8a5a5-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="8a5a5-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="8a5a5-107">násobitel: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8a5a5-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8a5a5-108">Multiplikátor v koeficientu.</span><span class="sxs-lookup"><span data-stu-id="8a5a5-108">The multiplier on the coefficient.</span></span>


### <a name="generatorindex--generatorindex"></a><span data-ttu-id="8a5a5-109">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="8a5a5-109">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="8a5a5-110">`GeneratorIndex`Vynásobeno.</span><span class="sxs-lookup"><span data-stu-id="8a5a5-110">The `GeneratorIndex` to be multiplied.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="8a5a5-111">Výstup: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="8a5a5-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="8a5a5-112">`GeneratorIndex`Představuje výraz s větším koeficientem součinitele `multiplier` .</span><span class="sxs-lookup"><span data-stu-id="8a5a5-112">A `GeneratorIndex` representing a term with coefficient a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a5a5-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="8a5a5-113">See Also</span></span>

- [<span data-ttu-id="8a5a5-114">Microsoft. v. simulace. GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="8a5a5-114">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)