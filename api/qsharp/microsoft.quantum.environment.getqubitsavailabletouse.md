---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Operace GetQubitsAvailableToUse
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 2ed8c3789331a15b351769be960d06f6364d8047
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827804"
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