---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Operace GetQubitsAvailableToBorrow
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow. This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.
ms.openlocfilehash: cb56ce4aefd7a03c0f0827b8d34688ef17988f56
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698041"
---
# <a name="getqubitsavailabletoborrow-operation"></a>Operace GetQubitsAvailableToBorrow

Obor názvů: [Microsoft.. Environment](xref:Microsoft.Quantum.Environment)

Balíček [](https://nuget.org/packages/)


Vrátí počet qubitsů, které jsou aktuálně k dispozici k vypůjčení.
To zahrnuje nepoužívané qubits; To znamená, že zahrnuje qubits, který vrátil `GetQubitsAvailableToUse` .

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Počet qubits, které mohou být přiděleny v `borrowing` příkazu.
Pokud použitý cílový počítač tyto informace neposkytuje, `-1` vrátí se.

## <a name="see-also"></a>Viz také

- [Microsoft. GetQubitsAvailableToUse. Environment.](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)