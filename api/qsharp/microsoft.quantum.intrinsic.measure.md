---
uid: Microsoft.Quantum.Intrinsic.Measure
title: Operace měření
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: 56ddfbe5e63692e477ad75bde6b1b16269ed20c0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697717"
---
# <a name="measure-operation"></a>Operace měření

Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)

Balíček [](https://nuget.org/packages/)


Provede společné měření jednoho nebo více qubits v zadaných základech Pauli.

Výsledek výstupu je dán distribucí: \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \frac12 \braket{\psi \mid | \left (\boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_ {N-1} \right) \mid | \psi}, \end{align} kde $P _i $ je $i $ th prvek `bases` a kde $N = \texttt{Length} (\texttt{Bases}) $.
To znamená, že měření vrátí `Result` $d $ tak, že eigenvalue účinek pozorovaného měření je $ (-1) ^ d $.

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a>Vstup

### <a name="bases--pauli"></a>základ: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Pole hodnot qubit Pauli, které označují faktory tensor produktů na každé qubit.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registrace qubits, která se má měřit



## <a name="output--__invalidresult__"></a>Výstup: __neplatný <Result>__

`Zero` Pokud se eigenvalue $ + $1, a `One` Pokud je zjištěna $-$1 eigenvalue.

## <a name="remarks"></a>Poznámky

Pokud jsou pole základu a qubit různými délkami, operace se nezdaří.