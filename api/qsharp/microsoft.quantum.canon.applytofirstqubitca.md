---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: Operace ApplyToFirstQubitCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: bc2b1275b4258b9cc2db45c9e5cfe14f7eee0c67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208801"
---
# <a name="applytofirstqubitca-operation"></a>Operace ApplyToFirstQubitCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje operaci op na první qubit v registru.
Modifikátor `CA` označuje, že operace je ovladatelné a s sousedními poli.

```qsharp
operation ApplyToFirstQubitCA (op : (Qubit => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="op--qubit--unit--is-adj--ctl"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [jednotka](xref:microsoft.quantum.lang-ref.unit) qubit je ADJ + CTL

Operace, která se má použít pro první qubit


### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit pole na první qubit, ze kterého se operace používá.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToFirstQubit. Canon.](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)