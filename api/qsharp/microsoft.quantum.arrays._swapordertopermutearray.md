---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 9df2ec00d91c1124fae960efd15d576b15b0223c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221704"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="615b0-102">_SwapOrderToPermuteArray funkce</span><span class="sxs-lookup"><span data-stu-id="615b0-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="615b0-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="615b0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="615b0-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="615b0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="615b0-105">Vrátí prvky Order v poli musí být zaměněny, aby vytvořilo seřazené pole.</span><span class="sxs-lookup"><span data-stu-id="615b0-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="615b0-106">Předpokládá, že probíhají zahození.</span><span class="sxs-lookup"><span data-stu-id="615b0-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="615b0-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="615b0-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="615b0-108">newOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="615b0-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="615b0-109">Pole s permutací indexů nového pole.</span><span class="sxs-lookup"><span data-stu-id="615b0-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="615b0-110">Mělo by se jednat o $n $ prvky, přičemž každý z nich bude mít jedinečné celé číslo od $0 $ do $n-$1.</span><span class="sxs-lookup"><span data-stu-id="615b0-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="615b0-111">Výstup: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="615b0-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="615b0-112">Řazená kolekce členů představuje dva indexy, které se mají prohodit.</span><span class="sxs-lookup"><span data-stu-id="615b0-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="615b0-113">Zahození začíná na nejnižším indexu.</span><span class="sxs-lookup"><span data-stu-id="615b0-113">The swaps begin at the lowest index.</span></span>

## <a name="remarks"></a><span data-ttu-id="615b0-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="615b0-114">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="615b0-115">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="615b0-115">Psuedocode</span></span>

<span data-ttu-id="615b0-116">for (Indexing 0.. Length (newOrder)-1) {while [index]! = index {Switch newOrder [index] with newOrder [newOrder [index]]}}</span><span class="sxs-lookup"><span data-stu-id="615b0-116">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>