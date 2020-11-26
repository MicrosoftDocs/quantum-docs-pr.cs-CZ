---
uid: Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary
title: Operace ApproximatelyApplyDiagonalUnitary
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 0a05b8a5891977a08ee2ae6a996657c6a8f3d792
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217114"
---
# <a name="approximatelyapplydiagonalunitary-operation"></a><span data-ttu-id="cb864-102">Operace ApproximatelyApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="cb864-102">ApproximatelyApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="cb864-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cb864-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cb864-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cb864-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cb864-105">Aplikuje pole komplexních fází na číselné základní stavy registru qubits a zkrátí krátké úhly natočení podle dané tolerance.</span><span class="sxs-lookup"><span data-stu-id="cb864-105">Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyApplyDiagonalUnitary (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="cb864-106">Popis</span><span class="sxs-lookup"><span data-stu-id="cb864-106">Description</span></span>

<span data-ttu-id="cb864-107">Tato operace implementuje diagonální čárku, která aplikuje komplexní fázi $e ^ {i \ theta_j} $ ve stavu $n $-qubit číslo $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="cb864-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="cb864-108">Konkrétně tuto operaci může představovat jednotná</span><span class="sxs-lookup"><span data-stu-id="cb864-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="cb864-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.</span><span class="sxs-lookup"><span data-stu-id="cb864-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="cb864-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="cb864-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="cb864-111">Vstup</span><span class="sxs-lookup"><span data-stu-id="cb864-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="cb864-112">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cb864-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cb864-113">Tolerance, pod kterou jsou malé koeficienty zkráceny.</span><span class="sxs-lookup"><span data-stu-id="cb864-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="cb864-114">koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="cb864-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="cb864-115">Pole až do $2 ^ n $ koeficienty $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="cb864-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="cb864-116">$J $ th součinitel indexuje číselný stav $ \ket{j} $ kódovaný ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="cb864-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="cb864-117">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="cb864-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="cb864-118">$n $-qubit registr ovládacího prvku, který kóduje číselný stav $ \ket{j} $ ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="cb864-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cb864-119">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cb864-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cb864-120">Poznámky</span><span class="sxs-lookup"><span data-stu-id="cb864-120">Remarks</span></span>

<span data-ttu-id="cb864-121">`coefficients` budou doplněny elementy $ \ theta_j = $0,0, pokud je zadána méně než $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="cb864-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="cb864-122">Reference</span><span class="sxs-lookup"><span data-stu-id="cb864-122">References</span></span>

- <span data-ttu-id="cb864-123">Shrnutí logických okruhů Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="cb864-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="cb864-124">Viz také</span><span class="sxs-lookup"><span data-stu-id="cb864-124">See Also</span></span>

- [<span data-ttu-id="cb864-125">Microsoft. proApplyDiagonalUnitary. Canon.</span><span class="sxs-lookup"><span data-stu-id="cb864-125">Microsoft.Quantum.Canon.ApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApplyDiagonalUnitary)