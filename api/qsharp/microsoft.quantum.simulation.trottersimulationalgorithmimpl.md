---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithmImpl
title: Operace TrotterSimulationAlgorithmImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithmImpl
qsharp.summary: Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).
ms.openlocfilehash: 2af68532d700a1fb5b037707ce4650696cbe1a64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709232"
---
# <a name="trottersimulationalgorithmimpl-operation"></a><span data-ttu-id="c7f0d-102">Operace TrotterSimulationAlgorithmImpl</span><span class="sxs-lookup"><span data-stu-id="c7f0d-102">TrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="c7f0d-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c7f0d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c7f0d-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c7f0d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c7f0d-105">Provede opakované volání k `TrotterStep` aproximaci operátoru vývoj času EXP ( _-iHt_ ).</span><span class="sxs-lookup"><span data-stu-id="c7f0d-105">Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp( _-iHt_ ).</span></span>

```qsharp
operation TrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c7f0d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c7f0d-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="c7f0d-107">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c7f0d-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c7f0d-108">Doba trvání simulovaného vývojového času v jednom kroku Trotter</span><span class="sxs-lookup"><span data-stu-id="c7f0d-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="c7f0d-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c7f0d-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c7f0d-110">Pořadí Trotter integrátoru.</span><span class="sxs-lookup"><span data-stu-id="c7f0d-110">Order of Trotter integrator.</span></span> <span data-ttu-id="c7f0d-111">Hodnota musí být buď 1, nebo sudé číslo.</span><span class="sxs-lookup"><span data-stu-id="c7f0d-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="c7f0d-112">maxTime: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c7f0d-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c7f0d-113">Celková doba trvání simulace $t $.</span><span class="sxs-lookup"><span data-stu-id="c7f0d-113">Total duration of simulation $t$.</span></span>


### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="c7f0d-114">evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="c7f0d-114">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="c7f0d-115">Úplný popis systému, který se má simulovat</span><span class="sxs-lookup"><span data-stu-id="c7f0d-115">A complete description of the system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="c7f0d-116">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c7f0d-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c7f0d-117">Qubits se při simulaci jednalo.</span><span class="sxs-lookup"><span data-stu-id="c7f0d-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c7f0d-118">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c7f0d-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

