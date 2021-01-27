---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerZZTerm_
title: Operace _ApplyJordanWignerZZTerm_
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerZZTerm_
qsharp.summary: Applies time-evolution by a ZZ term described by a `GeneratorIndex`.
ms.openlocfilehash: 4ecf6279595d12d4262aa6786d908270707b95bc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851685"
---
# <a name="_applyjordanwignerzzterm_-operation"></a><span data-ttu-id="a97fa-102">Operace _ApplyJordanWignerZZTerm_</span><span class="sxs-lookup"><span data-stu-id="a97fa-102">_ApplyJordanWignerZZTerm_ operation</span></span>

<span data-ttu-id="a97fa-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="a97fa-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="a97fa-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="a97fa-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="a97fa-105">Aplikuje čas na vývoj na základě výrazu ZZ, který je popsaný v `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="a97fa-105">Applies time-evolution by a ZZ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerZZTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a97fa-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="a97fa-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="a97fa-107">termín: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="a97fa-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="a97fa-108">`GeneratorIndex` představuje období ZZ.</span><span class="sxs-lookup"><span data-stu-id="a97fa-108">`GeneratorIndex` representing a ZZ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="a97fa-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a97fa-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a97fa-110">Doba trvání vývoje času.</span><span class="sxs-lookup"><span data-stu-id="a97fa-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="a97fa-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a97fa-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a97fa-112">Qubits z Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="a97fa-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a97fa-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a97fa-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

