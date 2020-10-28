---
uid: Microsoft.Quantum.Simulation.GetGeneratorSystemFunction
title: GetGeneratorSystemFunction – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GetGeneratorSystemFunction
qsharp.summary: Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.
ms.openlocfilehash: 60ebbdbd1020d41a54426377043fc0c84ceec504
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708889"
---
# <a name="getgeneratorsystemfunction-function"></a><span data-ttu-id="6a3d2-102">GetGeneratorSystemFunction – funkce</span><span class="sxs-lookup"><span data-stu-id="6a3d2-102">GetGeneratorSystemFunction function</span></span>

<span data-ttu-id="6a3d2-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="6a3d2-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="6a3d2-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6a3d2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6a3d2-105">Načte `GeneratorIndex` funkci v `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="6a3d2-105">Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.</span></span>

```qsharp
function GetGeneratorSystemFunction (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex)
```


## <a name="input"></a><span data-ttu-id="6a3d2-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="6a3d2-106">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="6a3d2-107">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="6a3d2-107">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="6a3d2-108">`GeneratorSystem`O zájmu.</span><span class="sxs-lookup"><span data-stu-id="6a3d2-108">The `GeneratorSystem` of interest.</span></span>



## <a name="output--int---generatorindex"></a><span data-ttu-id="6a3d2-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="6a3d2-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="6a3d2-110">Funkce, která indexuje každý `GeneratorIndex` pojem v Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="6a3d2-110">An function that indexes each `GeneratorIndex` term in a Hamiltonian.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a3d2-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="6a3d2-111">See Also</span></span>

- [<span data-ttu-id="6a3d2-112">Microsoft. v. simulace. GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="6a3d2-112">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)
- [<span data-ttu-id="6a3d2-113">Microsoft. v. simulace. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="6a3d2-113">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)