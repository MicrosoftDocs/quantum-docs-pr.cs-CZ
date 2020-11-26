---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationPositiveCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.


  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 8f1fd7d77531996faf566adb78f452929d6cbd50
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193246"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="abced-102">StatePreparationPositiveCoefficients – funkce</span><span class="sxs-lookup"><span data-stu-id="abced-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="abced-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="abced-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="abced-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="abced-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="abced-105">StatePreparationPositiveCoefficients se už nepoužívá.</span><span class="sxs-lookup"><span data-stu-id="abced-105">StatePreparationPositiveCoefficients has been deprecated.</span></span> <span data-ttu-id="abced-106"><xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD>Místo toho ho použijte.</span><span class="sxs-lookup"><span data-stu-id="abced-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.</span></span>

<span data-ttu-id="abced-107">Vrátí operaci, která připraví daný stav.</span><span class="sxs-lookup"><span data-stu-id="abced-107">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="abced-108">Vrácená operace $U $ připraví libovolný stav pro každý kraj $ \ket{\psi} $ s pozitivním koeficientem $ \ alpha_j \ge $0 ze stavu $n $-qubit výpočetního základu $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="abced-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="abced-109">Akce U nově přiděleného registru je dána $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="abced-109">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="abced-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="abced-110">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="abced-111">Vstup</span><span class="sxs-lookup"><span data-stu-id="abced-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="abced-112">koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="abced-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="abced-113">Pole až do $2 ^ n $ koeficienty $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="abced-113">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="abced-114">$J $ th součinitel indexuje číselný stav $ \ket{j} $ kódovaný ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="abced-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="abced-115">Výstup: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) LittleEndian je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="abced-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="abced-116">Jednotná provozní operace pro přípravu stavu $U $.</span><span class="sxs-lookup"><span data-stu-id="abced-116">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="abced-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="abced-117">Remarks</span></span>

<span data-ttu-id="abced-118">Negativní vstupní koeficienty $ \ alpha_j < $0 budou považovány za kladné s hodnotou $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="abced-118">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="abced-119">`coefficients` budou doplněny elementy $ \ alpha_j = $0,0, pokud je zadána méně než $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="abced-119">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>