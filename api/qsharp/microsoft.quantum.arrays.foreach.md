---
uid: Microsoft.Quantum.Arrays.ForEach
title: Operace ForEach
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: ab6ac6eb913095f31ba166ac27f034f2e2875acf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706000"
---
# <a name="foreach-operation"></a><span data-ttu-id="c50f3-102">Operace ForEach</span><span class="sxs-lookup"><span data-stu-id="c50f3-102">ForEach operation</span></span>

<span data-ttu-id="c50f3-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c50f3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c50f3-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c50f3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c50f3-105">Předané pole a operace, která je definována pro prvky pole, vrátí nové pole, které se skládá z obrázků původního pole v rámci operace.</span><span class="sxs-lookup"><span data-stu-id="c50f3-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="c50f3-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c50f3-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="c50f3-107">Action: t => ' U</span><span class="sxs-lookup"><span data-stu-id="c50f3-107">action : 'T => 'U</span></span> 

<span data-ttu-id="c50f3-108">Operace z `'T` na `'U` , která je použita na každý prvek.</span><span class="sxs-lookup"><span data-stu-id="c50f3-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="c50f3-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="c50f3-109">array : 'T[]</span></span>

<span data-ttu-id="c50f3-110">Pole prvků nad `'T` .</span><span class="sxs-lookup"><span data-stu-id="c50f3-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="c50f3-111">Výstup: U []</span><span class="sxs-lookup"><span data-stu-id="c50f3-111">Output : 'U[]</span></span>

<span data-ttu-id="c50f3-112">Pole `'U[]` prvků, které jsou mapovány `action` operací.</span><span class="sxs-lookup"><span data-stu-id="c50f3-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c50f3-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c50f3-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c50f3-114">'S</span><span class="sxs-lookup"><span data-stu-id="c50f3-114">'T</span></span>

<span data-ttu-id="c50f3-115">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="c50f3-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="c50f3-116">U</span><span class="sxs-lookup"><span data-stu-id="c50f3-116">'U</span></span>

<span data-ttu-id="c50f3-117">Typ výsledku `action` operace.</span><span class="sxs-lookup"><span data-stu-id="c50f3-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="c50f3-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c50f3-118">Remarks</span></span>

<span data-ttu-id="c50f3-119">Operace je definována pro obecné typy, tj. kdykoli máme pole `'T[]` a operaci, `action : 'T -> 'U` můžeme namapovat prvky pole a vytvořit nové pole typu `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="c50f3-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>