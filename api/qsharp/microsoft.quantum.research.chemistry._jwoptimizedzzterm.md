---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZZTerm
title: Operace _JWOptimizedZZTerm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZZTerm
qsharp.summary: Applies time-evolution by a ZZ term described by a `GeneratorIndex`.
ms.openlocfilehash: 7fdda06b88ce03e0d76b7b589e50b460f0a5ff48
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225801"
---
# <a name="_jwoptimizedzzterm-operation"></a><span data-ttu-id="fcc96-102">Operace _JWOptimizedZZTerm</span><span class="sxs-lookup"><span data-stu-id="fcc96-102">_JWOptimizedZZTerm operation</span></span>

<span data-ttu-id="fcc96-103">Obor názvů: [Microsoft. Prohledávejte. Research. chemie](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="fcc96-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="fcc96-104">Balíček: [Microsoft. prostudoval. Research. chemie](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="fcc96-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="fcc96-105">Aplikuje čas na vývoj na základě výrazu ZZ, který je popsaný v `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="fcc96-105">Applies time-evolution by a ZZ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedZZTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fcc96-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="fcc96-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="fcc96-107">termín: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="fcc96-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="fcc96-108">`GeneratorIndex` představuje období ZZ.</span><span class="sxs-lookup"><span data-stu-id="fcc96-108">`GeneratorIndex` representing a ZZ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="fcc96-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fcc96-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fcc96-110">Doba trvání vývoje času.</span><span class="sxs-lookup"><span data-stu-id="fcc96-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="fcc96-111">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fcc96-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fcc96-112">Qubit, která určuje znaménko času vývoje.</span><span class="sxs-lookup"><span data-stu-id="fcc96-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="fcc96-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fcc96-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fcc96-114">Qubits z Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="fcc96-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fcc96-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fcc96-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

