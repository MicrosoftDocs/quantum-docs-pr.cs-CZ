---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: Uživatelem definovaný typ EvolutionSet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: ee8f3c0716f035dcb0c4fad557092fbf8dd3c356
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229405"
---
# <a name="evolutionset-user-defined-type"></a>Uživatelem definovaný typ EvolutionSet

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje sadu bran, které lze snadno implementovat a použít k implementaci algoritmů simulace.

Prvky v sadě jsou indexovány  <xref:microsoft.quantum.simulation.generatorindex> a a každá sada je popsána funkcí z `GeneratorIndex` na  <xref:microsoft.quantum.simulation.evolutionunitary> , což jsou operace parametrizované reálné číslo představující čas

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

