---
uid: Microsoft.Quantum.Arrays.Mapped
title: Mapovaná funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 00ea0803faf6e8edfa748af63dd6c7e217b1de41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845674"
---
# <a name="mapped-function"></a><span data-ttu-id="a3d7d-102">Mapovaná funkce</span><span class="sxs-lookup"><span data-stu-id="a3d7d-102">Mapped function</span></span>

<span data-ttu-id="a3d7d-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a3d7d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a3d7d-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a3d7d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a3d7d-105">Předané pole a funkce, které jsou definovány pro prvky pole, vrátí nové pole, které se skládá z obrázků původního pole pod funkcí.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-105">Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="a3d7d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="a3d7d-106">Input</span></span>

### <a name="mapper--t---u"></a><span data-ttu-id="a3d7d-107">Mapper: t-> ' U</span><span class="sxs-lookup"><span data-stu-id="a3d7d-107">mapper : 'T -> 'U</span></span>

<span data-ttu-id="a3d7d-108">Funkce z `'T` `'U` , která se používá k mapování prvků.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-108">A function from `'T` to `'U` that is used to map elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="a3d7d-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="a3d7d-109">array : 'T[]</span></span>

<span data-ttu-id="a3d7d-110">Pole prvků nad `'T` .</span><span class="sxs-lookup"><span data-stu-id="a3d7d-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="a3d7d-111">Výstup: U []</span><span class="sxs-lookup"><span data-stu-id="a3d7d-111">Output : 'U[]</span></span>

<span data-ttu-id="a3d7d-112">Pole `'U[]` prvků, které jsou mapovány `mapper` funkcí.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a3d7d-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a3d7d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a3d7d-114">'S</span><span class="sxs-lookup"><span data-stu-id="a3d7d-114">'T</span></span>

<span data-ttu-id="a3d7d-115">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="a3d7d-116">U</span><span class="sxs-lookup"><span data-stu-id="a3d7d-116">'U</span></span>

<span data-ttu-id="a3d7d-117">Typ výsledku `mapper` funkce</span><span class="sxs-lookup"><span data-stu-id="a3d7d-117">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="a3d7d-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="a3d7d-118">Remarks</span></span>

<span data-ttu-id="a3d7d-119">Funkce je definována pro obecné typy, tj., kdykoli máme pole `'T[]` a funkci, `mapper: 'T -> 'U` můžeme namapovat prvky pole a vytvořit nové pole typu `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="a3d7d-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `mapper: 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>