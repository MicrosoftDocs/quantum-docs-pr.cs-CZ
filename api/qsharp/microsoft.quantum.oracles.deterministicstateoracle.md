---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: Uživatelem definovaný typ DeterministicStateOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 10ae9e52f298cdfb92dd6a9e5cf85960bece6800
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842596"
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