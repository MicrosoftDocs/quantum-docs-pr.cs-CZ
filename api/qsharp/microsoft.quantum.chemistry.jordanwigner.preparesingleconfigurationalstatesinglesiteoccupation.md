---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSingleConfigurationalStateSingleSiteOccupation
title: Operace PrepareSingleConfigurationalStateSingleSiteOccupation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSingleConfigurationalStateSingleSiteOccupation
qsharp.summary: Simple state preparation of trial state by occupying spin-orbitals
ms.openlocfilehash: 360800037318f56d0bb659aeb2a2c6292f860b2c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214547"
---
# <a name="preparesingleconfigurationalstatesinglesiteoccupation-operation"></a>Operace PrepareSingleConfigurationalStateSingleSiteOccupation

Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Jednoduchá příprava stavu zkušební verze pomocí číselníku orbitals

```qsharp
operation PrepareSingleConfigurationalStateSingleSiteOccupation (qubitIndices : Int[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="qubitindices--int"></a>qubitIndices: [int](xref:microsoft.quantum.lang-ref.int)[]

Indexy qubits, které mají být obsazeny Electrons.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits z Hamiltonian.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

