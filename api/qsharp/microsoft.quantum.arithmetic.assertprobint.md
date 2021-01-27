---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: Operace AssertProbInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843407"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="1edee-102">Operace AssertProbInt</span><span class="sxs-lookup"><span data-stu-id="1edee-102">AssertProbInt operation</span></span>

<span data-ttu-id="1edee-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1edee-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1edee-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1edee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1edee-105">Vyhodnotí, že pravděpodobnost konkrétního stavu registru pro nepodmíněných hodnot má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="1edee-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="1edee-106">Popis</span><span class="sxs-lookup"><span data-stu-id="1edee-106">Description</span></span>

<span data-ttu-id="1edee-107">Je-li zadána hodnota $n $-qubit se stavem $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $, vyhodnotí, že pravděpodobnost $ | \ alpha_j | ^ 2 $ stavu $ \ket{j} $ indexovaného $j $ má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="1edee-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="1edee-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="1edee-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="1edee-109">stateIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1edee-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1edee-110">Index $j $ stavu $ \ket{j} $ reprezentovaný `LittleEndian` registrem.</span><span class="sxs-lookup"><span data-stu-id="1edee-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="1edee-111">očekáváno: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1edee-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1edee-112">Očekávaná hodnota $ | \ alpha_j | ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="1edee-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="1edee-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1edee-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="1edee-114">Registr qubit ukládá \ket{\psi} $ ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="1edee-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="1edee-115">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1edee-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1edee-116">Absolutní tolerance rozdílu mezi skutečnými a očekávanými hodnotami.</span><span class="sxs-lookup"><span data-stu-id="1edee-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1edee-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1edee-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="1edee-118">Příklad</span><span class="sxs-lookup"><span data-stu-id="1edee-118">Example</span></span>

<span data-ttu-id="1edee-119">Předpokládejme, že `qubits` registr zakóduje qubit stav 3 \ket{\psi} = \ sqrt {1/8} \ KET {0} + \ sqrt {7/8} \ KET {6} $ ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="1edee-119">Suppose that the `qubits` register encodes a 3-qubit quantum state $\ket{\psi}=\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{6}$ in little-endian format.</span></span>
<span data-ttu-id="1edee-120">To znamená, že počet stavů $ \ket {0} \equiv\ket {0} \ket {0} \ket {0} $ a $ \ket \equiv\ket \ket {6} {0} {1} \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="1edee-120">This means that the number states $\ket{0}\equiv\ket{0}\ket{0}\ket{0}$ and $\ket{6}\equiv\ket{0}\ket{1}\ket{1}$.</span></span> <span data-ttu-id="1edee-121">Následující kontrolní výrazy jsou úspěšné:</span><span class="sxs-lookup"><span data-stu-id="1edee-121">Then the following asserts succeed:</span></span>

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```