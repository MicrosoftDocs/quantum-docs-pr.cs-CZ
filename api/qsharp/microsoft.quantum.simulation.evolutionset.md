---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: Uživatelem definovaný typ EvolutionSet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: 35c0b24da284a5871fd11b6d624102b853b89d19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856076"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="b7bb8-102">Uživatelem definovaný typ EvolutionSet</span><span class="sxs-lookup"><span data-stu-id="b7bb8-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="b7bb8-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b7bb8-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b7bb8-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b7bb8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b7bb8-105">Představuje sadu bran, které lze snadno implementovat a použít k implementaci algoritmů simulace.</span><span class="sxs-lookup"><span data-stu-id="b7bb8-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="b7bb8-106">Prvky v sadě jsou indexovány  <xref:microsoft.quantum.simulation.generatorindex> a a každá sada je popsána funkcí z `GeneratorIndex` na  <xref:microsoft.quantum.simulation.evolutionunitary> , což jsou operace parametrizované reálné číslo představující čas</span><span class="sxs-lookup"><span data-stu-id="b7bb8-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

