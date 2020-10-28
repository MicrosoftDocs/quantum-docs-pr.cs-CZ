---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA
title: Operace ApplyToFirstTwoQubitsA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 911e9bc3d02bf6c0395c30fa167a6cb730dc666e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704817"
---
# <a name="applytofirsttwoqubitsa-operation"></a>Operace ApplyToFirstTwoQubitsA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Použije operaci na první dvě qubits v registru.
Modifikátor `A` označuje, že operace je sousední.

```qsharp
operation ApplyToFirstTwoQubitsA (op : ((Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="op--qubitqubit--unit-adj"></a>op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [jednotky](xref:microsoft.quantum.lang-ref.unit) ADJ

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