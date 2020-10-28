---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: Operace ApplyToFirstThreeQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: 61330f9e9b1f6b9f3965c9240505814b295aaefe
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704864"
---
# <a name="applytofirstthreequbits-operation"></a>Operace ApplyToFirstThreeQubits

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Použije operaci na první tři qubits v registru.

```qsharp
operation ApplyToFirstThreeQubits (op : ((Qubit, Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="op--qubitqubitqubit--unit"></a>op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

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

- [Microsoft. proApplyToFirstThreeQubitsC. Canon.](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC)
- [Microsoft. proApplyToFirstThreeQubitsA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA)
- [Microsoft. proApplyToFirstThreeQubitsCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA)