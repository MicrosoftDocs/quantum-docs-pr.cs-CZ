---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerClusterOperatorPQRSTerm
title: Operace _ApplyJordanWignerClusterOperatorPQRSTerm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerClusterOperatorPQRSTerm
qsharp.summary: Applies time-evolution by a cluster operator PQRS term described by a `GeneratorIndex`.
ms.openlocfilehash: f5f77c102596c26100c85eaac42f5f88848e4550
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839576"
---
# <a name="_applyjordanwignerclusteroperatorpqrsterm-operation"></a><span data-ttu-id="047e5-102">Operace _ApplyJordanWignerClusterOperatorPQRSTerm</span><span class="sxs-lookup"><span data-stu-id="047e5-102">_ApplyJordanWignerClusterOperatorPQRSTerm operation</span></span>

<span data-ttu-id="047e5-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="047e5-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="047e5-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="047e5-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="047e5-105">Aplikuje čas do vývoje pomocí operátoru PQRS, který je popsaný v tématu `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="047e5-105">Applies time-evolution by a cluster operator PQRS term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerClusterOperatorPQRSTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="047e5-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="047e5-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="047e5-107">termín: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="047e5-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="047e5-108">`GeneratorIndex` představuje PQRS termín operátora clusteru.</span><span class="sxs-lookup"><span data-stu-id="047e5-108">`GeneratorIndex` representing a cluster operator PQRS term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="047e5-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="047e5-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="047e5-110">Doba trvání vývoje času.</span><span class="sxs-lookup"><span data-stu-id="047e5-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="047e5-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="047e5-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="047e5-112">Qubits z Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="047e5-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="047e5-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="047e5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

