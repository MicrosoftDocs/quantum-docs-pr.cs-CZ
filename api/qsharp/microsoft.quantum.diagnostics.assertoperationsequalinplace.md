---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: Operace AssertOperationsEqualInPlace
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 7c330ebdc156e60713a734d39a3600ee1326563c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853487"
---
# <a name="assertoperationsequalinplace-operation"></a>Operace AssertOperationsEqualInPlace

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Tyto dvě operace vyhodnotí, že jsou identické pro všechny vstupní stavy.

Tento kontrolní výraz je implementován pomocí kontroly akce operací ve všech stavech formuláře $V _0 \otimes... \otimes V_ {n-1} $, kde $V _k $ je jedna ze stavů $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ a $ \ket{i} $ (+ 1 Eigenstate of Pauli Y operator).

Tento kontrolní výraz používá $n $ qubits a vyžaduje více volání operací, které jsou porovnány.

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Vstup

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Počet qubits $n $, na kterých operace `givenU` fungují a `expectedU` pracují.


### <a name="givenu--qubit--unit"></a>předané: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Bude zkontrolována operace na $n $ qubits.


### <a name="expectedu--qubit--unit--is-adj"></a>očekává se: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Operace reference na $n $ qubits, která se má `givenU` Porovnat s.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Reference

Základem stavů $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ a $ \ket{i} $ je Chuang-Nielsen základ, který je popsaný v části [ *i. L. Čuangština, M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001).

## <a name="see-also"></a>Viz také

- [Microsoft. AssertOperationsEqualReferenced. Diagnostics.](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)