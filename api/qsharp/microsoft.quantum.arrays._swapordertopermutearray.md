---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: ff8e4e23dde7d69f93054a275548ded49d5b0bfb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846299"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="7fd73-102">_SwapOrderToPermuteArray funkce</span><span class="sxs-lookup"><span data-stu-id="7fd73-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="7fd73-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7fd73-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7fd73-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7fd73-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7fd73-105">Vrátí prvky Order v poli musí být zaměněny, aby vytvořilo seřazené pole.</span><span class="sxs-lookup"><span data-stu-id="7fd73-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="7fd73-106">Předpokládá, že probíhají zahození.</span><span class="sxs-lookup"><span data-stu-id="7fd73-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="7fd73-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="7fd73-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="7fd73-108">newOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7fd73-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7fd73-109">Pole s permutací indexů nového pole.</span><span class="sxs-lookup"><span data-stu-id="7fd73-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="7fd73-110">Mělo by se jednat o $n $ prvky, přičemž každý z nich bude mít jedinečné celé číslo od $0 $ do $n-$1.</span><span class="sxs-lookup"><span data-stu-id="7fd73-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="7fd73-111">Výstup: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="7fd73-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="7fd73-112">Řazená kolekce členů představuje dva indexy, které se mají prohodit.</span><span class="sxs-lookup"><span data-stu-id="7fd73-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="7fd73-113">Zahození začíná na nejnižším indexu.</span><span class="sxs-lookup"><span data-stu-id="7fd73-113">The swaps begin at the lowest index.</span></span>

## <a name="example"></a><span data-ttu-id="7fd73-114">Příklad</span><span class="sxs-lookup"><span data-stu-id="7fd73-114">Example</span></span>

```qsharp
// The following returns [(0, 5),(0, 4),(0, 1),(0, 3)];
let swapOrder = _SwapOrderToPermuteArray([5, 3, 2, 0, 1, 4]);
```

## <a name="remarks"></a><span data-ttu-id="7fd73-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="7fd73-115">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="7fd73-116">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="7fd73-116">Psuedocode</span></span>

<span data-ttu-id="7fd73-117">for (Indexing 0.. Length (newOrder)-1) {while [index]! = index {Switch newOrder [index] with newOrder [newOrder [index]]}}</span><span class="sxs-lookup"><span data-stu-id="7fd73-117">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>