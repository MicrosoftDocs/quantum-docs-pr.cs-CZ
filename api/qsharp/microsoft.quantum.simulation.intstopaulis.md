---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 2333dcbd2988480e2b2b9b217b26705f3578de00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230527"
---
# <a name="intstopaulis-function"></a>IntsToPaulis – funkce

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Převede pole celých čísel na pole qubitch operátorů Pauli s jedním.

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a>Vstup

### <a name="ints--int"></a>čísla: [int](xref:microsoft.quantum.lang-ref.int)[]

Pole celých čísel v rozsahu `0..3`  , který má být převeden na Pauli operátory.



## <a name="output--pauli"></a>Výstup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Pole `paulis` operátorů Pauli `Pauli[]` se stejnou délkou `ints` , která `paulis[idxPauli]` je rovna elementu z `[PauliI, PauliX, PauliY, PauliZ]` daného `ints[idxPauli]` .