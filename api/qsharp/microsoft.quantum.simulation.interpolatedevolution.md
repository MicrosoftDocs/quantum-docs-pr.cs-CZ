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
# <a name="interpolatedevolution-function"></a>InterpolatedEvolution – funkce

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Interpoluje mezi dvěma generátory s jednotným plánem a vrátí operaci, která použije Simulovaný vývoj v rámci výsledného generátoru závislého na čase do qubit registru.

```qsharp
function InterpolatedEvolution (interpolationTime : Double, evolutionGeneratorStart : Microsoft.Quantum.Simulation.EvolutionGenerator, evolutionGeneratorEnd : Microsoft.Quantum.Simulation.EvolutionGenerator, timeDependentSimulationAlgorithm : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Vstup

### <a name="interpolationtime--double"></a>interpolationTime: [Double](xref:microsoft.quantum.lang-ref.double)

Čas, kdy se má provést interpolace.


### <a name="evolutiongeneratorstart--evolutiongenerator"></a>evolutionGeneratorStart: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Počáteční generátor pro simulaci vývoje v rámci.


### <a name="evolutiongeneratorend--evolutiongenerator"></a>evolutionGeneratorEnd: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Konečný generátor pro simulaci vývoje v rámci.


### <a name="timedependentsimulationalgorithm--timedependentsimulationalgorithm"></a>timeDependentSimulationAlgorithm: [timeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)

Algoritmus simulace závislý na čase, který bude použit k simulaci vývoje během rovnoměrného plánu interpolace.



## <a name="output--qubit--unit--is-adj--ctl"></a>Výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL



## <a name="remarks"></a>Poznámky

Pokud je zvolena doba interpolace pro splnění podmínek adiabatic, pak tato funkce vrátí operaci, která provede přípravu stavu adiabatic pro finální dynamický generátor.