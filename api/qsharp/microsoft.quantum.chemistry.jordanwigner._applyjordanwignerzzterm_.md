---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerZZTerm_
title: Operace _ApplyJordanWignerZZTerm_
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerZZTerm_
qsharp.summary: Applies time-evolution by a ZZ term described by a `GeneratorIndex`.
ms.openlocfilehash: 9f03255d53f7ed7f3e79689ea53c8b95133f6cde
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698652"
---
# <a name="_applyjordanwignerzzterm_-operation"></a><span data-ttu-id="89809-102">Operace _ApplyJordanWignerZZTerm_</span><span class="sxs-lookup"><span data-stu-id="89809-102">_ApplyJordanWignerZZTerm_ operation</span></span>

<span data-ttu-id="89809-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="89809-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="89809-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="89809-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="89809-105">Aplikuje čas na vývoj na základě výrazu ZZ, který je popsaný v `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="89809-105">Applies time-evolution by a ZZ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerZZTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="89809-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="89809-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="89809-107">termín: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="89809-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="89809-108">`GeneratorIndex` představuje období ZZ.</span><span class="sxs-lookup"><span data-stu-id="89809-108">`GeneratorIndex` representing a ZZ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="89809-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="89809-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="89809-110">Doba trvání vývoje času.</span><span class="sxs-lookup"><span data-stu-id="89809-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="89809-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="89809-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="89809-112">Qubits z Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="89809-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="89809-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="89809-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

