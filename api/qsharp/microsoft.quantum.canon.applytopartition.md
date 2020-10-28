---
uid: Microsoft.Quantum.Canon.ApplyToPartition
title: Operace ApplyToPartition
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartition
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts.
ms.openlocfilehash: c1f43e7936fc1c18fb665388e9892dc3b74cdd05
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704728"
---
# <a name="applytopartition-operation"></a>Operace ApplyToPartition

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje dvojici operací na daný oddíl registru do dvou částí.

```qsharp
operation ApplyToPartition (op : ((Qubit[], Qubit[]) => Unit), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="op--qubitqubit--unit"></a>op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[];[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Dvojice operací, které mají být pro daný oddíl aplikovány.


### <a name="numberofqubitstofirstargument--int"></a>numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)

Počet qubits z cíle na vložení do první části oddílu
Zbývající qubits tvoří druhou část oddílu.


### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registr qubitsů, které jsou rozděleny na oddíly a provozovány na základě dané dvě operace.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToPartitionA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToPartitionA)
- [Microsoft. proApplyToPartitionC. Canon.](xref:Microsoft.Quantum.Canon.ApplyToPartitionC)
- [Microsoft. proApplyToPartitionCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToPartitionCA)