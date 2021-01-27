---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: StatePreparationComplexCoefficients – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationComplexCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: c16df0fe075b15cff745a6b7d5b79aac39c14d09
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856141"
---
# <a name="statepreparationcomplexcoefficients-function"></a><span data-ttu-id="1b24b-102">StatePreparationComplexCoefficients – funkce</span><span class="sxs-lookup"><span data-stu-id="1b24b-102">StatePreparationComplexCoefficients function</span></span>

<span data-ttu-id="1b24b-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="1b24b-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="1b24b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1b24b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="1b24b-105">StatePreparationComplexCoefficients se už nepoužívá.</span><span class="sxs-lookup"><span data-stu-id="1b24b-105">StatePreparationComplexCoefficients has been deprecated.</span></span> <span data-ttu-id="1b24b-106"><xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP>Místo toho ho použijte.</span><span class="sxs-lookup"><span data-stu-id="1b24b-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.</span></span>

<span data-ttu-id="1b24b-107">Vrátí operaci, která připraví určitý stav nečinnosti.</span><span class="sxs-lookup"><span data-stu-id="1b24b-107">Returns an operation that prepares a specific quantum state.</span></span>

<span data-ttu-id="1b24b-108">Vrácená operace $U $ připraví libovolný stav za běhu $ \ket{\psi} $ pomocí složitých koeficientů $r _j e ^ {i t_j} $ ze stavu výpočtu $n $-qubit výpočetního základu $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="1b24b-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="1b24b-109">Akce U nově přiděleného registru je dána $ $ \begin{align} U\ket {0... 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="1b24b-109">The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}.</span></span>
<span data-ttu-id="1b24b-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="1b24b-110">\end{align} $$</span></span>

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="1b24b-111">Vstup</span><span class="sxs-lookup"><span data-stu-id="1b24b-111">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="1b24b-112">koeficienty: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="1b24b-112">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="1b24b-113">Pole až do $2 ^ n $ složitých koeficientů reprezentovaných jejich absolutní hodnotou a fází $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="1b24b-113">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="1b24b-114">$J $ th součinitel indexuje číselný stav $ \ket{j} $ kódovaný ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="1b24b-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="1b24b-115">Výstup: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) LittleEndian je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="1b24b-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="1b24b-116">Jednotná provozní operace pro přípravu stavu $U $.</span><span class="sxs-lookup"><span data-stu-id="1b24b-116">A state-preparation unitary operation $U$.</span></span>

## <a name="example"></a><span data-ttu-id="1b24b-117">Příklad</span><span class="sxs-lookup"><span data-stu-id="1b24b-117">Example</span></span>

<span data-ttu-id="1b24b-118">Následující fragment kódu připraví stav po zemi $ \ket{\psi} = e ^ {i 0,1} \ sqrt {1/8} \ KET {0} + \ sqrt {7/8} \ KET {2} $ v registru qubit `qubitsLE` .</span><span class="sxs-lookup"><span data-stu-id="1b24b-118">The following snippet prepares the quantum state $\ket{\psi}=e^{i 0.1}\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{2}$ in the qubit register `qubitsLE`.</span></span>

```qsharp
let amplitudes = [Sqrt(0.125), 0.0, Sqrt(0.875), 0.0];
let phases = [0.1, 0.0, 0.0, 0.0];
mutable complexNumbers = new ComplexPolar[4];
for (idx in 0..3) {
    set complexNumbers[idx] = ComplexPolar(amplitudes[idx], phases[idx]);
}
let op = StatePreparationComplexCoefficients(complexNumbers);
using (qubits = Qubit[2]) {
    let qubitsLE = LittleEndian(qubits);
    op(qubitsLE);
}
```

## <a name="remarks"></a><span data-ttu-id="1b24b-119">Poznámky</span><span class="sxs-lookup"><span data-stu-id="1b24b-119">Remarks</span></span>

<span data-ttu-id="1b24b-120">Negativní vstupní koeficienty $r _j < $0 budou považovány za kladné s hodnotou $ | r_j | $.</span><span class="sxs-lookup"><span data-stu-id="1b24b-120">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="1b24b-121">`coefficients` bude doplněna elementy $ (r_j, t_j) = (0,0, 0,0) $, pokud je zadáno méně než $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="1b24b-121">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>