---
uid: Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary
title: Operace ApproximatelyApplyDiagonalUnitary
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 5d8f6646c124f4296b9cd2abd71e73de5a530e55
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850339"
---
# <a name="approximatelyapplydiagonalunitary-operation"></a><span data-ttu-id="513b6-102">Operace ApproximatelyApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="513b6-102">ApproximatelyApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="513b6-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="513b6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="513b6-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="513b6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="513b6-105">Aplikuje pole komplexních fází na číselné základní stavy registru qubits a zkrátí krátké úhly natočení podle dané tolerance.</span><span class="sxs-lookup"><span data-stu-id="513b6-105">Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyApplyDiagonalUnitary (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="513b6-106">Popis</span><span class="sxs-lookup"><span data-stu-id="513b6-106">Description</span></span>

<span data-ttu-id="513b6-107">Tato operace implementuje diagonální čárku, která aplikuje komplexní fázi $e ^ {i \ theta_j} $ ve stavu $n $-qubit číslo $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="513b6-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="513b6-108">Konkrétně tuto operaci může představovat jednotná</span><span class="sxs-lookup"><span data-stu-id="513b6-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="513b6-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.</span><span class="sxs-lookup"><span data-stu-id="513b6-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="513b6-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="513b6-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="513b6-111">Vstup</span><span class="sxs-lookup"><span data-stu-id="513b6-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="513b6-112">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="513b6-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="513b6-113">Tolerance, pod kterou jsou malé koeficienty zkráceny.</span><span class="sxs-lookup"><span data-stu-id="513b6-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="513b6-114">koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="513b6-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="513b6-115">Pole až do $2 ^ n $ koeficienty $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="513b6-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="513b6-116">$J $ th součinitel indexuje číselný stav $ \ket{j} $ kódovaný ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="513b6-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="513b6-117">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="513b6-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="513b6-118">$n $-qubit registr ovládacího prvku, který kóduje číselný stav $ \ket{j} $ ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="513b6-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="513b6-119">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="513b6-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="513b6-120">Poznámky</span><span class="sxs-lookup"><span data-stu-id="513b6-120">Remarks</span></span>

<span data-ttu-id="513b6-121">`coefficients` budou doplněny elementy $ \ theta_j = $0,0, pokud je zadána méně než $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="513b6-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="513b6-122">Reference</span><span class="sxs-lookup"><span data-stu-id="513b6-122">References</span></span>

- <span data-ttu-id="513b6-123">Shrnutí logických okruhů Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="513b6-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="513b6-124">Viz také</span><span class="sxs-lookup"><span data-stu-id="513b6-124">See Also</span></span>

- [<span data-ttu-id="513b6-125">Microsoft. proApplyDiagonalUnitary. Canon.</span><span class="sxs-lookup"><span data-stu-id="513b6-125">Microsoft.Quantum.Canon.ApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApplyDiagonalUnitary)