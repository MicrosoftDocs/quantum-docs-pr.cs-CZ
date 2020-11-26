---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Operace GetQubitsAvailableToBorrow
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: 30b97c2b6e1353f008d085c3bae6160763557c67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201457"
---
# <a name="getqubitsavailabletoborrow-operation"></a>Operace GetQubitsAvailableToBorrow

Obor názvů: [Microsoft.. Environment](xref:Microsoft.Quantum.Environment)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Vrátí počet qubitsů, které jsou aktuálně k dispozici k vypůjčení.

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Počet qubits, které by mohly být vypůjčené a nebudou se přidělovat jako součást `borrowing` příkazu.
Pokud použitý cílový počítač tyto informace neposkytuje, `-1` vrátí se.

## <a name="see-also"></a>Viz také

- [Microsoft. GetQubitsAvailableToUse. Environment.](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)