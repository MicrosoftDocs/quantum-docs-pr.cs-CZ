---
uid: Microsoft.Quantum.Arrays.Filtered
title: Filtrovaná funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 83336b7001ce1d8ab1f5340b194abdcf93588c31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847166"
---
# <a name="filtered-function"></a><span data-ttu-id="cdbc8-102">Filtrovaná funkce</span><span class="sxs-lookup"><span data-stu-id="cdbc8-102">Filtered function</span></span>

<span data-ttu-id="cdbc8-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="cdbc8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="cdbc8-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cdbc8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cdbc8-105">Předané pole a predikát, který je definován pro prvky pole, vrátí pole, které se skládá z prvků, které odpovídají predikátu.</span><span class="sxs-lookup"><span data-stu-id="cdbc8-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="cdbc8-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="cdbc8-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="cdbc8-107">predikát: t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cdbc8-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cdbc8-108">Funkce z `'T` na logickou hodnotu, která slouží k filtrování prvků.</span><span class="sxs-lookup"><span data-stu-id="cdbc8-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="cdbc8-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="cdbc8-109">array : 'T[]</span></span>

<span data-ttu-id="cdbc8-110">Pole prvků nad `'T` .</span><span class="sxs-lookup"><span data-stu-id="cdbc8-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="cdbc8-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="cdbc8-111">Output : 'T[]</span></span>

<span data-ttu-id="cdbc8-112">Pole `'T[]` prvků, které odpovídají predikátu.</span><span class="sxs-lookup"><span data-stu-id="cdbc8-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cdbc8-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="cdbc8-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cdbc8-114">'S</span><span class="sxs-lookup"><span data-stu-id="cdbc8-114">'T</span></span>

<span data-ttu-id="cdbc8-115">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="cdbc8-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="cdbc8-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="cdbc8-116">Example</span></span>

<span data-ttu-id="cdbc8-117">Následující kód demonstruje funkci "Filtered".</span><span class="sxs-lookup"><span data-stu-id="cdbc8-117">The following code demonstrates the "Filtered" function.</span></span>
<span data-ttu-id="cdbc8-118">Predikát je definován pomocí @"microsoft.quantum.logical.greaterthani" funkce:</span><span class="sxs-lookup"><span data-stu-id="cdbc8-118">A predicate is defined using the @"microsoft.quantum.logical.greaterthani" function:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function FilteredDemo() : Unit {
   let predicate = GreaterThanI(_, 5);
   let filteredArray = Filtered(predicate, [2, 5, 9, 1, 8]);
   Message($"{filteredArray}");
}
```

<span data-ttu-id="cdbc8-119">Výsledek, který by měl být z tohoto příkladu očekáván, bude pole čísel větší než 5.</span><span class="sxs-lookup"><span data-stu-id="cdbc8-119">The outcome one should expect from this example will be an array of numbers greater than 5.</span></span>

## <a name="remarks"></a><span data-ttu-id="cdbc8-120">Poznámky</span><span class="sxs-lookup"><span data-stu-id="cdbc8-120">Remarks</span></span>

<span data-ttu-id="cdbc8-121">Funkce je definována pro obecné typy, tj., kdykoli máme pole `'T[]` a predikát `'T -> Bool` můžeme filtrovat prvky.</span><span class="sxs-lookup"><span data-stu-id="cdbc8-121">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>