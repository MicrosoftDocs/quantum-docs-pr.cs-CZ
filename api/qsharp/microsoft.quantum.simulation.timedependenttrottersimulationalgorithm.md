---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithm
title: TimeDependentTrotterSimulationAlgorithm – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithm
qsharp.summary: '`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.'
ms.openlocfilehash: 94bc606fdc46d77e8beb1470c78102a63e6d4e81
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192770"
---
# <a name="timedependenttrottersimulationalgorithm-function"></a><span data-ttu-id="cd43b-102">TimeDependentTrotterSimulationAlgorithm – funkce</span><span class="sxs-lookup"><span data-stu-id="cd43b-102">TimeDependentTrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="cd43b-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="cd43b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="cd43b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cd43b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cd43b-105">`TimeDependentSimulationAlgorithm` funkce, která používá dekompozici Trotter – Suzuki k aproximaci jednotkového operátoru, který řeší rovnici Schrodinger závislé na čase.</span><span class="sxs-lookup"><span data-stu-id="cd43b-105">`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.</span></span>

```qsharp
function TimeDependentTrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="cd43b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="cd43b-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="cd43b-107">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cd43b-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cd43b-108">Doba trvání simulovaného vývojového času v jednom kroku Trotter</span><span class="sxs-lookup"><span data-stu-id="cd43b-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="cd43b-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cd43b-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cd43b-110">Pořadí Trotter integrátoru.</span><span class="sxs-lookup"><span data-stu-id="cd43b-110">Order of Trotter integrator.</span></span> <span data-ttu-id="cd43b-111">Hodnota musí být buď 1, nebo sudé číslo.</span><span class="sxs-lookup"><span data-stu-id="cd43b-111">This must be either 1 or an even number.</span></span>



## <a name="output--timedependentsimulationalgorithm"></a><span data-ttu-id="cd43b-112">Výstup: [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="cd43b-112">Output : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="cd43b-113">`TimeDependentSimulationAlgorithm`Typ.</span><span class="sxs-lookup"><span data-stu-id="cd43b-113">A `TimeDependentSimulationAlgorithm` type.</span></span>