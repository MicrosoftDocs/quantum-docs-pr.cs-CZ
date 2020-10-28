---
uid: Microsoft.Quantum.Simulation.SimulationAlgorithm
title: Uživatelem definovaný typ SimulationAlgorithm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SimulationAlgorithm
qsharp.summary: >-
  Represents a time-independent simulation algorithm.

  A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator> to unitary time evolution for some time-interval.
ms.openlocfilehash: 9127a936bbf7a212e712645eabdf49fefc7a97d0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709322"
---
# <a name="simulationalgorithm-user-defined-type"></a><span data-ttu-id="007bd-102">Uživatelem definovaný typ SimulationAlgorithm</span><span class="sxs-lookup"><span data-stu-id="007bd-102">SimulationAlgorithm user defined type</span></span>

<span data-ttu-id="007bd-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="007bd-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="007bd-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="007bd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="007bd-105">Představuje algoritmus simulace závislý na čase.</span><span class="sxs-lookup"><span data-stu-id="007bd-105">Represents a time-independent simulation algorithm.</span></span>

<span data-ttu-id="007bd-106">Technika simulace, která je závislá na čase, převede <xref:microsoft.quantum.simulation.evolutiongenerator></span><span class="sxs-lookup"><span data-stu-id="007bd-106">A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator></span></span>
<span data-ttu-id="007bd-107">na jednotkový vývoj pro určitý časový interval.</span><span class="sxs-lookup"><span data-stu-id="007bd-107">to unitary time evolution for some time-interval.</span></span>

```qsharp

newtype SimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl));
```

