---
uid: Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
title: Uživatelem definovaný typ MixedStatePreparationRequirements
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: MixedStatePreparationRequirements
qsharp.summary: Represents the number of qubits required in order to prepare a given mixed state.
ms.openlocfilehash: df57b7b43fc84f7ddf68392f6a2b7013225da730
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856932"
---
# <a name="mixedstatepreparationrequirements-user-defined-type"></a><span data-ttu-id="090c0-102">Uživatelem definovaný typ MixedStatePreparationRequirements</span><span class="sxs-lookup"><span data-stu-id="090c0-102">MixedStatePreparationRequirements user defined type</span></span>

<span data-ttu-id="090c0-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="090c0-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="090c0-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="090c0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="090c0-105">Představuje počet qubits vyžadovaných pro přípravu daného smíšeného stavu.</span><span class="sxs-lookup"><span data-stu-id="090c0-105">Represents the number of qubits required in order to prepare a given mixed state.</span></span>

```qsharp

newtype MixedStatePreparationRequirements = (NTotalQubits : Int, (NIndexQubits : Int, NGarbageQubits : Int));
```



## <a name="named-items"></a><span data-ttu-id="090c0-106">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="090c0-106">Named Items</span></span>

### <a name="ntotalqubits--int"></a><span data-ttu-id="090c0-107">NTotalQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="090c0-107">NTotalQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="nindexqubits--int"></a><span data-ttu-id="090c0-108">NIndexQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="090c0-108">NIndexQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="ngarbagequbits--int"></a><span data-ttu-id="090c0-109">NGarbageQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="090c0-109">NGarbageQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="see-also"></a><span data-ttu-id="090c0-110">Viz také</span><span class="sxs-lookup"><span data-stu-id="090c0-110">See Also</span></span>

- [<span data-ttu-id="090c0-111">Microsoft. PurifiedMixedState.</span><span class="sxs-lookup"><span data-stu-id="090c0-111">Microsoft.Quantum.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.PurifiedMixedState)