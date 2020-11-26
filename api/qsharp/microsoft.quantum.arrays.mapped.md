---
uid: Microsoft.Quantum.Arrays.Mapped
title: Mapovaná funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 9632b9f53ffad8ece958ab1dc9ad446c7dcb9e13
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220735"
---
# <a name="mapped-function"></a><span data-ttu-id="2015a-102">Mapovaná funkce</span><span class="sxs-lookup"><span data-stu-id="2015a-102">Mapped function</span></span>

<span data-ttu-id="2015a-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2015a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2015a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2015a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2015a-105">Předané pole a funkce, které jsou definovány pro prvky pole, vrátí nové pole, které se skládá z obrázků původního pole pod funkcí.</span><span class="sxs-lookup"><span data-stu-id="2015a-105">Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="2015a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2015a-106">Input</span></span>

### <a name="mapper--t---u"></a><span data-ttu-id="2015a-107">Mapper: t-> ' U</span><span class="sxs-lookup"><span data-stu-id="2015a-107">mapper : 'T -> 'U</span></span>

<span data-ttu-id="2015a-108">Funkce z `'T` `'U` , která se používá k mapování prvků.</span><span class="sxs-lookup"><span data-stu-id="2015a-108">A function from `'T` to `'U` that is used to map elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="2015a-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="2015a-109">array : 'T[]</span></span>

<span data-ttu-id="2015a-110">Pole prvků nad `'T` .</span><span class="sxs-lookup"><span data-stu-id="2015a-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="2015a-111">Výstup: U []</span><span class="sxs-lookup"><span data-stu-id="2015a-111">Output : 'U[]</span></span>

<span data-ttu-id="2015a-112">Pole `'U[]` prvků, které jsou mapovány `mapper` funkcí.</span><span class="sxs-lookup"><span data-stu-id="2015a-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2015a-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="2015a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2015a-114">'S</span><span class="sxs-lookup"><span data-stu-id="2015a-114">'T</span></span>

<span data-ttu-id="2015a-115">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="2015a-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="2015a-116">U</span><span class="sxs-lookup"><span data-stu-id="2015a-116">'U</span></span>

<span data-ttu-id="2015a-117">Typ výsledku `mapper` funkce</span><span class="sxs-lookup"><span data-stu-id="2015a-117">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="2015a-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2015a-118">Remarks</span></span>

<span data-ttu-id="2015a-119">Funkce je definována pro obecné typy, tj., kdykoli máme pole `'T[]` a funkci, `mapper: 'T -> 'U` můžeme namapovat prvky pole a vytvořit nové pole typu `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="2015a-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `mapper: 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>