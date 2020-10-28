---
uid: Microsoft.Quantum.Simulation.AdiabaticStateEnergyUnitary
title: Operace AdiabaticStateEnergyUnitary
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AdiabaticStateEnergyUnitary
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: 642f6a0af76b3b2d0703f0377c379abf33ecee71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708122"
---
# <a name="adiabaticstateenergyunitary-operation"></a><span data-ttu-id="5058a-102">Operace AdiabaticStateEnergyUnitary</span><span class="sxs-lookup"><span data-stu-id="5058a-102">AdiabaticStateEnergyUnitary operation</span></span>

<span data-ttu-id="5058a-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="5058a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="5058a-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5058a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5058a-105">Provede přípravu stavu pomocí `statePrepUnitary` příkazu ve stavu vstupu, následovaným přípravou stavu adiabatic pomocí a `adiabaticUnitary` , a konečně odhadem fáze s ohledem na `qpeUnitary` výsledný stav pomocí `phaseEstAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="5058a-105">Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation AdiabaticStateEnergyUnitary (statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double), qubits : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="5058a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5058a-106">Input</span></span>

### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="5058a-107">statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5058a-107">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="5058a-108">Oracle představující stavovou přípravu počátečního dynamického generátoru.</span><span class="sxs-lookup"><span data-stu-id="5058a-108">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="adiabaticunitary--qubit--unit"></a><span data-ttu-id="5058a-109">adiabaticUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5058a-109">adiabaticUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="5058a-110">Oracle představující algoritmus vývoje adiabatic, který se použije k implementaci Sweep do konečného stavu algoritmu.</span><span class="sxs-lookup"><span data-stu-id="5058a-110">An oracle representing the adiabatic evolution algorithm to be used to implement the sweeps to the final state of the algorithm.</span></span>


### <a name="qpeunitary--qubit--unit-adj--ctl"></a><span data-ttu-id="5058a-111">qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotky](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="5058a-111">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="5058a-112">Oracle reprezentující jednotkový operátor $U $ představující vývoj pro čas $ \delta t $ v rámci dynamického generátoru s uzemněným stavem $ \ket{\phi} $ a pozemní energie $E = \phi \\ , \delta t $.</span><span class="sxs-lookup"><span data-stu-id="5058a-112">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="5058a-113">phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5058a-113">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="5058a-114">Operace, která provádí odhad fáze pro danou jednotkovou operaci.</span><span class="sxs-lookup"><span data-stu-id="5058a-114">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="5058a-115">Další podrobnosti najdete v tématu [odhad iterativní fáze](/quantum/libraries/characterization#iterative-phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="5058a-115">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="5058a-116">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5058a-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5058a-117">Registr qubits, který se má použít k provedení simulace.</span><span class="sxs-lookup"><span data-stu-id="5058a-117">A register of qubits to be used to perform the simulation.</span></span>



## <a name="output--double"></a><span data-ttu-id="5058a-118">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5058a-118">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5058a-119">Odhad $ \hat{\phi} $ pro stav energie $ \phi $ generátoru, reprezentovaný $U $.</span><span class="sxs-lookup"><span data-stu-id="5058a-119">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the generator represented by $U$.</span></span>