---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: Uživatelem definovaný typ GeneratorIndex
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 762dac81ea0963443f0338cea1b879856c84b0ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858387"
---
# <a name="generatorindex-user-defined-type"></a>Uživatelem definovaný typ GeneratorIndex

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje jeden primitivní výraz v sadě všech dynamických generátorů, např. Hermitian operátory, pro které existuje mapa od tohoto generátoru k časovému vývoji tohoto generátoru prostřednictvím `EvolutionSet` .

První prvek (int []; Double []) je index, který je jedním termínem--například řetězec Pauli XXY s koeficientem 0,5 by byl indexován ([1, 1, 2], [0,5]). Alternativně je Hamiltonians Parametrizovaná souvislou proměnnou, jako je například X cos φ + Y Sin φ, může být instance reprezentovaná ([], [φ]). Druhý prvek indexuje podsystém, na kterém generátor působí.

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="example"></a>Příklad

Pomocí  <xref:microsoft.quantum.simulation.paulievolutionset> , operátor $ \pi X_2 X_5 Y_9 $ je reprezentován jako:

```qsharp
let index = GeneratorIndex(([1, 1, 2], [PI()]), [2, 5, 9]);
```

## <a name="remarks"></a>Poznámky

> [!WARNING]
> Interpretace `GeneratorIndex` není definována s výjimkou odkazů na konkrétní sadu generátorů.

## <a name="see-also"></a>Viz také

- [Microsoft. v. simulace. EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [Microsoft. v. simulace. PauliEvolutionSet](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)