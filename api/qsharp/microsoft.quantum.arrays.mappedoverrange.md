---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: b1d73c2503e63ed09a3d6a56421760ca29eb0c3f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220684"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="7fad6-102">MappedOverRange – funkce</span><span class="sxs-lookup"><span data-stu-id="7fad6-102">MappedOverRange function</span></span>

<span data-ttu-id="7fad6-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7fad6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7fad6-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7fad6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7fad6-105">Pro rozsah a funkci, která přijímá jako vstup celé číslo, vrátí nové pole, které se skládá z obrázků hodnot rozsahu pod funkcí.</span><span class="sxs-lookup"><span data-stu-id="7fad6-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="7fad6-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="7fad6-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="7fad6-107">Mapovač: [int](xref:microsoft.quantum.lang-ref.int) -> 't</span><span class="sxs-lookup"><span data-stu-id="7fad6-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="7fad6-108">Funkce z `Int` `'T` , která se používá k mapování hodnot rozsahu.</span><span class="sxs-lookup"><span data-stu-id="7fad6-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="7fad6-109">Rozsah: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="7fad6-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="7fad6-110">Rozsah celých čísel.</span><span class="sxs-lookup"><span data-stu-id="7fad6-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="7fad6-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="7fad6-111">Output : 'T[]</span></span>

<span data-ttu-id="7fad6-112">Pole `'T[]` prvků, které jsou mapovány `mapper` funkcí.</span><span class="sxs-lookup"><span data-stu-id="7fad6-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7fad6-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="7fad6-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7fad6-114">'S</span><span class="sxs-lookup"><span data-stu-id="7fad6-114">'T</span></span>

<span data-ttu-id="7fad6-115">Typ výsledku `mapper` funkce</span><span class="sxs-lookup"><span data-stu-id="7fad6-115">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="7fad6-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="7fad6-116">Remarks</span></span>

<span data-ttu-id="7fad6-117">Funkce je definována pro obecné typy, tj. kdykoli máme funkci, `mapper: Int -> 'T` můžeme namapovat hodnoty rozsahu a vytvořit pole typu `'T[]` .</span><span class="sxs-lookup"><span data-stu-id="7fad6-117">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="7fad6-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="7fad6-118">See Also</span></span>

- [<span data-ttu-id="7fad6-119">Microsoft. Forms. Arrays. mapované</span><span class="sxs-lookup"><span data-stu-id="7fad6-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)