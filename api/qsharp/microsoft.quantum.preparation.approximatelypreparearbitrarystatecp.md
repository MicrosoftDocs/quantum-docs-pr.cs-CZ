---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP
title: Operace ApproximatelyPrepareArbitraryStateCP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryStateCP
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 44352a4d6325c128539351695fb14d3706ce842f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226532"
---
# <a name="approximatelypreparearbitrarystatecp-operation"></a><span data-ttu-id="45bae-102">Operace ApproximatelyPrepareArbitraryStateCP</span><span class="sxs-lookup"><span data-stu-id="45bae-102">ApproximatelyPrepareArbitraryStateCP operation</span></span>

<span data-ttu-id="45bae-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="45bae-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="45bae-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="45bae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="45bae-105">Vzhledem k sadě koeficientů a registru s kódováním ve formátu Little endian se připraví stav v tomto registru, který je popsán danými koeficienty, až do dané tolerance odhadu.</span><span class="sxs-lookup"><span data-stu-id="45bae-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.</span></span>

```qsharp
operation ApproximatelyPrepareArbitraryStateCP (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="45bae-106">Popis</span><span class="sxs-lookup"><span data-stu-id="45bae-106">Description</span></span>

<span data-ttu-id="45bae-107">Tato operace připraví libovolný stav pro každý kraj $ \ket{\psi} $ pomocí složitých koeficientů $r _j e ^ {i t_j} $ ze stavu $n $-qubit výpočetního základu $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="45bae-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="45bae-108">Konkrétně je možné akci této operace simulovat pomocí jednotkové transformace $U $, která funguje se stavem vše – nula jako</span><span class="sxs-lookup"><span data-stu-id="45bae-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="45bae-109">$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="45bae-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="45bae-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="45bae-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="45bae-111">Vstup</span><span class="sxs-lookup"><span data-stu-id="45bae-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="45bae-112">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="45bae-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="45bae-113">Tolerance aproximace, která se má použít při přípravě daného stavu.</span><span class="sxs-lookup"><span data-stu-id="45bae-113">The approximation tolerance to be used when preparing the given state.</span></span>


### <a name="coefficients--complexpolar"></a><span data-ttu-id="45bae-114">koeficienty: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="45bae-114">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="45bae-115">Pole až do $2 ^ n $ složitých koeficientů reprezentovaných jejich absolutní hodnotou a fází $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="45bae-115">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="45bae-116">$J $ th součinitel indexuje číselný stav $ \ket{j} $ kódovaný ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="45bae-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="45bae-117">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="45bae-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="45bae-118">Qubit registruje číselné kódování stavů ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="45bae-118">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="45bae-119">Očekává se, že se má inicializovat ve stavu výpočtu $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="45bae-119">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="45bae-120">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="45bae-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="45bae-121">Poznámky</span><span class="sxs-lookup"><span data-stu-id="45bae-121">Remarks</span></span>

<span data-ttu-id="45bae-122">Negativní vstupní koeficienty $r _j < $0 budou považovány za kladné s hodnotou $ | r_j | $.</span><span class="sxs-lookup"><span data-stu-id="45bae-122">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="45bae-123">`coefficients` bude doplněna elementy $ (r_j, t_j) = (0,0, 0,0) $, pokud je zadáno méně než $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="45bae-123">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="45bae-124">Reference</span><span class="sxs-lookup"><span data-stu-id="45bae-124">References</span></span>

- <span data-ttu-id="45bae-125">Shrnutí logických okruhů Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="45bae-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>