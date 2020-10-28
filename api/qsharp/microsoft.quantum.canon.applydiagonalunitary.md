---
uid: Microsoft.Quantum.Canon.ApplyDiagonalUnitary
title: Operace ApplyDiagonalUnitary
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits.
ms.openlocfilehash: 6ecacf6e4fe2c505036de208c8aeb5350e479e3c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705385"
---
# <a name="applydiagonalunitary-operation"></a><span data-ttu-id="d9606-102">Operace ApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="d9606-102">ApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="d9606-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d9606-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d9606-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d9606-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d9606-105">Aplikuje pole komplexních fází na číselné stavy registru qubits.</span><span class="sxs-lookup"><span data-stu-id="d9606-105">Applies an array of complex phases to numeric basis states of a register of qubits.</span></span>

```qsharp
operation ApplyDiagonalUnitary (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="d9606-106">Popis</span><span class="sxs-lookup"><span data-stu-id="d9606-106">Description</span></span>

<span data-ttu-id="d9606-107">Tato operace implementuje diagonální čárku, která aplikuje komplexní fázi $e ^ {i \ theta_j} $ ve stavu $n $-qubit číslo $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="d9606-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="d9606-108">Konkrétně tuto operaci může představovat jednotná</span><span class="sxs-lookup"><span data-stu-id="d9606-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="d9606-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.</span><span class="sxs-lookup"><span data-stu-id="d9606-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="d9606-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="d9606-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="d9606-111">Vstup</span><span class="sxs-lookup"><span data-stu-id="d9606-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="d9606-112">koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d9606-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d9606-113">Pole až do $2 ^ n $ koeficienty $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="d9606-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="d9606-114">$J $ th součinitel indexuje číselný stav $ \ket{j} $ kódovaný ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="d9606-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="d9606-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d9606-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d9606-116">$n $-qubit registr ovládacího prvku, který kóduje číselný stav $ \ket{j} $ ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="d9606-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d9606-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d9606-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d9606-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="d9606-118">Remarks</span></span>

<span data-ttu-id="d9606-119">`coefficients` budou doplněny elementy $ \ theta_j = $0,0, pokud je zadána méně než $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="d9606-119">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="d9606-120">Odkazy</span><span class="sxs-lookup"><span data-stu-id="d9606-120">References</span></span>

- <span data-ttu-id="d9606-121">Shrnutí logických okruhů Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="d9606-121">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="d9606-122">Viz také</span><span class="sxs-lookup"><span data-stu-id="d9606-122">See Also</span></span>

- [<span data-ttu-id="d9606-123">Microsoft. proApproximatelyApplyDiagonalUnitary. Canon.</span><span class="sxs-lookup"><span data-stu-id="d9606-123">Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary)