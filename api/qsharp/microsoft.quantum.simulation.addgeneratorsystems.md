---
uid: Microsoft.Quantum.Simulation.AddGeneratorSystems
title: AddGeneratorSystems – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AddGeneratorSystems
qsharp.summary: Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.
ms.openlocfilehash: 494037aa7635cccf25978bea9339ecc7aee75142
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697485"
---
# <a name="addgeneratorsystems-function"></a><span data-ttu-id="d53e3-102">AddGeneratorSystems – funkce</span><span class="sxs-lookup"><span data-stu-id="d53e3-102">AddGeneratorSystems function</span></span>

<span data-ttu-id="d53e3-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="d53e3-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="d53e3-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d53e3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d53e3-105">Přidá dvě `GeneratorSystem` s pro vytvoření nového `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="d53e3-105">Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.</span></span>

```qsharp
function AddGeneratorSystems (generatorSystemA : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemB : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="d53e3-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="d53e3-106">Input</span></span>

### <a name="generatorsystema--generatorsystem"></a><span data-ttu-id="d53e3-107">generatorSystemA: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="d53e3-107">generatorSystemA : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="d53e3-108">První `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="d53e3-108">The first `GeneratorSystem`.</span></span>


### <a name="generatorsystemb--generatorsystem"></a><span data-ttu-id="d53e3-109">generatorSystemB: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="d53e3-109">generatorSystemB : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="d53e3-110">Druhý objekt `GeneratorSystem`.</span><span class="sxs-lookup"><span data-stu-id="d53e3-110">The second `GeneratorSystem`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="d53e3-111">Výstup: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="d53e3-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="d53e3-112">Představuje `GeneratorSystem` systém, který představuje součet systémů generátorů vstupu.</span><span class="sxs-lookup"><span data-stu-id="d53e3-112">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="d53e3-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="d53e3-113">See Also</span></span>

- [<span data-ttu-id="d53e3-114">Microsoft. v. simulace. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="d53e3-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)