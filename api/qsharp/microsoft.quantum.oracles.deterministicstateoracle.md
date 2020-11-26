---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: Uživatelem definovaný typ DeterministicStateOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6f8f80aacd3386ba61675101acb87e09fff5afff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193926"
---
# <a name="deterministicstateoracle-user-defined-type"></a>Uživatelem definovaný typ DeterministicStateOracle

Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje Oracle pro deterministické přípravení stavu.

Vstup pro Oracle $O $ je:

- Registr, ve kterém bude uložen požadovaný stav pro tento počet dat $ \ket{\psi} \_ s $

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Poznámky

Tento Oracle definovaný pomocí $O \ket {0} = \ket{\psi} $ pracuje na stavovém základě výpočtu $ \ket {0} $ a vytvoří stav $ \ket{\psi} $.
Prvním parametrem je qubit registr $ \ket{\psi} $.