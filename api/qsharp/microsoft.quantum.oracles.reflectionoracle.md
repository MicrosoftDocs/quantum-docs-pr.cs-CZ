---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: Uživatelem definovaný typ ReflectionOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 8e35e7e508ea7e0c30ea2a70633f71a6c87d4be1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708740"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="76af4-102">Uživatelem definovaný typ ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="76af4-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="76af4-103">Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="76af4-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="76af4-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="76af4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="76af4-105">Představuje reflexi Oracle.</span><span class="sxs-lookup"><span data-stu-id="76af4-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="76af4-106">Reflexe Oracle, $O $, má vstupy:</span><span class="sxs-lookup"><span data-stu-id="76af4-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="76af4-107">Fáze $ \phi $, o kterou se má otočit odrážet mezera.</span><span class="sxs-lookup"><span data-stu-id="76af4-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="76af4-108">Registr qubit, na kterém se má provést daná reflexe.</span><span class="sxs-lookup"><span data-stu-id="76af4-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="76af4-109">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="76af4-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit-adj--ctl"></a><span data-ttu-id="76af4-110">ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="76af4-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="76af4-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="76af4-111">Remarks</span></span>

<span data-ttu-id="76af4-112">Tento Oracle $O = \boldone-(1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ provede částečný odraz pomocí fáze $ \phi $ o jednom čistě stavu $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="76af4-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>