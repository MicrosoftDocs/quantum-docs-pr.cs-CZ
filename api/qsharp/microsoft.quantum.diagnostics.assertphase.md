---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: Operace AssertPhase
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 9130d6c735d90abbc51989ef4a68a8eff8b41371
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202256"
---
# <a name="assertphase-operation"></a><span data-ttu-id="c1c13-102">Operace AssertPhase</span><span class="sxs-lookup"><span data-stu-id="c1c13-102">AssertPhase operation</span></span>

<span data-ttu-id="c1c13-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c1c13-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c1c13-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c1c13-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c1c13-105">Vyhodnotí, že fáze rovného stavu pozice má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="c1c13-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="c1c13-106">Popis</span><span class="sxs-lookup"><span data-stu-id="c1c13-106">Description</span></span>

<span data-ttu-id="c1c13-107">Tato operace vyhodnotí, že fáze $ \phi $ pro stav, který může být vyjádřen jako $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ KET {0} + e ^ {-i\phi} \ KET {1} ) $ pro některé reálné $t $ má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="c1c13-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="c1c13-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="c1c13-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="c1c13-109">očekáváno: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c1c13-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c1c13-110">Očekávaná hodnota $ \phi \in (-\pi, \pi] $.</span><span class="sxs-lookup"><span data-stu-id="c1c13-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="c1c13-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c1c13-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c1c13-112">Qubit, ve kterém je uložen očekávaný stav.</span><span class="sxs-lookup"><span data-stu-id="c1c13-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="c1c13-113">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c1c13-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c1c13-114">Absolutní tolerance rozdílu mezi skutečnými a očekávanými hodnotami.</span><span class="sxs-lookup"><span data-stu-id="c1c13-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c1c13-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c1c13-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

