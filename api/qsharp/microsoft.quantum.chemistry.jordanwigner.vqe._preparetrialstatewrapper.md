---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE._prepareTrialStateWrapper
title: operace _prepareTrialStateWrapper
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: _prepareTrialStateWrapper
qsharp.summary: Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint. EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.
ms.openlocfilehash: 8e1a39cbd307a467ab7f0466c90722e1c8c46d4a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224679"
---
# <a name="_preparetrialstatewrapper-operation"></a>operace _prepareTrialStateWrapper

Obor názvů: [Microsoft. JordanWigner. chemie.. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Soukromá Obálka kolem PrepareTrialState tak, aby byla kompatibilní s EstimateFrequencyA, definováním sousedícího.
EstimateFrequencyA má vestavěnou funkci emulace, když cílí na QuantumSimulator, což zrychluje jeho spuštění.

```qsharp
operation _prepareTrialStateWrapper (inputState : (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), qubits : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Vstup

### <a name="inputstate--intjordanwignerinputstate"></a>inputState: ([int](xref:microsoft.quantum.lang-ref.int);[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])

Pro spuštění PrepareTrialState je vyžadován vstup Jordan-Wigner.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit registr.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

