---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryState
title: Operace PrepareArbitraryState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryState
qsharp.summary: >-
  > [!WARNING]

  > PrepareArbitraryState has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: 18a1e86f8e110a8f48d7dd50961e1f1f471ffc4e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190695"
---
# <a name="preparearbitrarystate-operation"></a><span data-ttu-id="1b344-102">Operace PrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="1b344-102">PrepareArbitraryState operation</span></span>

<span data-ttu-id="1b344-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="1b344-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="1b344-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1b344-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="1b344-105">PrepareArbitraryState se už nepoužívá.</span><span class="sxs-lookup"><span data-stu-id="1b344-105">PrepareArbitraryState has been deprecated.</span></span> <span data-ttu-id="1b344-106"><xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP>Místo toho ho použijte.</span><span class="sxs-lookup"><span data-stu-id="1b344-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.</span></span>

<span data-ttu-id="1b344-107">Vzhledem k sadě koeficientů a registru s kódováním nenaloženého formátu Little endian připraví stav v tomto registru, který je popsán v daných koeficientech.</span><span class="sxs-lookup"><span data-stu-id="1b344-107">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.</span></span>

```qsharp
operation PrepareArbitraryState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="1b344-108">Popis</span><span class="sxs-lookup"><span data-stu-id="1b344-108">Description</span></span>

<span data-ttu-id="1b344-109">Tato operace připraví libovolný stav pro každý kraj $ \ket{\psi} $ pomocí složitých koeficientů $r _j e ^ {i t_j} $ ze stavu $n $-qubit výpočetního základu $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="1b344-109">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="1b344-110">Konkrétně je možné akci této operace simulovat pomocí jednotkové transformace $U $, která funguje se stavem vše – nula jako</span><span class="sxs-lookup"><span data-stu-id="1b344-110">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="1b344-111">$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="1b344-111">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="1b344-112">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="1b344-112">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="1b344-113">Vstup</span><span class="sxs-lookup"><span data-stu-id="1b344-113">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="1b344-114">koeficienty: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="1b344-114">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="1b344-115">Pole až do $2 ^ n $ složitých koeficientů reprezentovaných jejich absolutní hodnotou a fází $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="1b344-115">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="1b344-116">$J $ th součinitel indexuje číselný stav $ \ket{j} $ kódovaný ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="1b344-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="1b344-117">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1b344-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="1b344-118">Qubit registruje číselné kódování stavů ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="1b344-118">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="1b344-119">Očekává se, že se má inicializovat ve stavu výpočtu $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="1b344-119">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1b344-120">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1b344-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1b344-121">Poznámky</span><span class="sxs-lookup"><span data-stu-id="1b344-121">Remarks</span></span>

<span data-ttu-id="1b344-122">Negativní vstupní koeficienty $r _j < $0 budou považovány za kladné s hodnotou $ | r_j | $.</span><span class="sxs-lookup"><span data-stu-id="1b344-122">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="1b344-123">`coefficients` bude doplněna elementy $ (r_j, t_j) = (0,0, 0,0) $, pokud je zadáno méně než $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="1b344-123">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="1b344-124">Reference</span><span class="sxs-lookup"><span data-stu-id="1b344-124">References</span></span>

- <span data-ttu-id="1b344-125">Shrnutí logických okruhů Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="1b344-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="1b344-126">Viz také</span><span class="sxs-lookup"><span data-stu-id="1b344-126">See Also</span></span>

- [<span data-ttu-id="1b344-127">Microsoft. Přípravno. Preparation. ApproximatelyPrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="1b344-127">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)