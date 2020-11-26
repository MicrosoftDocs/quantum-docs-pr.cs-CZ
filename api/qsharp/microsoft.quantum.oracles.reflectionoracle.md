---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: Uživatelem definovaný typ ReflectionOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 7bb0626e7cca9ae0b640699ea57f2e114bda2d06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226651"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="67b51-102">Uživatelem definovaný typ ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="67b51-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="67b51-103">Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="67b51-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="67b51-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="67b51-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="67b51-105">Představuje reflexi Oracle.</span><span class="sxs-lookup"><span data-stu-id="67b51-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="67b51-106">Reflexe Oracle, $O $, má vstupy:</span><span class="sxs-lookup"><span data-stu-id="67b51-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="67b51-107">Fáze $ \phi $, o kterou se má otočit odrážet mezera.</span><span class="sxs-lookup"><span data-stu-id="67b51-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="67b51-108">Registr qubit, na kterém se má provést daná reflexe.</span><span class="sxs-lookup"><span data-stu-id="67b51-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="67b51-109">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="67b51-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a><span data-ttu-id="67b51-110">ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="67b51-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="67b51-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="67b51-111">Remarks</span></span>

<span data-ttu-id="67b51-112">Tento Oracle $O = \boldone-(1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ provede částečný odraz pomocí fáze $ \phi $ o jednom čistě stavu $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="67b51-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>