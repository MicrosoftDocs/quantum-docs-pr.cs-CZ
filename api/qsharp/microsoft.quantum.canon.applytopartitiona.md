---
uid: Microsoft.Quantum.Canon.ApplyToPartitionA
title: Operace ApplyToPartitionA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: f8f773e9fc3c18467185f9717a235649be8b385a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841291"
---
# <a name="applytopartitiona-operation"></a>Operace ApplyToPartitionA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje dvojici operací na daný oddíl registru do dvou částí.
Modifikátor `A` označuje, že operace je sousední.

```qsharp
operation ApplyToPartitionA (op : ((Qubit[], Qubit[]) => Unit is Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Vstup

### <a name="op--qubitqubit--unit--is-adj"></a>op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ

Dvojice operací, které mají být pro daný oddíl aplikovány.


### <a name="numberofqubitstofirstargument--int"></a>numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)

Počet qubits z cíle na vložení do první části oddílu
Zbývající qubits tvoří druhou část oddílu.


### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registr qubitsů, které jsou rozděleny na oddíly a provozovány na základě dané dvě operace.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToPartition. Canon.](xref:Microsoft.Quantum.Canon.ApplyToPartition)