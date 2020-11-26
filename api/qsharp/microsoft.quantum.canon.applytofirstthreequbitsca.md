---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA
title: Operace ApplyToFirstThreeQubitsCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsCA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 7e090a116a63e26278b05dc7c2fda9b65ff15bae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208784"
---
# <a name="applytofirstthreequbitsca-operation"></a>Operace ApplyToFirstThreeQubitsCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Použije operaci na první tři qubits v registru.
Modifikátor `CA` označuje, že operace je ovladatelné a s sousedními poli.

```qsharp
operation ApplyToFirstThreeQubitsCA (op : ((Qubit, Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="op--qubitqubitqubit--unit--is-adj--ctl"></a>op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Operace, která se má použít pro první tři qubits


### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit pole na první tři qubits, ze kterých se operace používá.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Jedná se o ekvivalent:

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToFirstThreeQubits. Canon.](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)