---
uid: Microsoft.Quantum.Arrays.ForEach
title: Operace ForEach
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: b362d28e77c8dea2b3daeed4a4d605e1dd42e487
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221143"
---
# <a name="foreach-operation"></a><span data-ttu-id="6acc4-102">Operace ForEach</span><span class="sxs-lookup"><span data-stu-id="6acc4-102">ForEach operation</span></span>

<span data-ttu-id="6acc4-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6acc4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6acc4-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6acc4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6acc4-105">Předané pole a operace, která je definována pro prvky pole, vrátí nové pole, které se skládá z obrázků původního pole v rámci operace.</span><span class="sxs-lookup"><span data-stu-id="6acc4-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="6acc4-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="6acc4-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="6acc4-107">Action: t => ' U</span><span class="sxs-lookup"><span data-stu-id="6acc4-107">action : 'T => 'U</span></span> 

<span data-ttu-id="6acc4-108">Operace z `'T` na `'U` , která je použita na každý prvek.</span><span class="sxs-lookup"><span data-stu-id="6acc4-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="6acc4-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="6acc4-109">array : 'T[]</span></span>

<span data-ttu-id="6acc4-110">Pole prvků nad `'T` .</span><span class="sxs-lookup"><span data-stu-id="6acc4-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="6acc4-111">Výstup: U []</span><span class="sxs-lookup"><span data-stu-id="6acc4-111">Output : 'U[]</span></span>

<span data-ttu-id="6acc4-112">Pole `'U[]` prvků, které jsou mapovány `action` operací.</span><span class="sxs-lookup"><span data-stu-id="6acc4-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6acc4-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="6acc4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6acc4-114">'S</span><span class="sxs-lookup"><span data-stu-id="6acc4-114">'T</span></span>

<span data-ttu-id="6acc4-115">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="6acc4-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="6acc4-116">U</span><span class="sxs-lookup"><span data-stu-id="6acc4-116">'U</span></span>

<span data-ttu-id="6acc4-117">Typ výsledku `action` operace.</span><span class="sxs-lookup"><span data-stu-id="6acc4-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="6acc4-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="6acc4-118">Remarks</span></span>

<span data-ttu-id="6acc4-119">Operace je definována pro obecné typy, tj. kdykoli máme pole `'T[]` a operaci, `action : 'T -> 'U` můžeme namapovat prvky pole a vytvořit nové pole typu `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="6acc4-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>