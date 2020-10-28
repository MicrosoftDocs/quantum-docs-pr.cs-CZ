---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 39d961c71d231e7b51290f81c20c8c6b48c7e0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708176"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="efb71-102">StatePreparationPositiveCoefficients – funkce</span><span class="sxs-lookup"><span data-stu-id="efb71-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="efb71-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="efb71-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="efb71-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="efb71-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="efb71-105">Vrátí operaci, která připraví daný stav.</span><span class="sxs-lookup"><span data-stu-id="efb71-105">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="efb71-106">Vrácená operace $U $ připraví libovolný stav pro každý kraj $ \ket{\psi} $ s pozitivním koeficientem $ \ alpha_j \ge $0 ze stavu $n $-qubit výpočetního základu $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="efb71-106">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="efb71-107">Akce U nově přiděleného registru je dána $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="efb71-107">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="efb71-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="efb71-108">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="efb71-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="efb71-109">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="efb71-110">koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="efb71-110">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="efb71-111">Pole až do $2 ^ n $ koeficienty $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="efb71-111">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="efb71-112">$J $ th součinitel indexuje číselný stav $ \ket{j} $ kódovaný ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="efb71-112">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit-adj--ctl"></a><span data-ttu-id="efb71-113">Výstup: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="efb71-113">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="efb71-114">Jednotná provozní operace pro přípravu stavu $U $.</span><span class="sxs-lookup"><span data-stu-id="efb71-114">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="efb71-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="efb71-115">Remarks</span></span>

<span data-ttu-id="efb71-116">Negativní vstupní koeficienty $ \ alpha_j < $0 budou považovány za kladné s hodnotou $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="efb71-116">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="efb71-117">`coefficients` budou doplněny elementy $ \ alpha_j = $0,0, pokud je zadána méně než $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="efb71-117">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>