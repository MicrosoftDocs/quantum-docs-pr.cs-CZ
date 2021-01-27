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
# <a name="generatorindex-user-defined-type"></a><span data-ttu-id="c8037-102">Uživatelem definovaný typ GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="c8037-102">GeneratorIndex user defined type</span></span>

<span data-ttu-id="c8037-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c8037-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c8037-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8037-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8037-105">Představuje jeden primitivní výraz v sadě všech dynamických generátorů, např. Hermitian operátory, pro které existuje mapa od tohoto generátoru k časovému vývoji tohoto generátoru prostřednictvím `EvolutionSet` .</span><span class="sxs-lookup"><span data-stu-id="c8037-105">Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.</span></span>

<span data-ttu-id="c8037-106">První prvek (int []; Double []) je index, který je jedním termínem--například řetězec Pauli XXY s koeficientem 0,5 by byl indexován ([1, 1, 2], [0,5]).</span><span class="sxs-lookup"><span data-stu-id="c8037-106">The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]).</span></span> <span data-ttu-id="c8037-107">Alternativně je Hamiltonians Parametrizovaná souvislou proměnnou, jako je například X cos φ + Y Sin φ, může být instance reprezentovaná ([], [φ]).</span><span class="sxs-lookup"><span data-stu-id="c8037-107">Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]).</span></span> <span data-ttu-id="c8037-108">Druhý prvek indexuje podsystém, na kterém generátor působí.</span><span class="sxs-lookup"><span data-stu-id="c8037-108">The second element indexes the subsystem on which the generator acts on.</span></span>

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="example"></a><span data-ttu-id="c8037-109">Příklad</span><span class="sxs-lookup"><span data-stu-id="c8037-109">Example</span></span>

<span data-ttu-id="c8037-110">Pomocí  <xref:microsoft.quantum.simulation.paulievolutionset> , operátor $ \pi X_2 X_5 Y_9 $ je reprezentován jako:</span><span class="sxs-lookup"><span data-stu-id="c8037-110">Using  <xref:microsoft.quantum.simulation.paulievolutionset>, the operator $\pi X_2 X_5 Y_9$ is represented as:</span></span>

```qsharp
let index = GeneratorIndex(([1, 1, 2], [PI()]), [2, 5, 9]);
```

## <a name="remarks"></a><span data-ttu-id="c8037-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c8037-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="c8037-112">Interpretace `GeneratorIndex` není definována s výjimkou odkazů na konkrétní sadu generátorů.</span><span class="sxs-lookup"><span data-stu-id="c8037-112">The interpretation of an `GeneratorIndex` is not defined except with reference to a particular set of generators.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8037-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="c8037-113">See Also</span></span>

- [<span data-ttu-id="c8037-114">Microsoft. v. simulace. EvolutionSet</span><span class="sxs-lookup"><span data-stu-id="c8037-114">Microsoft.Quantum.Simulation.EvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [<span data-ttu-id="c8037-115">Microsoft. v. simulace. PauliEvolutionSet</span><span class="sxs-lookup"><span data-stu-id="c8037-115">Microsoft.Quantum.Simulation.PauliEvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)