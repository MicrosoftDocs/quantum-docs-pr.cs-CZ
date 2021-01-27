---
uid: Microsoft.Quantum.Simulation.GetGeneratorSystemFunction
title: GetGeneratorSystemFunction – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GetGeneratorSystemFunction
qsharp.summary: Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.
ms.openlocfilehash: 7b6eabd203cecf8c64f0bff3e06f08a0bec31bf2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852769"
---
# <a name="getgeneratorsystemfunction-function"></a><span data-ttu-id="e66ac-102">GetGeneratorSystemFunction – funkce</span><span class="sxs-lookup"><span data-stu-id="e66ac-102">GetGeneratorSystemFunction function</span></span>

<span data-ttu-id="e66ac-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e66ac-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e66ac-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e66ac-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e66ac-105">Načte `GeneratorIndex` funkci v `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="e66ac-105">Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.</span></span>

```qsharp
function GetGeneratorSystemFunction (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex)
```


## <a name="input"></a><span data-ttu-id="e66ac-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e66ac-106">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="e66ac-107">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="e66ac-107">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="e66ac-108">`GeneratorSystem`O zájmu.</span><span class="sxs-lookup"><span data-stu-id="e66ac-108">The `GeneratorSystem` of interest.</span></span>



## <a name="output--int---generatorindex"></a><span data-ttu-id="e66ac-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e66ac-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="e66ac-110">Funkce, která indexuje každý `GeneratorIndex` pojem v Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="e66ac-110">An function that indexes each `GeneratorIndex` term in a Hamiltonian.</span></span>

## <a name="see-also"></a><span data-ttu-id="e66ac-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="e66ac-111">See Also</span></span>

- [<span data-ttu-id="e66ac-112">Microsoft. v. simulace. GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="e66ac-112">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)
- [<span data-ttu-id="e66ac-113">Microsoft. v. simulace. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="e66ac-113">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)