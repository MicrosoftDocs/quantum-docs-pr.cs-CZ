---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: Uživatelem definovaný typ EvolutionSet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: 41504837b281b1021a2d09ef75acc10315b4fd07
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697477"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="e7148-102">Uživatelem definovaný typ EvolutionSet</span><span class="sxs-lookup"><span data-stu-id="e7148-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="e7148-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e7148-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e7148-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e7148-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e7148-105">Představuje sadu bran, které lze snadno implementovat a použít k implementaci algoritmů simulace.</span><span class="sxs-lookup"><span data-stu-id="e7148-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="e7148-106">Prvky v sadě jsou indexovány  <xref:microsoft.quantum.simulation.generatorindex> a a každá sada je popsána funkcí z `GeneratorIndex` na  <xref:microsoft.quantum.simulation.evolutionunitary> , což jsou operace parametrizované reálné číslo představující čas</span><span class="sxs-lookup"><span data-stu-id="e7148-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

