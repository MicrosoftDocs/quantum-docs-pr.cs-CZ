---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitA
title: Operace ApplyToFirstQubitA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitA
qsharp.summary: Applies an operation to the first qubit in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 4f0b209988c01076bdd0429d36d98c8060141618
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208835"
---
# <a name="applytofirstqubita-operation"></a>Operace ApplyToFirstQubitA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Použije operaci na první qubit v registru.
Modifikátor `A` označuje, že operace je sousední.

```qsharp
operation ApplyToFirstQubitA (op : (Qubit => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Vstup

### <a name="op--qubit--unit--is-adj"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [jednotka](xref:microsoft.quantum.lang-ref.unit) qubit je ADJ.

Operace, která se má použít pro první qubit


### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit pole na první qubit, ze kterého se operace používá.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToFirstQubit. Canon.](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)