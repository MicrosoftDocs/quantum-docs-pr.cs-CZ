---
uid: Microsoft.Quantum.Simulation.AddGeneratorSystems
title: AddGeneratorSystems – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AddGeneratorSystems
qsharp.summary: Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.
ms.openlocfilehash: b23fc89b941a7cdd93ee7938dda50eb14e3ed528
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857942"
---
# <a name="addgeneratorsystems-function"></a><span data-ttu-id="64fc2-102">AddGeneratorSystems – funkce</span><span class="sxs-lookup"><span data-stu-id="64fc2-102">AddGeneratorSystems function</span></span>

<span data-ttu-id="64fc2-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="64fc2-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="64fc2-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="64fc2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="64fc2-105">Přidá dvě `GeneratorSystem` s pro vytvoření nového `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="64fc2-105">Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.</span></span>

```qsharp
function AddGeneratorSystems (generatorSystemA : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemB : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="64fc2-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="64fc2-106">Input</span></span>

### <a name="generatorsystema--generatorsystem"></a><span data-ttu-id="64fc2-107">generatorSystemA: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="64fc2-107">generatorSystemA : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="64fc2-108">První `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="64fc2-108">The first `GeneratorSystem`.</span></span>


### <a name="generatorsystemb--generatorsystem"></a><span data-ttu-id="64fc2-109">generatorSystemB: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="64fc2-109">generatorSystemB : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="64fc2-110">Druhý objekt `GeneratorSystem`.</span><span class="sxs-lookup"><span data-stu-id="64fc2-110">The second `GeneratorSystem`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="64fc2-111">Výstup: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="64fc2-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="64fc2-112">Představuje `GeneratorSystem` systém, který představuje součet systémů generátorů vstupu.</span><span class="sxs-lookup"><span data-stu-id="64fc2-112">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="64fc2-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="64fc2-113">See Also</span></span>

- [<span data-ttu-id="64fc2-114">Microsoft. v. simulace. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="64fc2-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)