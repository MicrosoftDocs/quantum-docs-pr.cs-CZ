---
uid: Microsoft.Quantum.Canon.ApplyToPartitionCA
title: Operace ApplyToPartitionCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionCA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 8ea437a0e25ed43eb745a7740ecd8861ced1350a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704713"
---
# <a name="applytopartitionca-operation"></a>Operace ApplyToPartitionCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje dvojici operací na daný oddíl registru do dvou částí.
Modifikátor `CA` označuje, že operace je ovladatelné a s sousedními poli.

```qsharp
operation ApplyToPartitionCA (op : ((Qubit[], Qubit[]) => Unit is Ctl + Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="op--qubitqubit--unit-ctl--adj"></a>op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[];[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) [=> CTL](xref:microsoft.quantum.lang-ref.unit) a ADJ

Dvojice operací, které mají být pro daný oddíl aplikovány.


### <a name="numberofqubitstofirstargument--int"></a>numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)

Počet qubits z cíle na vložení do první části oddílu
Zbývající qubits tvoří druhou část oddílu.


### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registr qubitsů, které jsou rozděleny na oddíly a provozovány na základě dané dvě operace.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToPartition. Canon.](xref:Microsoft.Quantum.Canon.ApplyToPartition)