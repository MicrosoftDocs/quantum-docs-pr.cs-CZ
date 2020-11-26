---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: Uživatelem definovaný typ GeneratorSystem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 20092a8deca50c90f46f4d79c6b40b805f135754
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225223"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="53f2a-102">Uživatelem definovaný typ GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="53f2a-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="53f2a-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="53f2a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="53f2a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="53f2a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="53f2a-105">Představuje kolekci `GeneratorIndex` ES.</span><span class="sxs-lookup"><span data-stu-id="53f2a-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="53f2a-106">Procházíme přes tuto kolekci s použitím jednoho indexu celé číslo a velikost kolekce se předpokládá jako známá.</span><span class="sxs-lookup"><span data-stu-id="53f2a-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="53f2a-107">Poznámky</span><span class="sxs-lookup"><span data-stu-id="53f2a-107">Remarks</span></span>

<span data-ttu-id="53f2a-108">Instance `GeneratorSystem` lze snadno definovat pomocí <xref:microsoft.quantum.arrays.lookupfunction> funkce.</span><span class="sxs-lookup"><span data-stu-id="53f2a-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="53f2a-109">Viz také</span><span class="sxs-lookup"><span data-stu-id="53f2a-109">See Also</span></span>

- [<span data-ttu-id="53f2a-110">Microsoft. Forms. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="53f2a-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)