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
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="4b9e7-102">Uživatelem definovaný typ DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="4b9e7-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="4b9e7-103">Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="4b9e7-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="4b9e7-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4b9e7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4b9e7-105">Představuje Oracle pro deterministické přípravení stavu.</span><span class="sxs-lookup"><span data-stu-id="4b9e7-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="4b9e7-106">Vstup pro Oracle $O $ je:</span><span class="sxs-lookup"><span data-stu-id="4b9e7-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="4b9e7-107">Registr, ve kterém bude uložen požadovaný stav pro tento počet dat $ \ket{\psi} \_ s $</span><span class="sxs-lookup"><span data-stu-id="4b9e7-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="4b9e7-108">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4b9e7-108">Remarks</span></span>

<span data-ttu-id="4b9e7-109">Tento Oracle definovaný pomocí $O \ket {0} = \ket{\psi} $ pracuje na stavovém základě výpočtu $ \ket {0} $ a vytvoří stav $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="4b9e7-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="4b9e7-110">Prvním parametrem je qubit registr $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="4b9e7-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>