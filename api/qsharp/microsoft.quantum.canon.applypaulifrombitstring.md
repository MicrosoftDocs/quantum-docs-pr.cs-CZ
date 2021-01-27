---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: Operace ApplyPauliFromBitString
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: e0edd8420127339116e525421ba23e246dcf0a45
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841589"
---
# <a name="applypaulifrombitstring-operation"></a>Operace ApplyPauliFromBitString

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje operátor Pauli na každou qubit v poli, pokud odpovídající bit logického pole odpovídá danému vstupu.

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Operátor Pauli, který se má použít na `qubits[idx]` WHERE `bitsApply == bits[idx]`


### <a name="bitapply--bool"></a>bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)

Pokud je tato hodnota bit, použijte Pauli.


### <a name="bits--bool"></a>bity: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Logický registr určující, který odpovídající qubit v `qubits` by měl být provozován


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registrování v registru, ve kterém se selektivně použijí zadaný Pauli operátor



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Pole Boolean a registr s police musí mít stejnou délku.