---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedFermionEvolution
title: Operace _JWOptimizedFermionEvolution
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedFermionEvolution
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 670accb6288d26cc7deb89c8d580fe082e795d57
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226005"
---
# <a name="_jwoptimizedfermionevolution-operation"></a><span data-ttu-id="86072-102">Operace _JWOptimizedFermionEvolution</span><span class="sxs-lookup"><span data-stu-id="86072-102">_JWOptimizedFermionEvolution operation</span></span>

<span data-ttu-id="86072-103">Obor názvů: [Microsoft. Prohledávejte. Research. chemie](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="86072-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="86072-104">Balíček: [Microsoft. prostudoval. Research. chemie](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="86072-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="86072-105">Představuje dynamický generátor jako sadu simulovaných bran a rozšíření v JWOptimized.</span><span class="sxs-lookup"><span data-stu-id="86072-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.</span></span>

<span data-ttu-id="86072-106">Další podrobnosti najdete v tématu [dynamické modelování generátoru](../libraries/data-structures#dynamical-generator-modeling) .</span><span class="sxs-lookup"><span data-stu-id="86072-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation _JWOptimizedFermionEvolution (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="86072-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="86072-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="86072-108">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="86072-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="86072-109">Index generátoru, který se reprezentuje jako jednotkový vývoj v JWOptimized.</span><span class="sxs-lookup"><span data-stu-id="86072-109">A generator index to be represented as unitary evolution in the JWOptimized basis.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="86072-110">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="86072-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="86072-111">Násobitel v době trvání vývoje času podle termínu, na který se odkazuje `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="86072-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="86072-112">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="86072-112">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="86072-113">Qubit, která určuje znaménko času vývoje.</span><span class="sxs-lookup"><span data-stu-id="86072-113">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="86072-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="86072-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="86072-115">Zaregistrujte se na základě operátora času a vývoje.</span><span class="sxs-lookup"><span data-stu-id="86072-115">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="86072-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="86072-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

