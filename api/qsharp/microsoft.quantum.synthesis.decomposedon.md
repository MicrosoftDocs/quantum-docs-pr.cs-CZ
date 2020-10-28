---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: b033723a50fb85e77c9d4baec1f94231327e9b25
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709172"
---
# <a name="decomposedon-function"></a><span data-ttu-id="e0c11-102">DecomposedOn – funkce</span><span class="sxs-lookup"><span data-stu-id="e0c11-102">DecomposedOn function</span></span>

<span data-ttu-id="e0c11-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="e0c11-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="e0c11-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e0c11-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e0c11-105">Vytvoří permutaci pro proměnnou.</span><span class="sxs-lookup"><span data-stu-id="e0c11-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="e0c11-106">Popis</span><span class="sxs-lookup"><span data-stu-id="e0c11-106">Description</span></span>

<span data-ttu-id="e0c11-107">Pokud je zadána permutace $ \pi $ ( `perm` ) a index $i $ ( `index` ), tato metoda vrátí tři permutace $ ((\ pi_l, \ pi_r), \pi ') $ tak, že obrázky $ \ pi_l $ a $ \ pi_r $ nemění bity v jejich prvcích v jiných rejstřících než $i $ a image $ \pi $ nemění bitovou $i $ ve svých prvcích.</span><span class="sxs-lookup"><span data-stu-id="e0c11-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="e0c11-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="e0c11-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="e0c11-109">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e0c11-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="e0c11-110">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e0c11-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="e0c11-111">Výstup: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="e0c11-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

