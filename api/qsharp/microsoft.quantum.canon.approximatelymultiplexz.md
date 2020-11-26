---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexZ
title: Operace ApproximatelyMultiplexZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 5e254c2b2d6cbf29b428f4d55aef0e61356e3480
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217097"
---
# <a name="approximatelymultiplexz-operation"></a><span data-ttu-id="a6b69-102">Operace ApproximatelyMultiplexZ</span><span class="sxs-lookup"><span data-stu-id="a6b69-102">ApproximatelyMultiplexZ operation</span></span>

<span data-ttu-id="a6b69-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a6b69-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a6b69-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a6b69-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a6b69-105">Aplikuje Pauli Z rotace v poli qubits a zkrátí krátké úhly otočení na základě dané tolerance.</span><span class="sxs-lookup"><span data-stu-id="a6b69-105">Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyMultiplexZ (tolerance : Double, coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="a6b69-106">Popis</span><span class="sxs-lookup"><span data-stu-id="a6b69-106">Description</span></span>

<span data-ttu-id="a6b69-107">To platí pro vynásobenou jednotnou operaci, která provádí rotace pomocí úhlu $ \ theta_j $ o qubit Pauli operator $Z $, pokud je kontrolováno stavem $n $-qubit číslo $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="a6b69-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="a6b69-108">Konkrétně tuto operaci může představovat jednotná</span><span class="sxs-lookup"><span data-stu-id="a6b69-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="a6b69-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="a6b69-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="a6b69-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="a6b69-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="a6b69-111">Vstup</span><span class="sxs-lookup"><span data-stu-id="a6b69-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="a6b69-112">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a6b69-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a6b69-113">Tolerance, pod kterou jsou malé koeficienty zkráceny.</span><span class="sxs-lookup"><span data-stu-id="a6b69-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="a6b69-114">koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a6b69-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a6b69-115">Pole až do $2 ^ n $ koeficienty $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="a6b69-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="a6b69-116">$J $ th součinitel indexuje číselný stav $ \ket{j} $ kódovaný ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="a6b69-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="a6b69-117">ovládací prvek: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a6b69-117">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a6b69-118">$n $-qubit registr ovládacího prvku, který kóduje číselný stav $ \ket{j} $ ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="a6b69-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a6b69-119">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a6b69-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a6b69-120">Jeden qubit registr, který je otočen $e ^ {i P \ theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="a6b69-120">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a6b69-121">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a6b69-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a6b69-122">Poznámky</span><span class="sxs-lookup"><span data-stu-id="a6b69-122">Remarks</span></span>

<span data-ttu-id="a6b69-123">`coefficients` budou doplněny elementy $ \ theta_j = $0,0, pokud je zadána méně než $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="a6b69-123">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="a6b69-124">Reference</span><span class="sxs-lookup"><span data-stu-id="a6b69-124">References</span></span>

- <span data-ttu-id="a6b69-125">Shrnutí logických okruhů Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="a6b69-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="a6b69-126">Viz také</span><span class="sxs-lookup"><span data-stu-id="a6b69-126">See Also</span></span>

- [<span data-ttu-id="a6b69-127">Microsoft. proMultiplexZ. Canon.</span><span class="sxs-lookup"><span data-stu-id="a6b69-127">Microsoft.Quantum.Canon.MultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.MultiplexZ)