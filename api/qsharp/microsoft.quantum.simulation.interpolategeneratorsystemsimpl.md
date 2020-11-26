---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystemsImpl
title: InterpolateGeneratorSystemsImpl – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystemsImpl
qsharp.summary: Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).
ms.openlocfilehash: 1ca9580ba603db8fee40e008a7ea51cb7a04d7d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229218"
---
# <a name="interpolategeneratorsystemsimpl-function"></a><span data-ttu-id="a585c-102">InterpolateGeneratorSystemsImpl – funkce</span><span class="sxs-lookup"><span data-stu-id="a585c-102">InterpolateGeneratorSystemsImpl function</span></span>

<span data-ttu-id="a585c-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a585c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a585c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a585c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a585c-105">Lineárně interpoluje dvě `GeneratorSystems` závislosti na parametru plánu `s` mezi 0 a 1 (včetně).</span><span class="sxs-lookup"><span data-stu-id="a585c-105">Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).</span></span>

```qsharp
function InterpolateGeneratorSystemsImpl (schedule : Double, generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="a585c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="a585c-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="a585c-107">Schedule: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a585c-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a585c-108">Parametr plánu $s \in [0, 1] $.</span><span class="sxs-lookup"><span data-stu-id="a585c-108">A schedule parameter $s\in[0,1]$.</span></span>


### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="a585c-109">generatorSystemStart: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="a585c-109">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="a585c-110">Spustí se `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="a585c-110">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="a585c-111">generatorSystemEnd: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="a585c-111">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="a585c-112">Konec `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="a585c-112">The end `GeneratorSystem`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="a585c-113">Výstup: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="a585c-113">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="a585c-114">`GeneratorSystem`Představuje systém, který je součtem systémů generátorů vstupu, s váhou $ (1-s) $ zapnutou `generatorSystemStart` a váhou $s $ on `generatorSystemEnd` .</span><span class="sxs-lookup"><span data-stu-id="a585c-114">A `GeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a585c-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="a585c-115">See Also</span></span>

- [<span data-ttu-id="a585c-116">Microsoft. v. simulace. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="a585c-116">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)