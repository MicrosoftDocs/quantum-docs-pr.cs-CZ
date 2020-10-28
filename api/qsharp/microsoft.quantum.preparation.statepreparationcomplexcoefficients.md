---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: StatePreparationComplexCoefficients – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: 02e3d2fcf21b5bb4ed1bf7aa931597f918a1d369
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708182"
---
# <a name="statepreparationcomplexcoefficients-function"></a><span data-ttu-id="607fd-102">StatePreparationComplexCoefficients – funkce</span><span class="sxs-lookup"><span data-stu-id="607fd-102">StatePreparationComplexCoefficients function</span></span>

<span data-ttu-id="607fd-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="607fd-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="607fd-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="607fd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="607fd-105">Vrátí operaci, která připraví určitý stav nečinnosti.</span><span class="sxs-lookup"><span data-stu-id="607fd-105">Returns an operation that prepares a specific quantum state.</span></span>

<span data-ttu-id="607fd-106">Vrácená operace $U $ připraví libovolný stav za běhu $ \ket{\psi} $ pomocí složitých koeficientů $r _j e ^ {i t_j} $ ze stavu výpočtu $n $-qubit výpočetního základu $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="607fd-106">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="607fd-107">Akce U nově přiděleného registru je dána $ $ \begin{align} U\ket {0... 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="607fd-107">The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}.</span></span>
<span data-ttu-id="607fd-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="607fd-108">\end{align} $$</span></span>

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="607fd-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="607fd-109">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="607fd-110">koeficienty: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="607fd-110">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="607fd-111">Pole až do $2 ^ n $ složitých koeficientů reprezentovaných jejich absolutní hodnotou a fází $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="607fd-111">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="607fd-112">$J $ th součinitel indexuje číselný stav $ \ket{j} $ kódovaný ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="607fd-112">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit-adj--ctl"></a><span data-ttu-id="607fd-113">Výstup: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="607fd-113">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="607fd-114">Jednotná provozní operace pro přípravu stavu $U $.</span><span class="sxs-lookup"><span data-stu-id="607fd-114">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="607fd-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="607fd-115">Remarks</span></span>

<span data-ttu-id="607fd-116">Negativní vstupní koeficienty $r _j < $0 budou považovány za kladné s hodnotou $ | r_j | $.</span><span class="sxs-lookup"><span data-stu-id="607fd-116">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="607fd-117">`coefficients` bude doplněna elementy $ (r_j, t_j) = (0,0, 0,0) $, pokud je zadáno méně než $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="607fd-117">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>