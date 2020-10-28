---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 605257aa7ca39e457127e3c3459b5891145b1863
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697145"
---
# <a name="intstopaulis-function"></a>IntsToPaulis – funkce

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček [](https://nuget.org/packages/)


Převede pole celých čísel na pole qubitch operátorů Pauli s jedním.

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a>Vstup

### <a name="ints--int"></a>čísla: [int](xref:microsoft.quantum.lang-ref.int)[]

Pole celých čísel v rozsahu `0..3`  , který má být převeden na Pauli operátory.



## <a name="output--pauli"></a>Výstup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Pole `paulis` operátorů Pauli `Pauli[]` se stejnou délkou `ints` , která `paulis[idxPauli]` je rovna elementu z `[PauliI, PauliX, PauliY, PauliZ]` daného `ints[idxPauli]` .