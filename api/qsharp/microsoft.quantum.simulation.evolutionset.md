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
# <a name="evolutionset-user-defined-type"></a>Uživatelem definovaný typ EvolutionSet

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje sadu bran, které lze snadno implementovat a použít k implementaci algoritmů simulace.

Prvky v sadě jsou indexovány  <xref:microsoft.quantum.simulation.generatorindex> a a každá sada je popsána funkcí z `GeneratorIndex` na  <xref:microsoft.quantum.simulation.evolutionunitary> , což jsou operace parametrizované reálné číslo představující čas

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

