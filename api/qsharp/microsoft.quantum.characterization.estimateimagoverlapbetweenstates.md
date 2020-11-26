---
uid: Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates
title: Operace EstimateImagOverlapBetweenStates
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateImagOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.
ms.openlocfilehash: b192abc4ba37d126bf46f94c66cb87fe3bbec4c8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216196"
---
# <a name="estimateimagoverlapbetweenstates-operation"></a><span data-ttu-id="e4cea-102">Operace EstimateImagOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="e4cea-102">EstimateImagOverlapBetweenStates operation</span></span>

<span data-ttu-id="e4cea-103">Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="e4cea-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="e4cea-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e4cea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e4cea-105">Vzhledem k tomu, že jednotlivé operace připravují kopie stavu, odhadne imaginární část překrytí mezi stavy, které jsou připraveny jednotlivými operacemi.</span><span class="sxs-lookup"><span data-stu-id="e4cea-105">Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateImagOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="e4cea-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e4cea-106">Input</span></span>

### <a name="commonpreparation--qubit--unit--is-adj"></a><span data-ttu-id="e4cea-107">commonPreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="e4cea-107">commonPreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="e4cea-108">Operace, která připraví pevný vstupní stav.</span><span class="sxs-lookup"><span data-stu-id="e4cea-108">An operation that prepares a fixed input state.</span></span>


### <a name="preparation1--qubit--unit--is-adj--ctl"></a><span data-ttu-id="e4cea-109">preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="e4cea-109">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="e4cea-110">První z těchto dvou operací přípravy stavu, které mají být porovnány.</span><span class="sxs-lookup"><span data-stu-id="e4cea-110">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit--is-adj--ctl"></a><span data-ttu-id="e4cea-111">preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="e4cea-111">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="e4cea-112">Druhý ze dvou operací přípravení stavu, které mají být porovnány.</span><span class="sxs-lookup"><span data-stu-id="e4cea-112">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="e4cea-113">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e4cea-113">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e4cea-114">Počet qubits, které jsou `commonPreparation` , `preparation1` a `preparation2` všechny Act.</span><span class="sxs-lookup"><span data-stu-id="e4cea-114">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="e4cea-115">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e4cea-115">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e4cea-116">Počet měření, která se mají použít při odhadování překrytí</span><span class="sxs-lookup"><span data-stu-id="e4cea-116">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="e4cea-117">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e4cea-117">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="e4cea-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e4cea-118">Remarks</span></span>

<span data-ttu-id="e4cea-119">Tato operace používá test Hadamard k vyhledání imaginární části pro $ $ \begin{align} \braket{\psi | V ^ {\dagger} U | \psi} \end{align} $ $ kde $ \ket{\psi} $ je stav, který připravil `commonPreparation` , $U $ je jednotková reprezentace akce `preparation1` a kde $V $ odpovídá `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="e4cea-119">This operation uses the Hadamard test to find the imaginary part of $$ \begin{align} \braket{\psi | V^{\dagger} U | \psi} \end{align} $$ where $\ket{\psi}$ is the state prepared by `commonPreparation`, $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="references"></a><span data-ttu-id="e4cea-120">Reference</span><span class="sxs-lookup"><span data-stu-id="e4cea-120">References</span></span>

- <span data-ttu-id="e4cea-121">Aharonov *et al.* [quant-pH/0511096](https://arxiv.org/abs/quant-ph/0511096).</span><span class="sxs-lookup"><span data-stu-id="e4cea-121">Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).</span></span>

## <a name="see-also"></a><span data-ttu-id="e4cea-122">Viz také</span><span class="sxs-lookup"><span data-stu-id="e4cea-122">See Also</span></span>

- [<span data-ttu-id="e4cea-123">Microsoft. proEstimateRealOverlapBetweenStates. Popis.</span><span class="sxs-lookup"><span data-stu-id="e4cea-123">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [<span data-ttu-id="e4cea-124">Microsoft. proEstimateOverlapBetweenStates. Popis.</span><span class="sxs-lookup"><span data-stu-id="e4cea-124">Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)