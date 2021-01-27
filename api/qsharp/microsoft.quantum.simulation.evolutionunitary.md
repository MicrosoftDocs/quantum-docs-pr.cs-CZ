---
uid: Microsoft.Quantum.Simulation.EvolutionUnitary
title: Uživatelem definovaný typ EvolutionUnitary
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionUnitary
qsharp.summary: >-
  Represents a unitary time-evolution operator.

  The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.
ms.openlocfilehash: ea160bb9a0a8bb5106c3e37a6a16155bad71dd25
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856048"
---
# <a name="evolutionunitary-user-defined-type"></a>Uživatelem definovaný typ EvolutionUnitary

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje jednotnou obsluhu časového vývoje.

Prvním parametrem je doba trvání vývoje času a druhý parametr je qubit registrem, který se používá v rámci jednotně.

```qsharp

newtype EvolutionUnitary = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

