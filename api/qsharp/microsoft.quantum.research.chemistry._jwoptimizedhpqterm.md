---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedHpqTerm
title: Operace _JWOptimizedHpqTerm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedHpqTerm
qsharp.summary: Applies time-evolution by a PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: 06680bac0f0a2854c3ee3036c67c635ed0caf206
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225971"
---
# <a name="_jwoptimizedhpqterm-operation"></a><span data-ttu-id="f9139-102">Operace _JWOptimizedHpqTerm</span><span class="sxs-lookup"><span data-stu-id="f9139-102">_JWOptimizedHpqTerm operation</span></span>

<span data-ttu-id="f9139-103">Obor názvů: [Microsoft. Prohledávejte. Research. chemie](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f9139-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="f9139-104">Balíček: [Microsoft. prostudoval. Research. chemie](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f9139-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="f9139-105">Aplikuje čas na vývoj na základě výrazu PQ, který je popsaný v `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="f9139-105">Applies time-evolution by a PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedHpqTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f9139-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f9139-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="f9139-107">termín: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="f9139-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="f9139-108">`GeneratorIndex` představuje PQ termín.</span><span class="sxs-lookup"><span data-stu-id="f9139-108">`GeneratorIndex` representing a PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="f9139-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f9139-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f9139-110">Doba trvání vývoje času.</span><span class="sxs-lookup"><span data-stu-id="f9139-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="f9139-111">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f9139-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f9139-112">Qubit, která určuje znaménko času vývoje.</span><span class="sxs-lookup"><span data-stu-id="f9139-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="f9139-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f9139-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f9139-114">Qubits z Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="f9139-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f9139-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f9139-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

