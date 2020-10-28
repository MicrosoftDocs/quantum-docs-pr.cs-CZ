---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA
title: Operace ApplyToFirstTwoQubitsCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsCA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 0c5e29fbca8449f8122f2a9f988797e94e27da60
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704793"
---
# <a name="applytofirsttwoqubitsca-operation"></a>Operace ApplyToFirstTwoQubitsCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Použije operaci na první dvě qubits v registru.
Modifikátor `CA` označuje, že operace je ovladatelné a s sousedními poli.

```qsharp
operation ApplyToFirstTwoQubitsCA (op : ((Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="op--qubitqubit--unit-adj--ctl"></a>op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [jednotky](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

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