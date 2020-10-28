---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC
title: Operace ApplyToFirstThreeQubitsC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsC
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 9450b084cd77f75511fe631cda9a4f9fc426142d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704857"
---
# <a name="applytofirstthreequbitsc-operation"></a>Operace ApplyToFirstThreeQubitsC

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Použije operaci na první tři qubits v registru.
Modifikátor `C` označuje, že operace je ovladatelné.

```qsharp
operation ApplyToFirstThreeQubitsC (op : ((Qubit, Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="op--qubitqubitqubit--unit-ctl"></a>op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) = seznam CTL pro> [jednotku](xref:microsoft.quantum.lang-ref.unit)

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