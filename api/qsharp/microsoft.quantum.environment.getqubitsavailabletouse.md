---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Operace GetQubitsAvailableToUse
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: ce461b03a08b4c83b9de142c957ce5c590fe9659
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201406"
---
# <a name="getqubitsavailabletouse-operation"></a>Operace GetQubitsAvailableToUse

Obor názvů: [Microsoft.. Environment](xref:Microsoft.Quantum.Environment)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Vrátí počet qubits aktuálně dostupných k použití.

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Počet qubits, které mohou být přiděleny v `using` příkazu.
Pokud použitý cílový počítač tyto informace neposkytuje, `-1` vrátí se.

## <a name="see-also"></a>Viz také

- [Microsoft. GetQubitsAvailableToBorrow. Environment.](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)