---
uid: Microsoft.Quantum.Simulation.EstimateEnergy
title: Operace EstimateEnergy
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergy
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: f9243557718e12d168afadbf641492291afd1704
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856769"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="d2cf7-102">Operace EstimateEnergy</span><span class="sxs-lookup"><span data-stu-id="d2cf7-102">EstimateEnergy operation</span></span>

<span data-ttu-id="d2cf7-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="d2cf7-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="d2cf7-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d2cf7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d2cf7-105">Provede přípravu stavu pomocí `statePrepUnitary` objektu na automaticky přidělený odhad fáze stavu vstupu s ohledem na `qpeUnitary` výsledný stav pomocí `phaseEstAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="d2cf7-105">Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation EstimateEnergy (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a><span data-ttu-id="d2cf7-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="d2cf7-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="d2cf7-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d2cf7-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d2cf7-108">Počet qubits, které se používají k provedení simulace.</span><span class="sxs-lookup"><span data-stu-id="d2cf7-108">Number of qubits used to perform simulation.</span></span>


### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="d2cf7-109">statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d2cf7-109">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d2cf7-110">Oracle představující stavovou přípravu počátečního dynamického generátoru.</span><span class="sxs-lookup"><span data-stu-id="d2cf7-110">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a><span data-ttu-id="d2cf7-111">qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="d2cf7-111">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d2cf7-112">Oracle reprezentující jednotkový operátor $U $ představující vývoj pro čas $ \delta t $ v rámci dynamického generátoru s uzemněným stavem $ \ket{\phi} $ a pozemní energie $E = \phi \\ , \delta t $.</span><span class="sxs-lookup"><span data-stu-id="d2cf7-112">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="d2cf7-113">phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d2cf7-113">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="d2cf7-114">Operace, která provádí odhad fáze pro danou jednotkovou operaci.</span><span class="sxs-lookup"><span data-stu-id="d2cf7-114">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="d2cf7-115">Další podrobnosti najdete v tématu [odhad iterativní fáze](/quantum/libraries/characterization#iterative-phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="d2cf7-115">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>



## <a name="output--double"></a><span data-ttu-id="d2cf7-116">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d2cf7-116">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d2cf7-117">Odhad $ \hat{\phi} $ z mletého stavu energie $ \phi $ základní energie generátoru, reprezentovaný $U $.</span><span class="sxs-lookup"><span data-stu-id="d2cf7-117">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the ground state energy of the generator represented by $U$.</span></span>