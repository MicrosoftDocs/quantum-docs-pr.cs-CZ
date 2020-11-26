---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: Uživatelem definovaný typ GeneratorIndex
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: dae23db9bee34be4aa99d96799efad64a66d7193
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229320"
---
# <a name="generatorindex-user-defined-type"></a>Uživatelem definovaný typ GeneratorIndex

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje jeden primitivní výraz v sadě všech dynamických generátorů, např. Hermitian operátory, pro které existuje mapa od tohoto generátoru k časovému vývoji tohoto generátoru prostřednictvím `EvolutionSet` .

První prvek (int []; Double []) je index, který je jedním termínem--například řetězec Pauli XXY s koeficientem 0,5 by byl indexován ([1, 1, 2], [0,5]). Alternativně je Hamiltonians Parametrizovaná souvislou proměnnou, jako je například X cos φ + Y Sin φ, může být instance reprezentovaná ([], [φ]). Druhý prvek indexuje podsystém, na kterém generátor působí.

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="remarks"></a>Poznámky

> [!WARNING]
> Interpretace `GeneratorIndex` není definována s výjimkou odkazů na konkrétní sadu generátorů.

## <a name="see-also"></a>Viz také

- [Microsoft. v. simulace. EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [Microsoft. v. simulace. PauliEvolutionSet](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)