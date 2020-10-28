---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerZTerm_
title: Operace _ApplyJordanWignerZTerm_
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerZTerm_
qsharp.summary: Applies time-evolution by a Z term described by a `GeneratorIndex`.
ms.openlocfilehash: f42c2ba7570f32d3f26ff82dd4a0ee6f9677fa30
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698653"
---
# <a name="_applyjordanwignerzterm_-operation"></a><span data-ttu-id="3f5cb-102">Operace _ApplyJordanWignerZTerm_</span><span class="sxs-lookup"><span data-stu-id="3f5cb-102">_ApplyJordanWignerZTerm_ operation</span></span>

<span data-ttu-id="3f5cb-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="3f5cb-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="3f5cb-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3f5cb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3f5cb-105">Aplikuje čas na vývoj na základě termínu Z popsanýho v `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="3f5cb-105">Applies time-evolution by a Z term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerZTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3f5cb-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="3f5cb-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="3f5cb-107">termín: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="3f5cb-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="3f5cb-108">`GeneratorIndex` představuje termín Z.</span><span class="sxs-lookup"><span data-stu-id="3f5cb-108">`GeneratorIndex` representing a Z term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="3f5cb-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3f5cb-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3f5cb-110">Doba trvání vývoje času.</span><span class="sxs-lookup"><span data-stu-id="3f5cb-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="3f5cb-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3f5cb-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3f5cb-112">Qubits z Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="3f5cb-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3f5cb-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f5cb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

