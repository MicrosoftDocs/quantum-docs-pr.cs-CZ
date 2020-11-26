---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 430495517974b641c249fa146aa9effec542e825
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209923"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="c2cbc-102">MappedByIndex – funkce</span><span class="sxs-lookup"><span data-stu-id="c2cbc-102">MappedByIndex function</span></span>

<span data-ttu-id="c2cbc-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c2cbc-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c2cbc-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c2cbc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c2cbc-105">Pro pole a funkci, která je definována pro indexované prvky pole, vrátí nové pole, které se skládá z obrázků původního pole v rámci funkce.</span><span class="sxs-lookup"><span data-stu-id="c2cbc-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="c2cbc-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c2cbc-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="c2cbc-107">Mapper: ([int](xref:microsoft.quantum.lang-ref.int), t)-> ' U</span><span class="sxs-lookup"><span data-stu-id="c2cbc-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="c2cbc-108">Funkce z `(Int, 'T)` `'U` , která se používá k mapování prvků a jejich indexů.</span><span class="sxs-lookup"><span data-stu-id="c2cbc-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="c2cbc-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="c2cbc-109">array : 'T[]</span></span>

<span data-ttu-id="c2cbc-110">Pole prvků nad `'T` .</span><span class="sxs-lookup"><span data-stu-id="c2cbc-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="c2cbc-111">Výstup: U []</span><span class="sxs-lookup"><span data-stu-id="c2cbc-111">Output : 'U[]</span></span>

<span data-ttu-id="c2cbc-112">Pole `'U[]` prvků, které jsou mapovány `mapper` funkcí.</span><span class="sxs-lookup"><span data-stu-id="c2cbc-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c2cbc-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c2cbc-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c2cbc-114">'S</span><span class="sxs-lookup"><span data-stu-id="c2cbc-114">'T</span></span>

<span data-ttu-id="c2cbc-115">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="c2cbc-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="c2cbc-116">U</span><span class="sxs-lookup"><span data-stu-id="c2cbc-116">'U</span></span>

<span data-ttu-id="c2cbc-117">Typ výsledku `mapper` funkce</span><span class="sxs-lookup"><span data-stu-id="c2cbc-117">The result type of the `mapper` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2cbc-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="c2cbc-118">See Also</span></span>

- [<span data-ttu-id="c2cbc-119">Microsoft. Forms. Arrays. mapované</span><span class="sxs-lookup"><span data-stu-id="c2cbc-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)