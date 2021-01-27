---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE._prepareTrialStateWrapper
title: operace _prepareTrialStateWrapper
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: _prepareTrialStateWrapper
qsharp.summary: Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint. EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.
ms.openlocfilehash: f0deba39d834731fd9057a1d40d0c78b2b7e6bb8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850221"
---
# <a name="_preparetrialstatewrapper-operation"></a><span data-ttu-id="dda72-102">operace _prepareTrialStateWrapper</span><span class="sxs-lookup"><span data-stu-id="dda72-102">_prepareTrialStateWrapper operation</span></span>

<span data-ttu-id="dda72-103">Obor názvů: [Microsoft. JordanWigner. chemie.. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="dda72-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="dda72-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="dda72-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="dda72-105">Soukromá Obálka kolem PrepareTrialState tak, aby byla kompatibilní s EstimateFrequencyA, definováním sousedícího.</span><span class="sxs-lookup"><span data-stu-id="dda72-105">Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint.</span></span>
<span data-ttu-id="dda72-106">EstimateFrequencyA má vestavěnou funkci emulace, když cílí na QuantumSimulator, což zrychluje jeho spuštění.</span><span class="sxs-lookup"><span data-stu-id="dda72-106">EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.</span></span>

```qsharp
operation _prepareTrialStateWrapper (inputState : (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), qubits : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="dda72-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="dda72-107">Input</span></span>

### <a name="inputstate--intjordanwignerinputstate"></a><span data-ttu-id="dda72-108">inputState: ([int](xref:microsoft.quantum.lang-ref.int);[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])</span><span class="sxs-lookup"><span data-stu-id="dda72-108">inputState : ([Int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])</span></span>

<span data-ttu-id="dda72-109">Pro spuštění PrepareTrialState je vyžadován vstup Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="dda72-109">The Jordan-Wigner input required for PrepareTrialState to run.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="dda72-110">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dda72-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dda72-111">Qubit registr.</span><span class="sxs-lookup"><span data-stu-id="dda72-111">A qubit register.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dda72-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dda72-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

