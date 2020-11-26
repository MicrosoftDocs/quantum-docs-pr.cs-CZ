---
uid: Microsoft.Quantum.Simulation.GetGeneratorSystemFunction
title: GetGeneratorSystemFunction – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GetGeneratorSystemFunction
qsharp.summary: Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.
ms.openlocfilehash: 28e3c12d0ae0b08fc368c25eeb6f38d2834ca912
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229303"
---
# <a name="getgeneratorsystemfunction-function"></a><span data-ttu-id="4647d-102">GetGeneratorSystemFunction – funkce</span><span class="sxs-lookup"><span data-stu-id="4647d-102">GetGeneratorSystemFunction function</span></span>

<span data-ttu-id="4647d-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="4647d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="4647d-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4647d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4647d-105">Načte `GeneratorIndex` funkci v `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="4647d-105">Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.</span></span>

```qsharp
function GetGeneratorSystemFunction (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex)
```


## <a name="input"></a><span data-ttu-id="4647d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4647d-106">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="4647d-107">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="4647d-107">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="4647d-108">`GeneratorSystem`O zájmu.</span><span class="sxs-lookup"><span data-stu-id="4647d-108">The `GeneratorSystem` of interest.</span></span>



## <a name="output--int---generatorindex"></a><span data-ttu-id="4647d-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="4647d-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="4647d-110">Funkce, která indexuje každý `GeneratorIndex` pojem v Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="4647d-110">An function that indexes each `GeneratorIndex` term in a Hamiltonian.</span></span>

## <a name="see-also"></a><span data-ttu-id="4647d-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="4647d-111">See Also</span></span>

- [<span data-ttu-id="4647d-112">Microsoft. v. simulace. GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="4647d-112">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)
- [<span data-ttu-id="4647d-113">Microsoft. v. simulace. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="4647d-113">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)