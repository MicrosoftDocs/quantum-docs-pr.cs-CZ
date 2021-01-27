---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC
title: Operace ApplyToFirstTwoQubitsC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsC
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: f71209a806b0d1d712a3c776eb45e62d1cd5d5f7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841351"
---
# <a name="applytofirsttwoqubitsc-operation"></a>Operace ApplyToFirstTwoQubitsC

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Použije operaci na první dvě qubits v registru.
Modifikátor `C` označuje, že operace je ovladatelné.

```qsharp
operation ApplyToFirstTwoQubitsC (op : ((Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a>Vstup

### <a name="op--qubitqubit--unit--is-ctl"></a>op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL

Operace, která se má použít pro první dvě qubits


### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit pole na první dvě qubits, z nichž je operace použita.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Jedná se o ekvivalent:

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToFirstTwoQubits. Canon.](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)