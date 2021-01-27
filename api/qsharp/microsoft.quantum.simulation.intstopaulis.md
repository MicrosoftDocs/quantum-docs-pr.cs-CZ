---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 6904054bb1aff3a57c80882694b4c217812b2b81
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842225"
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