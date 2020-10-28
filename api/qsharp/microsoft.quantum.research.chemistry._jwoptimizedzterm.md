---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZTerm
title: Operace _JWOptimizedZTerm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZTerm
qsharp.summary: Applies time-evolution by a Z term described by a `GeneratorIndex`.
ms.openlocfilehash: 0b54bd7916ff8294501716365c11211b4654f5ad
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708133"
---
# <a name="_jwoptimizedzterm-operation"></a><span data-ttu-id="ea849-102">Operace _JWOptimizedZTerm</span><span class="sxs-lookup"><span data-stu-id="ea849-102">_JWOptimizedZTerm operation</span></span>

<span data-ttu-id="ea849-103">Obor názvů: [Microsoft. Prohledávejte. Research. chemie](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="ea849-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="ea849-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ea849-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ea849-105">Aplikuje čas na vývoj na základě termínu Z popsanýho v `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="ea849-105">Applies time-evolution by a Z term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedZTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ea849-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ea849-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="ea849-107">termín: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="ea849-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="ea849-108">`GeneratorIndex` představuje termín Z.</span><span class="sxs-lookup"><span data-stu-id="ea849-108">`GeneratorIndex` representing a Z term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="ea849-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ea849-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ea849-110">Doba trvání vývoje času.</span><span class="sxs-lookup"><span data-stu-id="ea849-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="ea849-111">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ea849-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ea849-112">Qubit, která určuje znaménko času vývoje.</span><span class="sxs-lookup"><span data-stu-id="ea849-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="ea849-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ea849-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ea849-114">Qubits z Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="ea849-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ea849-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ea849-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

