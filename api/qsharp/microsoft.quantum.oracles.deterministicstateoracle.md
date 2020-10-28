---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: Uživatelem definovaný typ DeterministicStateOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: f02267d48cf42fb5b02782dc6b667ac7b60a05dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708776"
---
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="104aa-102">Uživatelem definovaný typ DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="104aa-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="104aa-103">Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="104aa-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="104aa-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="104aa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="104aa-105">Představuje Oracle pro deterministické přípravení stavu.</span><span class="sxs-lookup"><span data-stu-id="104aa-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="104aa-106">Vstup pro Oracle $O $ je:</span><span class="sxs-lookup"><span data-stu-id="104aa-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="104aa-107">Registr, ve kterém bude uložen požadovaný stav pro tento počet dat $ \ket{\psi} \_ s $</span><span class="sxs-lookup"><span data-stu-id="104aa-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="104aa-108">Poznámky</span><span class="sxs-lookup"><span data-stu-id="104aa-108">Remarks</span></span>

<span data-ttu-id="104aa-109">Tento Oracle definovaný pomocí $O \ket {0} = \ket{\psi} $ pracuje na stavovém základě výpočtu $ \ket {0} $ a vytvoří stav $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="104aa-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="104aa-110">Prvním parametrem je qubit registr $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="104aa-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>