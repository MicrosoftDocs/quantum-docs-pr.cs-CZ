---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 76f482b86ff4a27b6e6ce6ae4ec3d59422563f12
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842252"
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