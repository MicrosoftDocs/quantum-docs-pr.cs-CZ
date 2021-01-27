---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithm
title: TimeDependentTrotterSimulationAlgorithm – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithm
qsharp.summary: '`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.'
ms.openlocfilehash: c827dd79af6f4b745adf8903ed2664d9e8255785
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858356"
---
# <a name="timedependenttrottersimulationalgorithm-function"></a><span data-ttu-id="c06c1-102">TimeDependentTrotterSimulationAlgorithm – funkce</span><span class="sxs-lookup"><span data-stu-id="c06c1-102">TimeDependentTrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="c06c1-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c06c1-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c06c1-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c06c1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c06c1-105">`TimeDependentSimulationAlgorithm` funkce, která používá dekompozici Trotter – Suzuki k aproximaci jednotkového operátoru, který řeší rovnici Schrodinger závislé na čase.</span><span class="sxs-lookup"><span data-stu-id="c06c1-105">`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.</span></span>

```qsharp
function TimeDependentTrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="c06c1-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c06c1-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="c06c1-107">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c06c1-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c06c1-108">Doba trvání simulovaného vývojového času v jednom kroku Trotter</span><span class="sxs-lookup"><span data-stu-id="c06c1-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="c06c1-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c06c1-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c06c1-110">Pořadí Trotter integrátoru.</span><span class="sxs-lookup"><span data-stu-id="c06c1-110">Order of Trotter integrator.</span></span> <span data-ttu-id="c06c1-111">Hodnota musí být buď 1, nebo sudé číslo.</span><span class="sxs-lookup"><span data-stu-id="c06c1-111">This must be either 1 or an even number.</span></span>



## <a name="output--timedependentsimulationalgorithm"></a><span data-ttu-id="c06c1-112">Výstup: [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="c06c1-112">Output : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="c06c1-113">`TimeDependentSimulationAlgorithm`Typ.</span><span class="sxs-lookup"><span data-stu-id="c06c1-113">A `TimeDependentSimulationAlgorithm` type.</span></span>