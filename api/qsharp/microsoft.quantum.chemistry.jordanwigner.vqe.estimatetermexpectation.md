---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Operace EstimateTermExpectation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 3f0ff5037b1424abb6fb318bd49ffd89f545822d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224645"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="cfabf-102">Operace EstimateTermExpectation</span><span class="sxs-lookup"><span data-stu-id="cfabf-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="cfabf-103">Obor názvů: [Microsoft. JordanWigner. chemie.. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="cfabf-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="cfabf-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="cfabf-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="cfabf-105">Vypočítá spotřebu energie spojenou s daným Jordan-Wigner Hamiltonian období</span><span class="sxs-lookup"><span data-stu-id="cfabf-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="cfabf-106">Popis</span><span class="sxs-lookup"><span data-stu-id="cfabf-106">Description</span></span>

<span data-ttu-id="cfabf-107">Tato operace odhadne očekávanou hodnotu přidruženou ke každému operátoru měření a vynásobí ji odpovídajícím koeficientem pomocí vzorkování.</span><span class="sxs-lookup"><span data-stu-id="cfabf-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="cfabf-108">Výsledky jsou shrnuty do proměnné, která obsahuje energii Jordan-Wignerho termínu.</span><span class="sxs-lookup"><span data-stu-id="cfabf-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="cfabf-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="cfabf-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit--is-adj"></a><span data-ttu-id="cfabf-110">inputStateUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="cfabf-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="cfabf-111">Jednotná použití pro přípravu stavu.</span><span class="sxs-lookup"><span data-stu-id="cfabf-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="cfabf-112">Ops: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="cfabf-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="cfabf-113">Měřicí operátory Jordan-Wignerho termínu.</span><span class="sxs-lookup"><span data-stu-id="cfabf-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="cfabf-114">coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="cfabf-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="cfabf-115">Koeficienty Jordan-Wignerho termínu.</span><span class="sxs-lookup"><span data-stu-id="cfabf-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="cfabf-116">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cfabf-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cfabf-117">Počet qubits potřebných pro simulaci molekulárního systému.</span><span class="sxs-lookup"><span data-stu-id="cfabf-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="cfabf-118">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cfabf-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cfabf-119">Počet vzorků, které se mají použít pro odhad očekávaného termínu.</span><span class="sxs-lookup"><span data-stu-id="cfabf-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="cfabf-120">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cfabf-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cfabf-121">Energie přidružená k Jordan-Wignermu období.</span><span class="sxs-lookup"><span data-stu-id="cfabf-121">The energy associated to the Jordan-Wigner term.</span></span>