---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: Operace ApplyToFirstQubitCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: ba82199cc7a548d771027141780873c05de71c57
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841430"
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

### <a name="op--qubit--unit--is-adj--ctl"></a>op: [](xref:microsoft.quantum.lang-ref.qubit) => [jednotka](xref:microsoft.quantum.lang-ref.unit) qubit je ADJ + CTL

Operace, která se má použít pro první qubit


### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit pole na první qubit, ze kterého se operace používá.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToFirstQubit. Canon.](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)