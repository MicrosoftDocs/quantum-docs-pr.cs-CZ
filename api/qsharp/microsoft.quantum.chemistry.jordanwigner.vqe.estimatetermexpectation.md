---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Operace EstimateTermExpectation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 7df4c1ea859140a669698434c6f8a786ea3bc2ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835666"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="ff100-102">Operace EstimateTermExpectation</span><span class="sxs-lookup"><span data-stu-id="ff100-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="ff100-103">Obor názvů: [Microsoft. JordanWigner. chemie.. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="ff100-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="ff100-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="ff100-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="ff100-105">Vypočítá spotřebu energie spojenou s daným Jordan-Wigner Hamiltonian období</span><span class="sxs-lookup"><span data-stu-id="ff100-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="ff100-106">Popis</span><span class="sxs-lookup"><span data-stu-id="ff100-106">Description</span></span>

<span data-ttu-id="ff100-107">Tato operace odhadne očekávanou hodnotu přidruženou ke každému operátoru měření a vynásobí ji odpovídajícím koeficientem pomocí vzorkování.</span><span class="sxs-lookup"><span data-stu-id="ff100-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="ff100-108">Výsledky jsou shrnuty do proměnné, která obsahuje energii Jordan-Wignerho termínu.</span><span class="sxs-lookup"><span data-stu-id="ff100-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="ff100-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="ff100-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit--is-adj"></a><span data-ttu-id="ff100-110">inputStateUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="ff100-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="ff100-111">Jednotná použití pro přípravu stavu.</span><span class="sxs-lookup"><span data-stu-id="ff100-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="ff100-112">Ops: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="ff100-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="ff100-113">Měřicí operátory Jordan-Wignerho termínu.</span><span class="sxs-lookup"><span data-stu-id="ff100-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="ff100-114">coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ff100-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ff100-115">Koeficienty Jordan-Wignerho termínu.</span><span class="sxs-lookup"><span data-stu-id="ff100-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="ff100-116">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ff100-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ff100-117">Počet qubits potřebných pro simulaci molekulárního systému.</span><span class="sxs-lookup"><span data-stu-id="ff100-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="ff100-118">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ff100-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ff100-119">Počet vzorků, které se mají použít pro odhad očekávaného termínu.</span><span class="sxs-lookup"><span data-stu-id="ff100-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="ff100-120">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ff100-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ff100-121">Energie přidružená k Jordan-Wignermu období.</span><span class="sxs-lookup"><span data-stu-id="ff100-121">The energy associated to the Jordan-Wigner term.</span></span>