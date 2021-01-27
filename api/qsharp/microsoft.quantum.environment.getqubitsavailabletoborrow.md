---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Operace GetQubitsAvailableToBorrow
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: f2294fadb9c10d800b7a743fbfe0810f36f18516
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853251"
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