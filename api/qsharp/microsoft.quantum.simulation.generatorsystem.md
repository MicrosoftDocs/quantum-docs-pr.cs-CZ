---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: Uživatelem definovaný typ GeneratorSystem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: c03caf99b197410c7fa15021c8acaaf55a728781
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708890"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="01ac7-102">Uživatelem definovaný typ GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="01ac7-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="01ac7-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="01ac7-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="01ac7-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="01ac7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="01ac7-105">Představuje kolekci `GeneratorIndex` ES.</span><span class="sxs-lookup"><span data-stu-id="01ac7-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="01ac7-106">Procházíme přes tuto kolekci s použitím jednoho indexu celé číslo a velikost kolekce se předpokládá jako známá.</span><span class="sxs-lookup"><span data-stu-id="01ac7-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="01ac7-107">Poznámky</span><span class="sxs-lookup"><span data-stu-id="01ac7-107">Remarks</span></span>

<span data-ttu-id="01ac7-108">Instance `GeneratorSystem` lze snadno definovat pomocí <xref:microsoft.quantum.arrays.lookupfunction> funkce.</span><span class="sxs-lookup"><span data-stu-id="01ac7-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="01ac7-109">Viz také</span><span class="sxs-lookup"><span data-stu-id="01ac7-109">See Also</span></span>

- [<span data-ttu-id="01ac7-110">Microsoft. Forms. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="01ac7-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)