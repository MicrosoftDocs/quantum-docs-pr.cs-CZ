---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedFermionEvolutionFunction
title: JWOptimizedFermionEvolutionFunction – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedFermionEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.
ms.openlocfilehash: 952f3dc4ab0595ace0ee34c040cb21969afa111f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697532"
---
# <a name="jwoptimizedfermionevolutionfunction-function"></a><span data-ttu-id="7bfba-102">JWOptimizedFermionEvolutionFunction – funkce</span><span class="sxs-lookup"><span data-stu-id="7bfba-102">JWOptimizedFermionEvolutionFunction function</span></span>

<span data-ttu-id="7bfba-103">Obor názvů: [Microsoft. Prohledávejte. Research. chemie](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="7bfba-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="7bfba-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7bfba-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7bfba-105">Představuje dynamický generátor jako sadu simulovaných bran a rozšíření v JWOptimized.</span><span class="sxs-lookup"><span data-stu-id="7bfba-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.</span></span>

```qsharp
function JWOptimizedFermionEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="7bfba-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="7bfba-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="7bfba-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="7bfba-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="7bfba-108">Index generátoru, který se reprezentuje jako jednotkový vývoj v JWOptimized.</span><span class="sxs-lookup"><span data-stu-id="7bfba-108">A generator index to be represented as unitary evolution in the JWOptimized basis.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="7bfba-109">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7bfba-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7bfba-110">Qubit, která určuje znaménko času vývoje.</span><span class="sxs-lookup"><span data-stu-id="7bfba-110">Qubit that determines the sign of time-evolution.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="7bfba-111">Výstup: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="7bfba-111">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="7bfba-112">`EvolutionUnitary`Představuje čas – vývoj v rámci termínu, na který se odkazuje v ' generatorIndex.</span><span class="sxs-lookup"><span data-stu-id="7bfba-112">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>