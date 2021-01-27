---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: Operace SelectZ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 2b38be5c196d81635daa8b478f6e727fdf378c62
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850238"
---
# <a name="selectz-operation"></a>Operace SelectZ

Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Jednotková $U $, která aplikuje bránu $Z Pauli na qubits $p $ podmíněně ve stavu indexu $ \ket{p} $. To znamená $ $ \begin{align} U\ket {p} \ KET {\ psí} = \ket{p}Z \_ p\ket {\ psí} \end{align} $ $

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="indexregister--littleendian"></a>indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Stav $ \ket{p} $ tohoto registru určuje qubit, na kterém je použita $Z $.


### <a name="targetregister--qubit"></a>targetRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registr qubits, na kterých se používají operátory Pauli



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

