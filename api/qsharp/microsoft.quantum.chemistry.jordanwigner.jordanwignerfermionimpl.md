---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionImpl
title: Operace JordanWignerFermionImpl
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: e0e0afe0f0998acb9791ceb25975fe8005771ed0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224934"
---
# <a name="jordanwignerfermionimpl-operation"></a><span data-ttu-id="2950f-102">Operace JordanWignerFermionImpl</span><span class="sxs-lookup"><span data-stu-id="2950f-102">JordanWignerFermionImpl operation</span></span>

<span data-ttu-id="2950f-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="2950f-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="2950f-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="2950f-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="2950f-105">Představuje dynamický generátor jako sadu simulovaných bran a rozšíření v JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="2950f-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

<span data-ttu-id="2950f-106">Další podrobnosti najdete v tématu [dynamické modelování generátoru](../libraries/data-structures#dynamical-generator-modeling) .</span><span class="sxs-lookup"><span data-stu-id="2950f-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation JordanWignerFermionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2950f-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="2950f-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="2950f-108">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="2950f-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="2950f-109">Index generátoru, který se má znázornit jako jednotkový vývoj v JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="2950f-109">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="2950f-110">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2950f-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2950f-111">Násobitel v době trvání vývoje času podle termínu, na který se odkazuje `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="2950f-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="2950f-112">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2950f-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2950f-113">Zaregistrujte se na základě operátora času a vývoje.</span><span class="sxs-lookup"><span data-stu-id="2950f-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2950f-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2950f-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

