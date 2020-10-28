---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Operace EstimateTermExpectation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: ef689c55f966e63a2ab8bcdccf99d9cb5e6d3a4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698368"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="8ee8e-102">Operace EstimateTermExpectation</span><span class="sxs-lookup"><span data-stu-id="8ee8e-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="8ee8e-103">Obor názvů: [Microsoft. JordanWigner. chemie.. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="8ee8e-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="8ee8e-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8ee8e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8ee8e-105">Vypočítá spotřebu energie spojenou s daným Jordan-Wigner Hamiltonian období</span><span class="sxs-lookup"><span data-stu-id="8ee8e-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="8ee8e-106">Popis</span><span class="sxs-lookup"><span data-stu-id="8ee8e-106">Description</span></span>

<span data-ttu-id="8ee8e-107">Tato operace odhadne očekávanou hodnotu přidruženou ke každému operátoru měření a vynásobí ji odpovídajícím koeficientem pomocí vzorkování.</span><span class="sxs-lookup"><span data-stu-id="8ee8e-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="8ee8e-108">Výsledky jsou shrnuty do proměnné, která obsahuje energii Jordan-Wignerho termínu.</span><span class="sxs-lookup"><span data-stu-id="8ee8e-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="8ee8e-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="8ee8e-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit-adj"></a><span data-ttu-id="8ee8e-110">inputStateUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotky](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="8ee8e-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="8ee8e-111">Jednotná použití pro přípravu stavu.</span><span class="sxs-lookup"><span data-stu-id="8ee8e-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="8ee8e-112">Ops: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="8ee8e-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="8ee8e-113">Měřicí operátory Jordan-Wignerho termínu.</span><span class="sxs-lookup"><span data-stu-id="8ee8e-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="8ee8e-114">coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="8ee8e-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="8ee8e-115">Koeficienty Jordan-Wignerho termínu.</span><span class="sxs-lookup"><span data-stu-id="8ee8e-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="8ee8e-116">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8ee8e-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8ee8e-117">Počet qubits potřebných pro simulaci molekulárního systému.</span><span class="sxs-lookup"><span data-stu-id="8ee8e-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="8ee8e-118">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8ee8e-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8ee8e-119">Počet vzorků, které se mají použít pro odhad očekávaného termínu.</span><span class="sxs-lookup"><span data-stu-id="8ee8e-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="8ee8e-120">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8ee8e-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8ee8e-121">Energie přidružená k Jordan-Wignermu období.</span><span class="sxs-lookup"><span data-stu-id="8ee8e-121">The energy associated to the Jordan-Wigner term.</span></span>