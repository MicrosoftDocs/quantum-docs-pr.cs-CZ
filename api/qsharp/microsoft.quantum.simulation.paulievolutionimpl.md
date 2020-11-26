---
uid: Microsoft.Quantum.Simulation.PauliEvolutionImpl
title: Operace PauliEvolutionImpl
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.

  See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 868f3eef187e8e993127cfcab21e1574583ac845
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229133"
---
# <a name="paulievolutionimpl-operation"></a><span data-ttu-id="957a5-102">Operace PauliEvolutionImpl</span><span class="sxs-lookup"><span data-stu-id="957a5-102">PauliEvolutionImpl operation</span></span>

<span data-ttu-id="957a5-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="957a5-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="957a5-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="957a5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="957a5-105">Představuje dynamický generátor jako sadu simulovaných bran a rozšíření v Pauli.</span><span class="sxs-lookup"><span data-stu-id="957a5-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

<span data-ttu-id="957a5-106">Další podrobnosti najdete v tématu [dynamické modelování generátoru](/quantum/libraries/data-structures#dynamical-generator-modeling) .</span><span class="sxs-lookup"><span data-stu-id="957a5-106">See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation PauliEvolutionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, delta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="957a5-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="957a5-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="957a5-108">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="957a5-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="957a5-109">Index generátoru, který se reprezentuje jako jednotkový vývoj v Pauli.</span><span class="sxs-lookup"><span data-stu-id="957a5-109">A generator index to be represented as unitary evolution in the Pauli basis.</span></span>


### <a name="delta--double"></a><span data-ttu-id="957a5-110">Delta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="957a5-110">delta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="957a5-111">Násobitel v době trvání vývoje času podle termínu, na který se odkazuje `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="957a5-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="957a5-112">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="957a5-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="957a5-113">Zaregistrujte se na základě operátora času a vývoje.</span><span class="sxs-lookup"><span data-stu-id="957a5-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="957a5-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="957a5-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

