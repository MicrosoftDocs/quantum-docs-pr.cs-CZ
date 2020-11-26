---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: Uživatelem definovaný typ ContinuousOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: fb05e97c635ba75fc2d85dc2a7cea27f3a3af63f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226787"
---
# <a name="continuousoracle-user-defined-type"></a>Uživatelem definovaný typ ContinuousOracle

Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje Oracle v nepřetržitém čase.

Toto je Oracle, který implementuje $U (\delta t): \ket{\psi (t)} \mapsto \ket{\psi (t + \delta t)} $ všechny časy $t $, kde $U $ je pevná operace a kde $ \delta t $ je nezáporné reálné číslo.

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

