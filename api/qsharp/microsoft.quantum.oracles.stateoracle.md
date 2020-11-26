---
uid: Microsoft.Quantum.Oracles.StateOracle
title: Uživatelem definovaný typ StateOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6b2cf09c23942a586414daccb99cbb27b5026b9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226600"
---
# <a name="stateoracle-user-defined-type"></a>Uživatelem definovaný typ StateOracle

Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje Oracle pro přípravu stavu.

Vstupy pro Oracle $O $ jsou:

- Celé číslo, které označuje příznak qubit $f $.
- Systém registruje $s $, ve kterém bude uložen požadovaný stav \ket{\psi} $ \_ s $.

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Poznámky

Tento jazyk Oracle definovaný pomocí $ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ psí} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, $ $ funguje na výpočetním stavu na bázi výpočtů $ \ket {0} \_ {f} \ket {0} \_ s $, který vytvoří cílový stav $ \ket{\psi} s \_ $ s amplitudou $ \lambda $ v tomto případě příznakem $ \ket {1} \_ f $.
První parametr je index qubit registrace \ket {0} \_ f $. Druhý parametr zahrnuje oba Registry.