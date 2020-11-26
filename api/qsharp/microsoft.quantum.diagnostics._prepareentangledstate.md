---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: operace _prepareEntangledState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 97a55b4bb85095c7d8e8432dfcd1c6d6f7e93cdc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223931"
---
# <a name="_prepareentangledstate-operation"></a>operace _prepareEntangledState

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Vzhledem k dvěma registrům připraví maximální entangled stav mezi každou dvojici qubits na příslušných registrech.
Všechny qubits musí začínat ve stavu | 0 ⟩.

Výsledkem je, že odpovídající páry qubits z každého registru jsou v $ \bra{\ beta_ {00} } \ket{\ Beta_ {00} } $.

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="left--qubit"></a>Left: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Pole qubit ve stavu $ \ket{0\cdots 0} $


### <a name="right--qubit"></a>Right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Pole qubit ve stavu $ \ket{0\cdots 0} $



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

