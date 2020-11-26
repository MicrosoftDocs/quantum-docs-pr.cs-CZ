---
uid: Microsoft.Quantum.Research.Chemistry.JordanWignerOptimizedFermionEvolutionSet
title: JordanWignerOptimizedFermionEvolutionSet – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JordanWignerOptimizedFermionEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 2cd555882792c29cb2ed71972739505df11fbabc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225733"
---
# <a name="jordanwigneroptimizedfermionevolutionset-function"></a><span data-ttu-id="89ba4-102">JordanWignerOptimizedFermionEvolutionSet – funkce</span><span class="sxs-lookup"><span data-stu-id="89ba4-102">JordanWignerOptimizedFermionEvolutionSet function</span></span>

<span data-ttu-id="89ba4-103">Obor názvů: [Microsoft. Prohledávejte. Research. chemie](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="89ba4-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="89ba4-104">Balíček: [Microsoft. prostudoval. Research. chemie](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="89ba4-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="89ba4-105">Představuje dynamický generátor jako sadu simulovaných bran a rozšíření v Pauli.</span><span class="sxs-lookup"><span data-stu-id="89ba4-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function JordanWignerOptimizedFermionEvolutionSet (parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="input"></a><span data-ttu-id="89ba4-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="89ba4-106">Input</span></span>

### <a name="parityqubit--qubit"></a><span data-ttu-id="89ba4-107">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="89ba4-107">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="89ba4-108">Qubit, která určuje znaménko času vývoje.</span><span class="sxs-lookup"><span data-stu-id="89ba4-108">Qubit that determines the sign of time-evolution.</span></span>



## <a name="output--evolutionset"></a><span data-ttu-id="89ba4-109">Výstup: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="89ba4-109">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="89ba4-110">Objekt `EvolutionSet` , který mapuje `GeneratorIndex` pro JWOptimized na EvolutionUnitary.</span><span class="sxs-lookup"><span data-stu-id="89ba4-110">An `EvolutionSet` that maps a `GeneratorIndex` for the JWOptimized basis to an \`EvolutionUnitary.</span></span>