---
uid: Microsoft.Quantum.Arrays.Subarray
title: Subarray – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: cf72f04421b277ce64354d1eccec11cbc61d78cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220157"
---
# <a name="subarray-function"></a><span data-ttu-id="f07d9-102">Subarray – funkce</span><span class="sxs-lookup"><span data-stu-id="f07d9-102">Subarray function</span></span>

<span data-ttu-id="f07d9-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f07d9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f07d9-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f07d9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f07d9-105">Převezme pole a seznam umístění a vytvoří nové pole vytvořené z prvků původního pole, které odpovídá zadaným umístěním.</span><span class="sxs-lookup"><span data-stu-id="f07d9-105">Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.</span></span>

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="f07d9-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f07d9-106">Input</span></span>

### <a name="indices--int"></a><span data-ttu-id="f07d9-107">indexy: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f07d9-107">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f07d9-108">Seznam celých čísel, která se používají k definování podpole.</span><span class="sxs-lookup"><span data-stu-id="f07d9-108">A list of integers that is used to define the subarray.</span></span>


### <a name="array--t"></a><span data-ttu-id="f07d9-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="f07d9-109">array : 'T[]</span></span>

<span data-ttu-id="f07d9-110">Pole prvků nad `'T` .</span><span class="sxs-lookup"><span data-stu-id="f07d9-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="f07d9-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="f07d9-111">Output : 'T[]</span></span>

<span data-ttu-id="f07d9-112">Pole `out` prvků, jejichž indexy odpovídají podpoli, například `out[idx] == array[indices[idx]]` .</span><span class="sxs-lookup"><span data-stu-id="f07d9-112">An array `out` of elements whose indices correspond to the subarray, such that `out[idx] == array[indices[idx]]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f07d9-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f07d9-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f07d9-114">'S</span><span class="sxs-lookup"><span data-stu-id="f07d9-114">'T</span></span>

<span data-ttu-id="f07d9-115">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="f07d9-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="f07d9-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f07d9-116">Remarks</span></span>

<span data-ttu-id="f07d9-117">Funkce je definována pro obecné typy, tj., kdykoli máme pole `'T[]` a seznam umístění, které `Int[]` definují podpole.</span><span class="sxs-lookup"><span data-stu-id="f07d9-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a list of locations `Int[]` defining the subarray.</span></span>
<span data-ttu-id="f07d9-118">Konstrukce podpole je založena na generování nové, hluboké kopie daného pole na rozdíl od udržování odkazů.</span><span class="sxs-lookup"><span data-stu-id="f07d9-118">The construction of the subarray is a based on generating a new, deep copy of the given array as opposed to maintaining references.</span></span>

<span data-ttu-id="f07d9-119">Pokud `Length(indices) < Length(array)` , tato funkce vrátí podmnožinu `array` .</span><span class="sxs-lookup"><span data-stu-id="f07d9-119">If `Length(indices) < Length(array)`, this function will return a subset of `array`.</span></span> <span data-ttu-id="f07d9-120">Na druhé straně, pokud `indices` obsahuje opakující se prvky, odpovídající prvky `array` se také opakují.</span><span class="sxs-lookup"><span data-stu-id="f07d9-120">On the other hand, if `indices` contains repeated elements, the corresponding elements of `array` will likewise be repeated.</span></span>
<span data-ttu-id="f07d9-121">Pokud `indices` a `array` mají stejnou délku, tato funkce poskytuje permutace `array` .</span><span class="sxs-lookup"><span data-stu-id="f07d9-121">If `indices` and `array` are the same length, this function provides permutations of `array`.</span></span>