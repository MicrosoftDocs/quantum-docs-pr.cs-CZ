---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: Uživatelem definovaný typ GeneratorSystem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 3748d3fb79597fb526c86a91bc28290155189014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858412"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="17788-102">Uživatelem definovaný typ GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="17788-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="17788-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="17788-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="17788-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="17788-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="17788-105">Představuje kolekci `GeneratorIndex` ES.</span><span class="sxs-lookup"><span data-stu-id="17788-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="17788-106">Procházíme přes tuto kolekci s použitím jednoho indexu celé číslo a velikost kolekce se předpokládá jako známá.</span><span class="sxs-lookup"><span data-stu-id="17788-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="17788-107">Poznámky</span><span class="sxs-lookup"><span data-stu-id="17788-107">Remarks</span></span>

<span data-ttu-id="17788-108">Instance `GeneratorSystem` lze snadno definovat pomocí <xref:microsoft.quantum.arrays.lookupfunction> funkce.</span><span class="sxs-lookup"><span data-stu-id="17788-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="17788-109">Viz také</span><span class="sxs-lookup"><span data-stu-id="17788-109">See Also</span></span>

- [<span data-ttu-id="17788-110">Microsoft. Forms. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="17788-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)