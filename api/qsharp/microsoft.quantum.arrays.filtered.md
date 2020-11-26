---
uid: Microsoft.Quantum.Arrays.Filtered
title: Filtrovaná funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: fa8600f4d773daf6eabf8b9961ab46961155d1fd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221262"
---
# <a name="filtered-function"></a><span data-ttu-id="820e6-102">Filtrovaná funkce</span><span class="sxs-lookup"><span data-stu-id="820e6-102">Filtered function</span></span>

<span data-ttu-id="820e6-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="820e6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="820e6-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="820e6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="820e6-105">Předané pole a predikát, který je definován pro prvky pole, vrátí pole, které se skládá z prvků, které odpovídají predikátu.</span><span class="sxs-lookup"><span data-stu-id="820e6-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="820e6-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="820e6-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="820e6-107">predikát: t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="820e6-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="820e6-108">Funkce z `'T` na logickou hodnotu, která slouží k filtrování prvků.</span><span class="sxs-lookup"><span data-stu-id="820e6-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="820e6-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="820e6-109">array : 'T[]</span></span>

<span data-ttu-id="820e6-110">Pole prvků nad `'T` .</span><span class="sxs-lookup"><span data-stu-id="820e6-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="820e6-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="820e6-111">Output : 'T[]</span></span>

<span data-ttu-id="820e6-112">Pole `'T[]` prvků, které odpovídají predikátu.</span><span class="sxs-lookup"><span data-stu-id="820e6-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="820e6-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="820e6-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="820e6-114">'S</span><span class="sxs-lookup"><span data-stu-id="820e6-114">'T</span></span>

<span data-ttu-id="820e6-115">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="820e6-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="820e6-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="820e6-116">Remarks</span></span>

<span data-ttu-id="820e6-117">Funkce je definována pro obecné typy, tj., kdykoli máme pole `'T[]` a predikát `'T -> Bool` můžeme filtrovat prvky.</span><span class="sxs-lookup"><span data-stu-id="820e6-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>