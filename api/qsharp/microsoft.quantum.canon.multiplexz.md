---
uid: Microsoft.Quantum.Canon.MultiplexZ
title: Operace MultiplexZ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits.
ms.openlocfilehash: dccfe86104263e23794bce33279e8748f11f5a54
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852427"
---
# <a name="multiplexz-operation"></a><span data-ttu-id="42545-102">Operace MultiplexZ</span><span class="sxs-lookup"><span data-stu-id="42545-102">MultiplexZ operation</span></span>

<span data-ttu-id="42545-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="42545-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="42545-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="42545-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="42545-105">Použije rotaci Pauli Z, která je splněná na poli qubits.</span><span class="sxs-lookup"><span data-stu-id="42545-105">Applies a Pauli Z rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexZ (coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="42545-106">Popis</span><span class="sxs-lookup"><span data-stu-id="42545-106">Description</span></span>

<span data-ttu-id="42545-107">To platí pro vynásobenou jednotnou operaci, která provádí rotace pomocí úhlu $ \ theta_j $ o qubit Pauli operator $Z $, pokud je kontrolováno stavem $n $-qubit číslo $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="42545-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="42545-108">Konkrétně tuto operaci může představovat jednotná</span><span class="sxs-lookup"><span data-stu-id="42545-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="42545-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="42545-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="42545-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="42545-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="42545-111">Vstup</span><span class="sxs-lookup"><span data-stu-id="42545-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="42545-112">koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="42545-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="42545-113">Pole až do $2 ^ n $ koeficienty $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="42545-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="42545-114">$J $ th součinitel indexuje číselný stav $ \ket{j} $ kódovaný ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="42545-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="42545-115">ovládací prvek: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="42545-115">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="42545-116">$n $-qubit registr ovládacího prvku, který kóduje číselný stav $ \ket{j} $ ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="42545-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="42545-117">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="42545-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="42545-118">Jeden qubit registr, který je otočen $e ^ {i P \ theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="42545-118">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="42545-119">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="42545-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="42545-120">Poznámky</span><span class="sxs-lookup"><span data-stu-id="42545-120">Remarks</span></span>

<span data-ttu-id="42545-121">`coefficients` budou doplněny elementy $ \ theta_j = $0,0, pokud je zadána méně než $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="42545-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="42545-122">Reference</span><span class="sxs-lookup"><span data-stu-id="42545-122">References</span></span>

- <span data-ttu-id="42545-123">Shrnutí logických okruhů Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="42545-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="42545-124">Viz také</span><span class="sxs-lookup"><span data-stu-id="42545-124">See Also</span></span>

- [<span data-ttu-id="42545-125">Microsoft. proApproximatelyMultiplexZ. Canon.</span><span class="sxs-lookup"><span data-stu-id="42545-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexZ)