---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: Uživatelem definovaný typ ContinuousOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: ac254b7556878550216d5c0c9222620fdc5c5702
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855933"
---
# <a name="continuousoracle-user-defined-type"></a>Uživatelem definovaný typ ContinuousOracle

Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje Oracle v nepřetržitém čase.

Toto je Oracle, který implementuje $U (\delta t): \ket{\psi (t)} \mapsto \ket{\psi (t + \delta t)} $ všechny časy $t $, kde $U $ je pevná operace a kde $ \delta t $ je nezáporné reálné číslo.

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

