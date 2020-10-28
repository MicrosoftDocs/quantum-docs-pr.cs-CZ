---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC
title: Operace ApplyToFirstTwoQubitsC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsC
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 97706ffcc8700a0055ff37bbbaccc6fb4f8854b6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704808"
---
# <a name="applytofirsttwoqubitsc-operation"></a>Operace ApplyToFirstTwoQubitsC

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Použije operaci na první dvě qubits v registru.
Modifikátor `C` označuje, že operace je ovladatelné.

```qsharp
operation ApplyToFirstTwoQubitsC (op : ((Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="op--qubitqubit--unit-ctl"></a>op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) = seznam CTL pro> [jednotku](xref:microsoft.quantum.lang-ref.unit)

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