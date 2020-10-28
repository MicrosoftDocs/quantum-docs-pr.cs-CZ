---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: Operace EstimateOverlapBetweenStates
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: 58a367c7ff7d13ac5c1eb1588fb8dac66414776c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698729"
---
# <a name="estimateoverlapbetweenstates-operation"></a><span data-ttu-id="84eb6-102">Operace EstimateOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="84eb6-102">EstimateOverlapBetweenStates operation</span></span>

<span data-ttu-id="84eb6-103">Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="84eb6-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="84eb6-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="84eb6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="84eb6-105">Vzhledem k tomu, že jednotlivé operace připravují kopie stavu, odhaduje se čtvercový překryv mezi stavy, které jsou připraveny jednotlivými operacemi.</span><span class="sxs-lookup"><span data-stu-id="84eb6-105">Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="84eb6-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="84eb6-106">Input</span></span>

### <a name="preparation1--qubit--unit-adj"></a><span data-ttu-id="84eb6-107">preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotky](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="84eb6-107">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="84eb6-108">První z těchto dvou operací přípravy stavu, které mají být porovnány.</span><span class="sxs-lookup"><span data-stu-id="84eb6-108">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit-adj"></a><span data-ttu-id="84eb6-109">preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotky](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="84eb6-109">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="84eb6-110">Druhý ze dvou operací přípravení stavu, které mají být porovnány.</span><span class="sxs-lookup"><span data-stu-id="84eb6-110">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="84eb6-111">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="84eb6-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="84eb6-112">Počet qubits, které jsou `commonPreparation` , `preparation1` a `preparation2` všechny Act.</span><span class="sxs-lookup"><span data-stu-id="84eb6-112">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="84eb6-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="84eb6-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="84eb6-114">Počet měření, která se mají použít při odhadování překrytí</span><span class="sxs-lookup"><span data-stu-id="84eb6-114">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="84eb6-115">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="84eb6-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="84eb6-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="84eb6-116">Remarks</span></span>

<span data-ttu-id="84eb6-117">Tato operace používá test prohození k vyhledání $ $ \begin{align} \left | \braket{00\cdots 0 | V ^ {\dagger} U | 00 \ cdots 0} \right | ^ 2 \end{align} $ $, kde $U $ je jednotková reprezentace akce `preparation1` a kde $V $ odpovídá `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="84eb6-117">This operation uses the SWAP test to find $$ \begin{align} \left| \braket{00\cdots 0 | V^{\dagger} U | 00\cdots 0} \right|^2 \end{align} $$ where $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="see-also"></a><span data-ttu-id="84eb6-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="84eb6-118">See Also</span></span>

- [<span data-ttu-id="84eb6-119">Microsoft. proEstimateRealOverlapBetweenStates. Popis.</span><span class="sxs-lookup"><span data-stu-id="84eb6-119">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [<span data-ttu-id="84eb6-120">Microsoft. proEstimateImagOverlapBetweenStates. Popis.</span><span class="sxs-lookup"><span data-stu-id="84eb6-120">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)