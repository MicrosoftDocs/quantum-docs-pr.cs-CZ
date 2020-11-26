---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: Operace AssertProbInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: b95c2c6294dd5a95b7215c22bd6c50a41635f432
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223693"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="0678b-102">Operace AssertProbInt</span><span class="sxs-lookup"><span data-stu-id="0678b-102">AssertProbInt operation</span></span>

<span data-ttu-id="0678b-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0678b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0678b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0678b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0678b-105">Vyhodnotí, že pravděpodobnost konkrétního stavu registru pro nepodmíněných hodnot má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="0678b-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="0678b-106">Popis</span><span class="sxs-lookup"><span data-stu-id="0678b-106">Description</span></span>

<span data-ttu-id="0678b-107">Je-li zadána hodnota $n $-qubit se stavem $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $, vyhodnotí, že pravděpodobnost $ | \ alpha_j | ^ 2 $ stavu $ \ket{j} $ indexovaného $j $ má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="0678b-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="0678b-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="0678b-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="0678b-109">stateIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0678b-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0678b-110">Index $j $ stavu $ \ket{j} $ reprezentovaný `LittleEndian` registrem.</span><span class="sxs-lookup"><span data-stu-id="0678b-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="0678b-111">očekáváno: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0678b-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0678b-112">Očekávaná hodnota $ | \ alpha_j | ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="0678b-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="0678b-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0678b-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0678b-114">Registr qubit ukládá \ket{\psi} $ ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="0678b-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="0678b-115">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0678b-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0678b-116">Absolutní tolerance rozdílu mezi skutečnými a očekávanými hodnotami.</span><span class="sxs-lookup"><span data-stu-id="0678b-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0678b-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0678b-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

