---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 18edb600f7b5b33c7ad98e78e32903c570082225
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229201"
---
# <a name="inttopauli-function"></a>IntToPauli – funkce

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Převede celé číslo na operátor Pauli s jedním qubit.

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a>Vstup

### <a name="idx--int"></a>IDX: [int](xref:microsoft.quantum.lang-ref.int)

Celé číslo v rozsahu `0..3` , které má být převedeno na Pauli operátory.



## <a name="output--pauli"></a>Výstup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

`Pauli`Operátor daného `[PauliI, PauliX, PauliY, PauliZ][idx]` .