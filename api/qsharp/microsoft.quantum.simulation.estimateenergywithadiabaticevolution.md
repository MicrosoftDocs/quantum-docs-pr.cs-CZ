---
uid: Microsoft.Quantum.Simulation.EstimateEnergyWithAdiabaticEvolution
title: Operace EstimateEnergyWithAdiabaticEvolution
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergyWithAdiabaticEvolution
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: b279d35418b8f013ad0d72e9a980c9bf6ce0689a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225325"
---
# <a name="estimateenergywithadiabaticevolution-operation"></a><span data-ttu-id="1e0ff-102">Operace EstimateEnergyWithAdiabaticEvolution</span><span class="sxs-lookup"><span data-stu-id="1e0ff-102">EstimateEnergyWithAdiabaticEvolution operation</span></span>

<span data-ttu-id="1e0ff-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1e0ff-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1e0ff-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1e0ff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1e0ff-105">Provede přípravu stavu pomocí `statePrepUnitary` příkazu na automaticky přidělený stav vstupu následovaný přípravou stavu adiabatic s využitím `adiabaticUnitary` a nakonec odhadem fáze s ohledem na `qpeUnitary` výsledný stav pomocí `phaseEstAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="1e0ff-105">Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation EstimateEnergyWithAdiabaticEvolution (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a><span data-ttu-id="1e0ff-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="1e0ff-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="1e0ff-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1e0ff-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1e0ff-108">Počet qubits použitých pro simulaci.</span><span class="sxs-lookup"><span data-stu-id="1e0ff-108">Number of qubits used for the simulation.</span></span>


### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="1e0ff-109">statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1e0ff-109">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="1e0ff-110">Oracle představující stavovou přípravu počátečního dynamického generátoru.</span><span class="sxs-lookup"><span data-stu-id="1e0ff-110">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="adiabaticunitary--qubit--unit"></a><span data-ttu-id="1e0ff-111">adiabaticUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1e0ff-111">adiabaticUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="1e0ff-112">Oracle představující algoritmus vývoje adiabatic, který se použije k implementaci Sweep do konečného stavu algoritmu.</span><span class="sxs-lookup"><span data-stu-id="1e0ff-112">An oracle representing the adiabatic evolution algorithm to be used to implement the sweeps to the final state of the algorithm.</span></span>


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a><span data-ttu-id="1e0ff-113">qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="1e0ff-113">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="1e0ff-114">Oracle reprezentující jednotkový operátor $U $ představující vývoj pro čas $ \delta t $ v rámci dynamického generátoru s uzemněným stavem $ \ket{\phi} $ a pozemní energie $E = \phi \\ , \delta t $.</span><span class="sxs-lookup"><span data-stu-id="1e0ff-114">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="1e0ff-115">phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1e0ff-115">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="1e0ff-116">Operace, která provádí odhad fáze pro danou jednotkovou operaci.</span><span class="sxs-lookup"><span data-stu-id="1e0ff-116">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="1e0ff-117">Další podrobnosti najdete v tématu [odhad iterativní fáze](/quantum/libraries/characterization#iterative-phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="1e0ff-117">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>



## <a name="output--double"></a><span data-ttu-id="1e0ff-118">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1e0ff-118">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1e0ff-119">Odhad $ \hat{\phi} $ pro stav energie $ \phi $ generátoru, reprezentovaný $U $.</span><span class="sxs-lookup"><span data-stu-id="1e0ff-119">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the generator represented by $U$.</span></span>