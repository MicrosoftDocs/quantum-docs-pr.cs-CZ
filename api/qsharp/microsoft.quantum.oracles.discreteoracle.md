---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: Uživatelem definovaný typ DiscreteOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: 4b85f58889ef9cc55518009bdd9b59bdb2b5b842
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842572"
---
# <a name="discreteoracle-user-defined-type"></a>Uživatelem definovaný typ DiscreteOracle

Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje diskrétní čas Oracle.

Jedná se o Oracle, který implementuje $U ^ m $ pro pevnou operaci $U $ a nezáporné celé číslo $m $.

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```

