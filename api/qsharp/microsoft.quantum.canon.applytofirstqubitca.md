---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: Operace ApplyToFirstQubitCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 2e1db23ad819a85df99a826f406d9b0fbcc7a175
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704872"
---
# <a name="applytofirstqubitca-operation"></a>Operace ApplyToFirstQubitCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje operaci op na první qubit v registru.
Modifikátor `CA` označuje, že operace je ovladatelné a s sousedními poli.

```qsharp
operation ApplyToFirstQubitCA (op : (Qubit => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="op--qubit--unit-adj--ctl"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [jednotky](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operace, která se má použít pro první qubit


### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit pole na první qubit, ze kterého se operace používá.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToFirstQubit. Canon.](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)