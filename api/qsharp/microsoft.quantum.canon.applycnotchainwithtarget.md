---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: Operace ApplyCNOTChainWithTarget
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: fd0a0f3e1db89946aec2c63f3cde7a021608eea5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705440"
---
# <a name="applycnotchainwithtarget-operation"></a>Operace ApplyCNOTChainWithTarget

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Vypočítá paritu pole qubits do cílového qubit.

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit
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