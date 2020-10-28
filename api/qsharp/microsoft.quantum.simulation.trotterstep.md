---
uid: Microsoft.Quantum.Simulation.TrotterStep
title: TrotterStep – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStep
qsharp.summary: Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.
ms.openlocfilehash: 7a1a27ba4dc4b8b7bbc4da6a378d4a1494bc9415
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709231"
---
# <a name="trotterstep-function"></a><span data-ttu-id="16cc9-102">TrotterStep – funkce</span><span class="sxs-lookup"><span data-stu-id="16cc9-102">TrotterStep function</span></span>

<span data-ttu-id="16cc9-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="16cc9-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="16cc9-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="16cc9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="16cc9-105">Implementuje jediný časový krok pro vývoj času systémem, který je popsaný v tématu `EvolutionGenerator` použití Trotter – Suzuki rekompozice.</span><span class="sxs-lookup"><span data-stu-id="16cc9-105">Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.</span></span>

```qsharp
function TrotterStep (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, trotterOrder : Int, trotterStepSize : Double) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="16cc9-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="16cc9-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="16cc9-107">evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="16cc9-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="16cc9-108">Úplný popis systému, který se má simulovat</span><span class="sxs-lookup"><span data-stu-id="16cc9-108">A complete description of the system to be simulated.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="16cc9-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="16cc9-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="16cc9-110">Pořadí Trotter integrátoru.</span><span class="sxs-lookup"><span data-stu-id="16cc9-110">Order of Trotter integrator.</span></span> <span data-ttu-id="16cc9-111">Hodnota musí být buď 1, nebo sudé číslo.</span><span class="sxs-lookup"><span data-stu-id="16cc9-111">This must be either 1 or an even number.</span></span>


### <a name="trotterstepsize--double"></a><span data-ttu-id="16cc9-112">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="16cc9-112">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="16cc9-113">Doba trvání simulovaného vývojového času v jednom kroku Trotter</span><span class="sxs-lookup"><span data-stu-id="16cc9-113">Duration of simulated time-evolution in single Trotter step.</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="16cc9-114">Výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="16cc9-114">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="16cc9-115">Jednotná operace, která se blíží jednomu kroku vývoje času pro dobu trvání `trotterStepSize` .</span><span class="sxs-lookup"><span data-stu-id="16cc9-115">Unitary operation that approximates a single step of time-evolution for duration `trotterStepSize`.</span></span>

## <a name="remarks"></a><span data-ttu-id="16cc9-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="16cc9-116">Remarks</span></span>

<span data-ttu-id="16cc9-117">Další informace o dekompozici Trotter – Suzuki najdete v tématu [časově seřazené složení](/quantum/libraries/control-flow#time-ordered-composition).</span><span class="sxs-lookup"><span data-stu-id="16cc9-117">For more on the Trotter–Suzuki decomposition, see [Time-Ordered Composition](/quantum/libraries/control-flow#time-ordered-composition).</span></span>