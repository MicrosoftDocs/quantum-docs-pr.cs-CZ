---
uid: Microsoft.Quantum.Simulation.TrotterStepImpl
title: Operace TrotterStepImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStepImpl
qsharp.summary: Implements time-evolution by a term contained in a `GeneratorSystem`.
ms.openlocfilehash: 1ddd7ab33df243d729b5b48cba393d976bfd3640
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709219"
---
# <a name="trotterstepimpl-operation"></a><span data-ttu-id="c7d00-102">Operace TrotterStepImpl</span><span class="sxs-lookup"><span data-stu-id="c7d00-102">TrotterStepImpl operation</span></span>

<span data-ttu-id="c7d00-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c7d00-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c7d00-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c7d00-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c7d00-105">Implementuje čas – vývoj pomocí termínu obsaženého v `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="c7d00-105">Implements time-evolution by a term contained in a `GeneratorSystem`.</span></span>

```qsharp
operation TrotterStepImpl (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, idx : Int, stepsize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c7d00-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c7d00-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="c7d00-107">evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="c7d00-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="c7d00-108">Úplný popis systému, který se má simulovat</span><span class="sxs-lookup"><span data-stu-id="c7d00-108">A complete description of the system to be simulated.</span></span>


### <a name="idx--int"></a><span data-ttu-id="c7d00-109">IDX: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c7d00-109">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c7d00-110">Celočíselný index na termín v popsaných systémech.</span><span class="sxs-lookup"><span data-stu-id="c7d00-110">Integer index to a term in the described system.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="c7d00-111">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c7d00-111">stepsize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c7d00-112">Multiplikátor v době trvání – vývoj podle termínů indexovaných pomocí `idx` .</span><span class="sxs-lookup"><span data-stu-id="c7d00-112">Multiplier on duration of time-evolution by term indexed by `idx`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="c7d00-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c7d00-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c7d00-114">Qubits se při simulaci jednalo.</span><span class="sxs-lookup"><span data-stu-id="c7d00-114">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c7d00-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c7d00-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

