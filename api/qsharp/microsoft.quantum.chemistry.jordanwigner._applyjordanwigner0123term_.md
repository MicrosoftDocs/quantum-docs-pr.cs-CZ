---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWigner0123Term_
title: Operace _ApplyJordanWigner0123Term_
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWigner0123Term_
qsharp.summary: Applies time-evolution by a PQRS term described by a `GeneratorIndex`.
ms.openlocfilehash: 31105f1adae3c17d409dde7b48a9aac6b87fca39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851746"
---
# <a name="_applyjordanwigner0123term_-operation"></a><span data-ttu-id="be1e3-102">Operace _ApplyJordanWigner0123Term_</span><span class="sxs-lookup"><span data-stu-id="be1e3-102">_ApplyJordanWigner0123Term_ operation</span></span>

<span data-ttu-id="be1e3-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="be1e3-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="be1e3-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="be1e3-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="be1e3-105">Aplikuje čas na vývoj na základě výrazu PQRS, který je popsaný v `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="be1e3-105">Applies time-evolution by a PQRS term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWigner0123Term_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="be1e3-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="be1e3-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="be1e3-107">termín: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="be1e3-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="be1e3-108">`GeneratorIndex` představuje PQRS termín.</span><span class="sxs-lookup"><span data-stu-id="be1e3-108">`GeneratorIndex` representing a PQRS term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="be1e3-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="be1e3-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="be1e3-110">Doba trvání vývoje času.</span><span class="sxs-lookup"><span data-stu-id="be1e3-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="be1e3-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="be1e3-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="be1e3-112">Qubits z Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="be1e3-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="be1e3-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="be1e3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

