---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: Uživatelem definovaný typ GeneratorIndex
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 8d36f74fbf122469e9e829b950e4ed9a6e3a35a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708608"
---
# <a name="generatorindex-user-defined-type"></a><span data-ttu-id="1204f-102">Uživatelem definovaný typ GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="1204f-102">GeneratorIndex user defined type</span></span>

<span data-ttu-id="1204f-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1204f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1204f-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1204f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1204f-105">Představuje jeden primitivní výraz v sadě všech dynamických generátorů, např. Hermitian operátory, pro které existuje mapa od tohoto generátoru k časovému vývoji tohoto generátoru prostřednictvím `EvolutionSet` .</span><span class="sxs-lookup"><span data-stu-id="1204f-105">Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.</span></span>

<span data-ttu-id="1204f-106">První prvek (int []; Double []) je index, který je jedním termínem--například řetězec Pauli XXY s koeficientem 0,5 by byl indexován ([1, 1, 2], [0,5]).</span><span class="sxs-lookup"><span data-stu-id="1204f-106">The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]).</span></span> <span data-ttu-id="1204f-107">Alternativně je Hamiltonians Parametrizovaná souvislou proměnnou, jako je například X cos φ + Y Sin φ, může být instance reprezentovaná ([], [φ]).</span><span class="sxs-lookup"><span data-stu-id="1204f-107">Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]).</span></span> <span data-ttu-id="1204f-108">Druhý prvek indexuje podsystém, na kterém generátor působí.</span><span class="sxs-lookup"><span data-stu-id="1204f-108">The second element indexes the subsystem on which the generator acts on.</span></span>

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="remarks"></a><span data-ttu-id="1204f-109">Poznámky</span><span class="sxs-lookup"><span data-stu-id="1204f-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="1204f-110">Interpretace `GeneratorIndex` není definována s výjimkou odkazů na konkrétní sadu generátorů.</span><span class="sxs-lookup"><span data-stu-id="1204f-110">The interpretation of an `GeneratorIndex` is not defined except with reference to a particular set of generators.</span></span>

## <a name="see-also"></a><span data-ttu-id="1204f-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="1204f-111">See Also</span></span>

- [<span data-ttu-id="1204f-112">Microsoft. v. simulace. EvolutionSet</span><span class="sxs-lookup"><span data-stu-id="1204f-112">Microsoft.Quantum.Simulation.EvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [<span data-ttu-id="1204f-113">Microsoft. v. simulace. PauliEvolutionSet</span><span class="sxs-lookup"><span data-stu-id="1204f-113">Microsoft.Quantum.Simulation.PauliEvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)