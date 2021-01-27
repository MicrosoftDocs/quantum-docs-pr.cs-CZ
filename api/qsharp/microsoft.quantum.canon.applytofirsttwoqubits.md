---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubits
title: Operace ApplyToFirstTwoQubits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubits
qsharp.summary: Applies an operation to the first two qubits in the register.
ms.openlocfilehash: c89ea89c055a950a9aee533653d40c84d8e179da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841365"
---
# <a name="applytofirsttwoqubits-operation"></a>Operace ApplyToFirstTwoQubits

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Použije operaci na první dvě qubits v registru.

```qsharp
operation ApplyToFirstTwoQubits (op : ((Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="op--qubitqubit--unit"></a>op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

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

- [Microsoft. proApplyToFirstTwoQubitsA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA)
- [Microsoft. proApplyToFirstTwoQubitsC. Canon.](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC)
- [Microsoft. proApplyToFirstTwoQubitsCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA)