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
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="d81f8-102">Uživatelem definovaný typ DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="d81f8-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="d81f8-103">Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="d81f8-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="d81f8-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d81f8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d81f8-105">Představuje Oracle pro deterministické přípravení stavu.</span><span class="sxs-lookup"><span data-stu-id="d81f8-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="d81f8-106">Vstup pro Oracle $O $ je:</span><span class="sxs-lookup"><span data-stu-id="d81f8-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="d81f8-107">Registr, ve kterém bude uložen požadovaný stav pro tento počet dat $ \ket{\psi} \_ s $</span><span class="sxs-lookup"><span data-stu-id="d81f8-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="d81f8-108">Poznámky</span><span class="sxs-lookup"><span data-stu-id="d81f8-108">Remarks</span></span>

<span data-ttu-id="d81f8-109">Tento Oracle definovaný pomocí $O \ket {0} = \ket{\psi} $ pracuje na stavovém základě výpočtu $ \ket {0} $ a vytvoří stav $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="d81f8-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="d81f8-110">Prvním parametrem je qubit registr $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="d81f8-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>