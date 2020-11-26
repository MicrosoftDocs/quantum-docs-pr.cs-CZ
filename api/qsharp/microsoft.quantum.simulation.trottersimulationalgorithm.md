---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithm
title: TrotterSimulationAlgorithm – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithm
qsharp.summary: '`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.'
ms.openlocfilehash: aa8338ab359441765db72a12f84a3a51e5bee3ce
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192532"
---
# <a name="trottersimulationalgorithm-function"></a><span data-ttu-id="77cac-102">TrotterSimulationAlgorithm – funkce</span><span class="sxs-lookup"><span data-stu-id="77cac-102">TrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="77cac-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="77cac-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="77cac-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="77cac-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="77cac-105">`SimulationAlgorithm` funkce, která používá dekompozici Trotter – Suzuki k aproximaci operátoru vývoj času _EXP (-iHt)_.</span><span class="sxs-lookup"><span data-stu-id="77cac-105">`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.</span></span>

```qsharp
function TrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.SimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="77cac-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="77cac-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="77cac-107">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="77cac-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="77cac-108">Doba trvání simulovaného vývojového času v jednom kroku Trotter</span><span class="sxs-lookup"><span data-stu-id="77cac-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="77cac-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="77cac-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="77cac-110">Pořadí Trotter integrátoru.</span><span class="sxs-lookup"><span data-stu-id="77cac-110">Order of Trotter integrator.</span></span> <span data-ttu-id="77cac-111">Hodnota musí být buď 1, nebo sudé číslo.</span><span class="sxs-lookup"><span data-stu-id="77cac-111">This must be either 1 or an even number.</span></span>



## <a name="output--simulationalgorithm"></a><span data-ttu-id="77cac-112">Výstup: [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="77cac-112">Output : [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span></span>

<span data-ttu-id="77cac-113">`SimulationAlgorithm`Typ.</span><span class="sxs-lookup"><span data-stu-id="77cac-113">A `SimulationAlgorithm` type.</span></span>