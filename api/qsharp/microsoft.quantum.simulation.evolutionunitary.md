---
uid: Microsoft.Quantum.Simulation.EvolutionUnitary
title: Uživatelem definovaný typ EvolutionUnitary
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionUnitary
qsharp.summary: >-
  Represents a unitary time-evolution operator.

  The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.
ms.openlocfilehash: 28ab492573b67e4aa42392e4ee499596b9c0225f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709016"
---
# <a name="evolutionunitary-user-defined-type"></a><span data-ttu-id="891e4-102">Uživatelem definovaný typ EvolutionUnitary</span><span class="sxs-lookup"><span data-stu-id="891e4-102">EvolutionUnitary user defined type</span></span>

<span data-ttu-id="891e4-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="891e4-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="891e4-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="891e4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="891e4-105">Představuje jednotnou obsluhu časového vývoje.</span><span class="sxs-lookup"><span data-stu-id="891e4-105">Represents a unitary time-evolution operator.</span></span>

<span data-ttu-id="891e4-106">Prvním parametrem je doba trvání vývoje času a druhý parametr je qubit registrem, který se používá v rámci jednotně.</span><span class="sxs-lookup"><span data-stu-id="891e4-106">The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.</span></span>

```qsharp

newtype EvolutionUnitary = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

