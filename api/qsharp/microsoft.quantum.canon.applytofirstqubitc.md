---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: Operace ApplyToFirstQubitC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e2c137ad4a8252731acf94d6f2343f8fd386b8e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704880"
---
# <a name="applytofirstqubitc-operation"></a>Operace ApplyToFirstQubitC

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje operaci op na první qubit v registru.
Modifikátor `C` označuje, že operace je ovladatelné.

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="op--qubit--unit-ctl"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => CTL pro [jednotky](xref:microsoft.quantum.lang-ref.unit)

Operace, která se má použít pro první qubit


### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit pole na první qubit, ze kterého se operace používá.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToFirstQubit. Canon.](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)