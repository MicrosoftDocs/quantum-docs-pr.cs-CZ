---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 965f2f3d4f8b366abb27287ce0d27a3b7d7b8fb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706192"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="f69a1-102">_SwapOrderToPermuteArray funkce</span><span class="sxs-lookup"><span data-stu-id="f69a1-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="f69a1-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f69a1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f69a1-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f69a1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f69a1-105">Vrátí prvky Order v poli musí být zaměněny, aby vytvořilo seřazené pole.</span><span class="sxs-lookup"><span data-stu-id="f69a1-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="f69a1-106">Předpokládá, že probíhají zahození.</span><span class="sxs-lookup"><span data-stu-id="f69a1-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="f69a1-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="f69a1-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="f69a1-108">newOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f69a1-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f69a1-109">Pole s permutací indexů nového pole.</span><span class="sxs-lookup"><span data-stu-id="f69a1-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="f69a1-110">Mělo by se jednat o $n $ prvky, přičemž každý z nich bude mít jedinečné celé číslo od $0 $ do $n-$1.</span><span class="sxs-lookup"><span data-stu-id="f69a1-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="f69a1-111">Výstup: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="f69a1-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="f69a1-112">Řazená kolekce členů představuje dva indexy, které se mají prohodit.</span><span class="sxs-lookup"><span data-stu-id="f69a1-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="f69a1-113">Zahození začíná na nejnižším indexu.</span><span class="sxs-lookup"><span data-stu-id="f69a1-113">The swaps begin at the lowest index.</span></span>

## <a name="remarks"></a><span data-ttu-id="f69a1-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f69a1-114">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="f69a1-115">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="f69a1-115">Psuedocode</span></span>

<span data-ttu-id="f69a1-116">for (Indexing 0.. Length (newOrder)-1) {while [index]! = index {Switch newOrder [index] with newOrder [newOrder [index]]}}</span><span class="sxs-lookup"><span data-stu-id="f69a1-116">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>