---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: 7093043e2a290e6132774b8fe154d3627a254f27
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845641"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="a8fe5-102">MappedOverRange – funkce</span><span class="sxs-lookup"><span data-stu-id="a8fe5-102">MappedOverRange function</span></span>

<span data-ttu-id="a8fe5-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a8fe5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a8fe5-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a8fe5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a8fe5-105">Pro rozsah a funkci, která přijímá jako vstup celé číslo, vrátí nové pole, které se skládá z obrázků hodnot rozsahu pod funkcí.</span><span class="sxs-lookup"><span data-stu-id="a8fe5-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="a8fe5-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="a8fe5-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="a8fe5-107">Mapovač: [int](xref:microsoft.quantum.lang-ref.int) -> 't</span><span class="sxs-lookup"><span data-stu-id="a8fe5-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="a8fe5-108">Funkce z `Int` `'T` , která se používá k mapování hodnot rozsahu.</span><span class="sxs-lookup"><span data-stu-id="a8fe5-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="a8fe5-109">Rozsah: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="a8fe5-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="a8fe5-110">Rozsah celých čísel.</span><span class="sxs-lookup"><span data-stu-id="a8fe5-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="a8fe5-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="a8fe5-111">Output : 'T[]</span></span>

<span data-ttu-id="a8fe5-112">Pole `'T[]` prvků, které jsou mapovány `mapper` funkcí.</span><span class="sxs-lookup"><span data-stu-id="a8fe5-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a8fe5-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a8fe5-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a8fe5-114">'S</span><span class="sxs-lookup"><span data-stu-id="a8fe5-114">'T</span></span>

<span data-ttu-id="a8fe5-115">Typ výsledku `mapper` funkce</span><span class="sxs-lookup"><span data-stu-id="a8fe5-115">The result type of the `mapper` function.</span></span>

## <a name="example"></a><span data-ttu-id="a8fe5-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="a8fe5-116">Example</span></span>

<span data-ttu-id="a8fe5-117">Tento příklad přidá 1 do rozsahu sudých čísel:</span><span class="sxs-lookup"><span data-stu-id="a8fe5-117">This example adds 1 to a range of even numbers:</span></span>

```qsharp
let numbers = MappedOverRange(PlusI(1, _), 0..2..10);
// numbers = [1, 3, 5, 7, 9, 11]
```

## <a name="remarks"></a><span data-ttu-id="a8fe5-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="a8fe5-118">Remarks</span></span>

<span data-ttu-id="a8fe5-119">Funkce je definována pro obecné typy, tj. kdykoli máme funkci, `mapper: Int -> 'T` můžeme namapovat hodnoty rozsahu a vytvořit pole typu `'T[]` .</span><span class="sxs-lookup"><span data-stu-id="a8fe5-119">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8fe5-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="a8fe5-120">See Also</span></span>

- [<span data-ttu-id="a8fe5-121">Microsoft. Forms. Arrays. mapované</span><span class="sxs-lookup"><span data-stu-id="a8fe5-121">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)