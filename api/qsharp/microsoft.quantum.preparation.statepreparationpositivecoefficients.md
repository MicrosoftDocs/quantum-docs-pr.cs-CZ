---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients – funkce
ms.date: 1/23/2021 12:00:00 AM
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
ms.openlocfilehash: 081541d93bf853fa0de1573038dc00c296432281
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855847"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="ed797-102">StatePreparationPositiveCoefficients – funkce</span><span class="sxs-lookup"><span data-stu-id="ed797-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="ed797-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="ed797-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="ed797-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ed797-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="ed797-105">StatePreparationPositiveCoefficients se už nepoužívá.</span><span class="sxs-lookup"><span data-stu-id="ed797-105">StatePreparationPositiveCoefficients has been deprecated.</span></span> <span data-ttu-id="ed797-106"><xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD>Místo toho ho použijte.</span><span class="sxs-lookup"><span data-stu-id="ed797-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.</span></span>

<span data-ttu-id="ed797-107">Vrátí operaci, která připraví daný stav.</span><span class="sxs-lookup"><span data-stu-id="ed797-107">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="ed797-108">Vrácená operace $U $ připraví libovolný stav pro každý kraj $ \ket{\psi} $ s pozitivním koeficientem $ \ alpha_j \ge $0 ze stavu $n $-qubit výpočetního základu $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="ed797-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="ed797-109">Akce U nově přiděleného registru je dána $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="ed797-109">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="ed797-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="ed797-110">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="ed797-111">Vstup</span><span class="sxs-lookup"><span data-stu-id="ed797-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="ed797-112">koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ed797-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ed797-113">Pole až do $2 ^ n $ koeficienty $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="ed797-113">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="ed797-114">$J $ th součinitel indexuje číselný stav $ \ket{j} $ kódovaný ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="ed797-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="ed797-115">Výstup: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) LittleEndian je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="ed797-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ed797-116">Jednotná provozní operace pro přípravu stavu $U $.</span><span class="sxs-lookup"><span data-stu-id="ed797-116">A state-preparation unitary operation $U$.</span></span>

## <a name="example"></a><span data-ttu-id="ed797-117">Příklad</span><span class="sxs-lookup"><span data-stu-id="ed797-117">Example</span></span>

<span data-ttu-id="ed797-118">Následující fragment kódu připraví stav pro stav, který je v registru qubit připraven na \ket{\psi} = \ sqrt {1/8} \ KET {0} + \ sqrt {7/8} \ KET {2} $ `qubitsLE` .</span><span class="sxs-lookup"><span data-stu-id="ed797-118">The following snippet prepares the quantum state $\ket{\psi}=\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{2}$ in the qubit register `qubitsLE`.</span></span>

```qsharp
let amplitudes = [Sqrt(0.125), 0.0, Sqrt(0.875), 0.0];
let op = StatePreparationPositiveCoefficients(amplitudes);
using (qubits = Qubit[2]) {
    let qubitsLE = LittleEndian(qubits);
    op(qubitsLE);
}
```

## <a name="remarks"></a><span data-ttu-id="ed797-119">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ed797-119">Remarks</span></span>

<span data-ttu-id="ed797-120">Negativní vstupní koeficienty $ \ alpha_j < $0 budou považovány za kladné s hodnotou $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="ed797-120">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="ed797-121">`coefficients` budou doplněny elementy $ \ alpha_j = $0,0, pokud je zadána méně než $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="ed797-121">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>