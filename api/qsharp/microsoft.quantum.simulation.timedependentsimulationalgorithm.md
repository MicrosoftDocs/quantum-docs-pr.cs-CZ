---
uid: Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
title: Uživatelem definovaný typ TimeDependentSimulationAlgorithm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentSimulationAlgorithm
qsharp.summary: >-
  Represents a time-dependent simulation algorithm.

  A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule> to unitary time-evolution for some time-interval.
ms.openlocfilehash: b495a9fd96c78872f84e8f8183105f6290f70655
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192515"
---
# <a name="timedependentsimulationalgorithm-user-defined-type"></a><span data-ttu-id="39521-102">Uživatelem definovaný typ TimeDependentSimulationAlgorithm</span><span class="sxs-lookup"><span data-stu-id="39521-102">TimeDependentSimulationAlgorithm user defined type</span></span>

<span data-ttu-id="39521-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="39521-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="39521-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39521-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39521-105">Představuje algoritmus simulace závislý na čase.</span><span class="sxs-lookup"><span data-stu-id="39521-105">Represents a time-dependent simulation algorithm.</span></span>

<span data-ttu-id="39521-106">Technika simulace závislá na čase převede <xref:microsoft.quantum.simulation.evolutionschedule></span><span class="sxs-lookup"><span data-stu-id="39521-106">A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule></span></span>
<span data-ttu-id="39521-107">na jednotkový čas – vývoj pro určitý časový interval.</span><span class="sxs-lookup"><span data-stu-id="39521-107">to unitary time-evolution for some time-interval.</span></span>

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```

