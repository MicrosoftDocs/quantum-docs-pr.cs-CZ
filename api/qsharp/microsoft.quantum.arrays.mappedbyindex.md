---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 584cabcb7b6059ae5d311f13f5f75bd1f87bdba5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845671"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="09270-102">MappedByIndex – funkce</span><span class="sxs-lookup"><span data-stu-id="09270-102">MappedByIndex function</span></span>

<span data-ttu-id="09270-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="09270-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="09270-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="09270-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="09270-105">Pro pole a funkci, která je definována pro indexované prvky pole, vrátí nové pole, které se skládá z obrázků původního pole v rámci funkce.</span><span class="sxs-lookup"><span data-stu-id="09270-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="09270-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="09270-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="09270-107">Mapper: ([int](xref:microsoft.quantum.lang-ref.int), t)-> ' U</span><span class="sxs-lookup"><span data-stu-id="09270-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="09270-108">Funkce z `(Int, 'T)` `'U` , která se používá k mapování prvků a jejich indexů.</span><span class="sxs-lookup"><span data-stu-id="09270-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="09270-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="09270-109">array : 'T[]</span></span>

<span data-ttu-id="09270-110">Pole prvků nad `'T` .</span><span class="sxs-lookup"><span data-stu-id="09270-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="09270-111">Výstup: U []</span><span class="sxs-lookup"><span data-stu-id="09270-111">Output : 'U[]</span></span>

<span data-ttu-id="09270-112">Pole `'U[]` prvků, které jsou mapovány `mapper` funkcí.</span><span class="sxs-lookup"><span data-stu-id="09270-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="09270-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="09270-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="09270-114">'S</span><span class="sxs-lookup"><span data-stu-id="09270-114">'T</span></span>

<span data-ttu-id="09270-115">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="09270-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="09270-116">U</span><span class="sxs-lookup"><span data-stu-id="09270-116">'U</span></span>

<span data-ttu-id="09270-117">Typ výsledku `mapper` funkce</span><span class="sxs-lookup"><span data-stu-id="09270-117">The result type of the `mapper` function.</span></span>

## <a name="example"></a><span data-ttu-id="09270-118">Příklad</span><span class="sxs-lookup"><span data-stu-id="09270-118">Example</span></span>

<span data-ttu-id="09270-119">Následující dva řádky jsou ekvivalentní:</span><span class="sxs-lookup"><span data-stu-id="09270-119">The following two lines are equivalent:</span></span>

```qsharp
let arr = MapIndex(f, [x0, x1, x2]);
```

<span data-ttu-id="09270-120">a</span><span class="sxs-lookup"><span data-stu-id="09270-120">and</span></span>

```qsharp
let arr = [f(0, x0), f(1, x1), f(2, x2)];
```

## <a name="see-also"></a><span data-ttu-id="09270-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="09270-121">See Also</span></span>

- [<span data-ttu-id="09270-122">Microsoft. Forms. Arrays. mapované</span><span class="sxs-lookup"><span data-stu-id="09270-122">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)