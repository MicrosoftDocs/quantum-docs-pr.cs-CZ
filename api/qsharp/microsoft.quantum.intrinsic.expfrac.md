---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: Operace ExpFrac
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: d11912a272387b087098f59e7ac071534b01c054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697728"
---
# <a name="expfrac-operation"></a>Operace ExpFrac

Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)

Balíček [](https://nuget.org/packages/)


Aplikuje exponenciální operátor qubit Pauli s argumentem daným zlomkem dyadic.

\begin{align} e ^ {i \pi k [P_0 \otimes P_1 \cdots P_ {N-1}]/2 ^ N}, \end{align} kde $P _i $ je prvek $i $ th `paulis` a kde $N = $ `Length(paulis)` .

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="paulis--pauli"></a>Pauls: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Pole hodnot qubit Pauli, které označují faktory tensor produktů na každé qubit.


### <a name="numerator--int"></a>Čitatel: [int](xref:microsoft.quantum.lang-ref.int)

Čitatel ($k $) ve zlomku dyadic zlomku úhlu, podle kterého se má otočit registr qubit.


### <a name="power--int"></a>napájení: [int](xref:microsoft.quantum.lang-ref.int)

Mocnina dvou ($n $) určující jmenovatele úhlu, podle kterého se má otočit registr qubit.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Zaregistrujte se na použití daného otočení na.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

