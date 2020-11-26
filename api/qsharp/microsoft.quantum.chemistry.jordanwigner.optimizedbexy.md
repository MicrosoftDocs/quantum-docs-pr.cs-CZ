---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEXY
title: Operace OptimizedBEXY
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEXY
qsharp.summary: A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$. That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$
ms.openlocfilehash: 3530e62671e16cfb5500c56c8e5e477dbb56e67e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224849"
---
# <a name="optimizedbexy-operation"></a>Operace OptimizedBEXY

Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Jednotková $U $, která používá řetězec Pauli v $ (X ^ {z + 1} \_ py ^ {z} \_ p) z \_ {p-1}... Z_0 $ on qubits $0.. p $ podmíněně v indexu $z \in \{ 0, 1 \} $ a $p $. To znamená $ $ \begin{align} U\ket {z} \ KET {p} \ KET {\ psí} = \ket{z}\ket{p} (X ^ {z + 1} \_ py ^ {z} \_ p) z \_ {p-1}... Z_0 \ket{\psi} \end{align} $ $

```qsharp
operation OptimizedBEXY (pauliBasis : Qubit, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="paulibasis--qubit"></a>pauliBasis: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Pokud je tento qubit ve stavu $ \ket {0} $, použije se $X $. Pokud je ve stavu $ \ket {1} $, použije se $Y $.


### <a name="indexregister--littleendian"></a>indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Stav $ \ket{p} $ tohoto registru určuje qubit, na kterém je použita $X $ nebo $Y $.


### <a name="targetregister--qubit"></a>targetRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registr qubits, na kterých se používají operátory Pauli



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Reference

- Kódování elektronického spektra v Okruhech v případě využití lineární T, Babbush, Craig Gidney, Dominic W. bobulovin, Nathan Wiebe, Jarrod McClean, Alexandru bledější, Austin Fowlera, Hartmut Neven https://arxiv.org/abs/1805.03662