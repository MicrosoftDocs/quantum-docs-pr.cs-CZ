---
uid: Microsoft.Quantum.Canon.MultiplexZ
title: Operace MultiplexZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits.
ms.openlocfilehash: 364d23a0e57a2510f069b6db66b085368f20162e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206064"
---
# <a name="multiplexz-operation"></a><span data-ttu-id="ae5dc-102">Operace MultiplexZ</span><span class="sxs-lookup"><span data-stu-id="ae5dc-102">MultiplexZ operation</span></span>

<span data-ttu-id="ae5dc-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ae5dc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ae5dc-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ae5dc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ae5dc-105">Použije rotaci Pauli Z, která je splněná na poli qubits.</span><span class="sxs-lookup"><span data-stu-id="ae5dc-105">Applies a Pauli Z rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexZ (coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="ae5dc-106">Popis</span><span class="sxs-lookup"><span data-stu-id="ae5dc-106">Description</span></span>

<span data-ttu-id="ae5dc-107">To platí pro vynásobenou jednotnou operaci, která provádí rotace pomocí úhlu $ \ theta_j $ o qubit Pauli operator $Z $, pokud je kontrolováno stavem $n $-qubit číslo $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="ae5dc-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="ae5dc-108">Konkrétně tuto operaci může představovat jednotná</span><span class="sxs-lookup"><span data-stu-id="ae5dc-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="ae5dc-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="ae5dc-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="ae5dc-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="ae5dc-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="ae5dc-111">Vstup</span><span class="sxs-lookup"><span data-stu-id="ae5dc-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="ae5dc-112">koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ae5dc-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ae5dc-113">Pole až do $2 ^ n $ koeficienty $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="ae5dc-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="ae5dc-114">$J $ th součinitel indexuje číselný stav $ \ket{j} $ kódovaný ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="ae5dc-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="ae5dc-115">ovládací prvek: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ae5dc-115">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ae5dc-116">$n $-qubit registr ovládacího prvku, který kóduje číselný stav $ \ket{j} $ ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="ae5dc-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ae5dc-117">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ae5dc-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ae5dc-118">Jeden qubit registr, který je otočen $e ^ {i P \ theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="ae5dc-118">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ae5dc-119">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ae5dc-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ae5dc-120">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ae5dc-120">Remarks</span></span>

<span data-ttu-id="ae5dc-121">`coefficients` budou doplněny elementy $ \ theta_j = $0,0, pokud je zadána méně než $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="ae5dc-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="ae5dc-122">Reference</span><span class="sxs-lookup"><span data-stu-id="ae5dc-122">References</span></span>

- <span data-ttu-id="ae5dc-123">Shrnutí logických okruhů Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="ae5dc-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="ae5dc-124">Viz také</span><span class="sxs-lookup"><span data-stu-id="ae5dc-124">See Also</span></span>

- [<span data-ttu-id="ae5dc-125">Microsoft. proApproximatelyMultiplexZ. Canon.</span><span class="sxs-lookup"><span data-stu-id="ae5dc-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexZ)