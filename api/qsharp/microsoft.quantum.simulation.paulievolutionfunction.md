---
uid: Microsoft.Quantum.Simulation.PauliEvolutionFunction
title: PauliEvolutionFunction – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 9b12dc4a05c99aad319799f8c6526cd3085e6dcd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847973"
---
# <a name="paulievolutionfunction-function"></a><span data-ttu-id="52fa5-102">PauliEvolutionFunction – funkce</span><span class="sxs-lookup"><span data-stu-id="52fa5-102">PauliEvolutionFunction function</span></span>

<span data-ttu-id="52fa5-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="52fa5-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="52fa5-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="52fa5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="52fa5-105">Představuje dynamický generátor jako sadu simulovaných bran a rozšíření v Pauli.</span><span class="sxs-lookup"><span data-stu-id="52fa5-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function PauliEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="52fa5-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="52fa5-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="52fa5-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="52fa5-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="52fa5-108">Index generátoru, který se reprezentuje jako jednotkový vývoj v Pauli.</span><span class="sxs-lookup"><span data-stu-id="52fa5-108">A generator index to be represented as unitary evolution in the Pauli basis.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="52fa5-109">Výstup: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="52fa5-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="52fa5-110">`EvolutionUnitary`Představuje čas – vývoj v rámci termínu, na který se odkazuje v ' generatorIndex.</span><span class="sxs-lookup"><span data-stu-id="52fa5-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>