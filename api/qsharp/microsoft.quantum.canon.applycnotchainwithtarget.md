---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: Operace ApplyCNOTChainWithTarget
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: 8ec85ce5805b3bbd1e1f7c739f27de3a861bc79e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219103"
---
# <a name="applycnotchainwithtarget-operation"></a>Operace ApplyCNOTChainWithTarget

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vypočítá paritu pole qubits do cílového qubit.

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Pokud je pole zpočátku ve stavu $ \ket{q_0} \ket{q_1} \cdots \ket{q_ {\Text{Target}}} $, konečný stav je dán v $ \ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_ {n-1} \oplus \cdots \oplus q_0 \oplus q_ {\Text{Target}}} $.

## <a name="input"></a>Vstup

### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Pole qubits, na kterém je vypočítána parita.


### <a name="targetqubit--qubit"></a>targetQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Konečný qubit, do kterého je parita ' qubits ' XORed.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Následují ekvivalenty:

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

a

```qsharp
ApplyCNOTChain(qs);
```