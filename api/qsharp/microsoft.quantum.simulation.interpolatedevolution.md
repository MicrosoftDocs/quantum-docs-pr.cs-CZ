---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: InterpolatedEvolution – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 2ad907c02a2412dd4bf95630f401b5f1db5c8a08
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225104"
---
# <a name="interpolatedevolution-function"></a><span data-ttu-id="cfe9e-102">InterpolatedEvolution – funkce</span><span class="sxs-lookup"><span data-stu-id="cfe9e-102">InterpolatedEvolution function</span></span>

<span data-ttu-id="cfe9e-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="cfe9e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="cfe9e-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cfe9e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cfe9e-105">Interpoluje mezi dvěma generátory s jednotným plánem a vrátí operaci, která použije Simulovaný vývoj v rámci výsledného generátoru závislého na čase do qubit registru.</span><span class="sxs-lookup"><span data-stu-id="cfe9e-105">Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.</span></span>

```qsharp
function InterpolatedEvolution (interpolationTime : Double, evolutionGeneratorStart : Microsoft.Quantum.Simulation.EvolutionGenerator, evolutionGeneratorEnd : Microsoft.Quantum.Simulation.EvolutionGenerator, timeDependentSimulationAlgorithm : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="cfe9e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="cfe9e-106">Input</span></span>

### <a name="interpolationtime--double"></a><span data-ttu-id="cfe9e-107">interpolationTime: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cfe9e-107">interpolationTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cfe9e-108">Čas, kdy se má provést interpolace.</span><span class="sxs-lookup"><span data-stu-id="cfe9e-108">Time to perform the interpolation over.</span></span>


### <a name="evolutiongeneratorstart--evolutiongenerator"></a><span data-ttu-id="cfe9e-109">evolutionGeneratorStart: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="cfe9e-109">evolutionGeneratorStart : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="cfe9e-110">Počáteční generátor pro simulaci vývoje v rámci.</span><span class="sxs-lookup"><span data-stu-id="cfe9e-110">Initial generator to simulate evolution under.</span></span>


### <a name="evolutiongeneratorend--evolutiongenerator"></a><span data-ttu-id="cfe9e-111">evolutionGeneratorEnd: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="cfe9e-111">evolutionGeneratorEnd : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="cfe9e-112">Konečný generátor pro simulaci vývoje v rámci.</span><span class="sxs-lookup"><span data-stu-id="cfe9e-112">Final generator to simulate evolution under.</span></span>


### <a name="timedependentsimulationalgorithm--timedependentsimulationalgorithm"></a><span data-ttu-id="cfe9e-113">timeDependentSimulationAlgorithm: [timeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="cfe9e-113">timeDependentSimulationAlgorithm : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="cfe9e-114">Algoritmus simulace závislý na čase, který bude použit k simulaci vývoje během rovnoměrného plánu interpolace.</span><span class="sxs-lookup"><span data-stu-id="cfe9e-114">A time-dependent simulation algorithm that will be used to simulate evolution during the uniform interpolation schedule.</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="cfe9e-115">Výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="cfe9e-115">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="cfe9e-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="cfe9e-116">Remarks</span></span>

<span data-ttu-id="cfe9e-117">Pokud je zvolena doba interpolace pro splnění podmínek adiabatic, pak tato funkce vrátí operaci, která provede přípravu stavu adiabatic pro finální dynamický generátor.</span><span class="sxs-lookup"><span data-stu-id="cfe9e-117">If the interpolation time is chosen to meet the adiabatic conditions, then this function returns an operation which performs adiabatic state preparation for the final dynamical generator.</span></span>