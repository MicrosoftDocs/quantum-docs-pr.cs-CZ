---
uid: Microsoft.Quantum.Canon.ApplyCCNOTChain
title: Operace ApplyCCNOTChain
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCCNOTChain
qsharp.summary: Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers. Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.
ms.openlocfilehash: 53fdd59b06d542494647acb665f248fc18de93d9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845140"
---
# <a name="applyccnotchain-operation"></a>Operace ApplyCCNOTChain

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementuje kaskády CCNOTch bran řízených v odpovídajících bitech dvou registrů qubit, které fungují na dalších qubit jednoho z registrů.
Počínaje od qubits na pozici 0 v obou registrech jako ovládací prvky se CCNOT použije na qubit na pozici 1 cílového registru, kterou řídí qubits na pozici 1 v qubit na pozici 2 v cílovém registru atd., končící akci na cílovém qubit na pozici `Length(nQubits)-1` .

```qsharp
operation ApplyCCNOTChain (register : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit registr, používá se pouze pro ovládací prvky.


### <a name="targets--qubit"></a>cíle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit registr, který se používá pro ovládací prvky a jako cíl.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Cílový registr qubit musí mít jeden qubit více než druhý registr.