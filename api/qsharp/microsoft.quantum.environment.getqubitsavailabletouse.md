---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Operace GetQubitsAvailableToUse
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 25d43d369193fc7453fd5ce9c50769c438a69afb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698040"
---
# <a name="getqubitsavailabletouse-operation"></a>Operace GetQubitsAvailableToUse

Obor názvů: [Microsoft.. Environment](xref:Microsoft.Quantum.Environment)

Balíček [](https://nuget.org/packages/)


Vrátí počet qubits aktuálně dostupných k použití.

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Počet qubits, které mohou být přiděleny v `using` příkazu.
Pokud použitý cílový počítač tyto informace neposkytuje, `-1` vrátí se.

## <a name="see-also"></a>Viz také

- [Microsoft. GetQubitsAvailableToBorrow. Environment.](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)