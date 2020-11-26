---
uid: Microsoft.Quantum.Preparation.PreparePauliEigenstate
title: Operace PreparePauliEigenstate
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PreparePauliEigenstate
qsharp.summary: Prepares a qubit in the positive eigenstate of a given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.
ms.openlocfilehash: b24852bb3a455a9fe04b3535156d0c3dfb1a7d12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193688"
---
# <a name="preparepaulieigenstate-operation"></a>Operace PreparePauliEigenstate

Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Připraví qubit v kladné eigenstate daného operátoru Pauli.
Pokud se udělí operátor identity, qubit se připraví do maximálního smíšeného stavu.

```qsharp
operation PreparePauliEigenstate (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="description"></a>Popis

Pokud byl původně qubit ve stavu $ \ket {0} $, tato operace připraví qubit v $ + $1 eigenstate daného operátoru Pauli, nebo pro `PauliI` , v případě, že je místo toho ve stavu "maximálního smíšené" (viz <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).

Pokud byl qubit v jiném stavu než $ \ket {0} $, tato operace použije následující brány: $H $ for `PauliX` , $HS $ for `PauliY` , $I $ pro `PauliZ` a <xref:microsoft.quantum.preparation.preparesinglequbitidentity> pro `PauliI` .

## <a name="input"></a>Vstup

### <a name="basis--pauli"></a>základ: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Operátor Pauli $P $.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, který se má připravit.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

