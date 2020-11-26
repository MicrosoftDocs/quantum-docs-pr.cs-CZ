---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: Operace PrepareQubit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  > [!WARNING]

  > PrepareQubit has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> instead.


  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: 84674d70d6a038ceaf1c637b22afa1b724d90795
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193518"
---
# <a name="preparequbit-operation"></a>Operace PrepareQubit

Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> PrepareQubit se už nepoužívá. <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate>Místo toho ho použijte.

Připraví qubit na + 1 ( `Zero` ) eigenstate daného operátoru Pauli.
Pokud se udělí operátor identity, qubit se připraví do maximálního smíšeného stavu.

Pokud byl původně qubit ve stavu $ \ket {0} $, tato operace připraví qubit v $ + $1 eigenstate daného operátoru Pauli, nebo pro `PauliI` , v případě, že je místo toho ve stavu "maximálního smíšené" (viz <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).

Pokud byl qubit v jiném stavu než $ \ket {0} $, tato operace použije následující brány: $H $ for `PauliX` , $HS $ for `PauliY` , $I $ pro `PauliZ` a <xref:microsoft.quantum.preparation.preparesinglequbitidentity> pro `PauliI` .

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a>Vstup

### <a name="basis--pauli"></a>základ: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Operátor Pauli $P $.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, který se má připravit.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

