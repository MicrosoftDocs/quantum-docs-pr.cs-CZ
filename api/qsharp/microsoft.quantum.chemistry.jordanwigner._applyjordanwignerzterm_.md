---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerZTerm_
title: Operace _ApplyJordanWignerZTerm_
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerZTerm_
qsharp.summary: Applies time-evolution by a Z term described by a `GeneratorIndex`.
ms.openlocfilehash: ad9245b0fd79b4f383d1ef8531537b03d78ae9b8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203990"
---
# <a name="_applyjordanwignerzterm_-operation"></a><span data-ttu-id="fe4a8-102">Operace _ApplyJordanWignerZTerm_</span><span class="sxs-lookup"><span data-stu-id="fe4a8-102">_ApplyJordanWignerZTerm_ operation</span></span>

<span data-ttu-id="fe4a8-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="fe4a8-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="fe4a8-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="fe4a8-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="fe4a8-105">Aplikuje čas na vývoj na základě termínu Z popsanýho v `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="fe4a8-105">Applies time-evolution by a Z term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerZTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fe4a8-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="fe4a8-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="fe4a8-107">termín: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="fe4a8-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="fe4a8-108">`GeneratorIndex` představuje termín Z.</span><span class="sxs-lookup"><span data-stu-id="fe4a8-108">`GeneratorIndex` representing a Z term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="fe4a8-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fe4a8-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fe4a8-110">Doba trvání vývoje času.</span><span class="sxs-lookup"><span data-stu-id="fe4a8-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="fe4a8-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fe4a8-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fe4a8-112">Qubits z Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="fe4a8-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fe4a8-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fe4a8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

