---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: Operace AssertPhase
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830080"
---
# <a name="assertphase-operation"></a><span data-ttu-id="9d5ec-102">Operace AssertPhase</span><span class="sxs-lookup"><span data-stu-id="9d5ec-102">AssertPhase operation</span></span>

<span data-ttu-id="9d5ec-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9d5ec-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="9d5ec-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9d5ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9d5ec-105">Vyhodnotí, že fáze rovného stavu pozice má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="9d5ec-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="9d5ec-106">Popis</span><span class="sxs-lookup"><span data-stu-id="9d5ec-106">Description</span></span>

<span data-ttu-id="9d5ec-107">Tato operace vyhodnotí, že fáze $ \phi $ pro stav, který může být vyjádřen jako $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ KET {0} + e ^ {-i\phi} \ KET {1} ) $ pro některé reálné $t $ má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="9d5ec-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="9d5ec-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="9d5ec-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="9d5ec-109">očekáváno: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9d5ec-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9d5ec-110">Očekávaná hodnota $ \phi \in (-\pi, \pi] $.</span><span class="sxs-lookup"><span data-stu-id="9d5ec-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="9d5ec-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9d5ec-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9d5ec-112">Qubit, ve kterém je uložen očekávaný stav.</span><span class="sxs-lookup"><span data-stu-id="9d5ec-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="9d5ec-113">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9d5ec-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9d5ec-114">Absolutní tolerance rozdílu mezi skutečnými a očekávanými hodnotami.</span><span class="sxs-lookup"><span data-stu-id="9d5ec-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9d5ec-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9d5ec-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="9d5ec-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="9d5ec-116">Example</span></span>

<span data-ttu-id="9d5ec-117">Následující vyhodnocení je úspěšné: `qubit` je ve stavu $ \ket{\psi} = e ^ {i 0,5} \ sqrt {1/2} \ KET {0} + e ^ {i 0.5} \ sqrt {1/2} \ KET {1} $;</span><span class="sxs-lookup"><span data-stu-id="9d5ec-117">The following assert succeeds: `qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.0,qubit,10e-10);`

<span data-ttu-id="9d5ec-118">`qubit` je ve stavu $ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ KET {0} + e ^ {-i 0,5} \ sqrt {1/2} \ KET {1} $;</span><span class="sxs-lookup"><span data-stu-id="9d5ec-118">`qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{-i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.5,qubit,10e-10);`

<span data-ttu-id="9d5ec-119">`qubit` je ve stavu $ \ket{\psi} = e ^ {-i 2,2} \ sqrt {1/2} \ KET {0} + e ^ {i 0,2} \ sqrt {1/2} \ KET {1} $;</span><span class="sxs-lookup"><span data-stu-id="9d5ec-119">`qubit` is in state $\ket{\psi}=e^{-i 2.2}\sqrt{1/2}\ket{0}+e^{i 0.2}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(-1.2,qubit,10e-10);`