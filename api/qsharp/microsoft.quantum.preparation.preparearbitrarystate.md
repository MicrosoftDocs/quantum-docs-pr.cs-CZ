---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryState
title: Operace PrepareArbitraryState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryState
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: 18f45da601b02fc5f83936b086323e31a66fc20b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708668"
---
# <a name="preparearbitrarystate-operation"></a><span data-ttu-id="b0189-102">Operace PrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="b0189-102">PrepareArbitraryState operation</span></span>

<span data-ttu-id="b0189-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="b0189-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="b0189-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b0189-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b0189-105">Vzhledem k sadě koeficientů a registru s kódováním nenaloženého formátu Little endian připraví stav v tomto registru, který je popsán v daných koeficientech.</span><span class="sxs-lookup"><span data-stu-id="b0189-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.</span></span>

```qsharp
operation PrepareArbitraryState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="b0189-106">Popis</span><span class="sxs-lookup"><span data-stu-id="b0189-106">Description</span></span>

<span data-ttu-id="b0189-107">Tato operace připraví libovolný stav pro každý kraj $ \ket{\psi} $ pomocí složitých koeficientů $r _j e ^ {i t_j} $ ze stavu $n $-qubit výpočetního základu $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="b0189-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="b0189-108">Konkrétně je možné akci této operace simulovat pomocí jednotkové transformace $U $, která funguje se stavem vše – nula jako</span><span class="sxs-lookup"><span data-stu-id="b0189-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="b0189-109">$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="b0189-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="b0189-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="b0189-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="b0189-111">Vstup</span><span class="sxs-lookup"><span data-stu-id="b0189-111">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="b0189-112">koeficienty: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="b0189-112">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="b0189-113">Pole až do $2 ^ n $ složitých koeficientů reprezentovaných jejich absolutní hodnotou a fází $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="b0189-113">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="b0189-114">$J $ th součinitel indexuje číselný stav $ \ket{j} $ kódovaný ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="b0189-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="b0189-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b0189-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b0189-116">Qubit registruje číselné kódování stavů ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="b0189-116">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="b0189-117">Očekává se, že se má inicializovat ve stavu výpočtu $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="b0189-117">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b0189-118">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b0189-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b0189-119">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b0189-119">Remarks</span></span>

<span data-ttu-id="b0189-120">Negativní vstupní koeficienty $r _j < $0 budou považovány za kladné s hodnotou $ | r_j | $.</span><span class="sxs-lookup"><span data-stu-id="b0189-120">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="b0189-121">`coefficients` bude doplněna elementy $ (r_j, t_j) = (0,0, 0,0) $, pokud je zadáno méně než $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="b0189-121">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="b0189-122">Odkazy</span><span class="sxs-lookup"><span data-stu-id="b0189-122">References</span></span>

- <span data-ttu-id="b0189-123">Shrnutí logických okruhů Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="b0189-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="b0189-124">Viz také</span><span class="sxs-lookup"><span data-stu-id="b0189-124">See Also</span></span>

- [<span data-ttu-id="b0189-125">Microsoft. Přípravno. Preparation. ApproximatelyPrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="b0189-125">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)