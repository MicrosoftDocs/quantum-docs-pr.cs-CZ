---
uid: Microsoft.Quantum.Arrays.Count
title: Count – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: e178ee63526e3485e8cc83a3ba8f827d8ecac552
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842840"
---
# <a name="count-function"></a><span data-ttu-id="433ae-102">Count – funkce</span><span class="sxs-lookup"><span data-stu-id="433ae-102">Count function</span></span>

<span data-ttu-id="433ae-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="433ae-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="433ae-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="433ae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="433ae-105">Předané pole a predikát, který je definován pro prvky pole, vrátí počet prvků pole, které se skládá z prvků, které odpovídají predikátu.</span><span class="sxs-lookup"><span data-stu-id="433ae-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="433ae-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="433ae-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="433ae-107">predikát: t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="433ae-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="433ae-108">Funkce z `'T` na logickou hodnotu, která slouží k filtrování prvků.</span><span class="sxs-lookup"><span data-stu-id="433ae-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="433ae-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="433ae-109">array : 'T[]</span></span>

<span data-ttu-id="433ae-110">Pole prvků nad `'T` .</span><span class="sxs-lookup"><span data-stu-id="433ae-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="433ae-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="433ae-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="433ae-112">Počet prvků v `array` , které odpovídají predikátu.</span><span class="sxs-lookup"><span data-stu-id="433ae-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="433ae-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="433ae-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="433ae-114">'S</span><span class="sxs-lookup"><span data-stu-id="433ae-114">'T</span></span>

<span data-ttu-id="433ae-115">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="433ae-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="433ae-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="433ae-116">Example</span></span>

<span data-ttu-id="433ae-117">Následující kód demonstruje funkci Count.</span><span class="sxs-lookup"><span data-stu-id="433ae-117">The following code demonstrates the "Count" function.</span></span>
<span data-ttu-id="433ae-118">Predikát je definován pomocí @"microsoft.quantum.logical.greaterthani" funkce:</span><span class="sxs-lookup"><span data-stu-id="433ae-118">A predicate is defined using the @"microsoft.quantum.logical.greaterthani" function:</span></span>

```qsharp
 let predicate = GreaterThanI(_, 5);
 let count = Count(predicate, [2, 5, 9, 1, 8]);
 // count = 2
```

## <a name="remarks"></a><span data-ttu-id="433ae-119">Poznámky</span><span class="sxs-lookup"><span data-stu-id="433ae-119">Remarks</span></span>

<span data-ttu-id="433ae-120">Funkce je definována pro obecné typy, tj., kdykoli máme pole `'T[]` a predikát `'T -> Bool` můžeme filtrovat prvky.</span><span class="sxs-lookup"><span data-stu-id="433ae-120">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>