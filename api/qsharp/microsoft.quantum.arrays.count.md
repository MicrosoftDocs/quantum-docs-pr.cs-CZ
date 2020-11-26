---
uid: Microsoft.Quantum.Arrays.Count
title: Count – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 48b75cc6d6584f899223a0803f31fd174836f303
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221551"
---
# <a name="count-function"></a><span data-ttu-id="ad108-102">Count – funkce</span><span class="sxs-lookup"><span data-stu-id="ad108-102">Count function</span></span>

<span data-ttu-id="ad108-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ad108-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ad108-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ad108-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ad108-105">Předané pole a predikát, který je definován pro prvky pole, vrátí počet prvků pole, které se skládá z prvků, které odpovídají predikátu.</span><span class="sxs-lookup"><span data-stu-id="ad108-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="ad108-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ad108-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="ad108-107">predikát: t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ad108-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ad108-108">Funkce z `'T` na logickou hodnotu, která slouží k filtrování prvků.</span><span class="sxs-lookup"><span data-stu-id="ad108-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="ad108-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="ad108-109">array : 'T[]</span></span>

<span data-ttu-id="ad108-110">Pole prvků nad `'T` .</span><span class="sxs-lookup"><span data-stu-id="ad108-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="ad108-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ad108-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ad108-112">Počet prvků v `array` , které odpovídají predikátu.</span><span class="sxs-lookup"><span data-stu-id="ad108-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ad108-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ad108-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ad108-114">'S</span><span class="sxs-lookup"><span data-stu-id="ad108-114">'T</span></span>

<span data-ttu-id="ad108-115">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="ad108-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="ad108-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ad108-116">Remarks</span></span>

<span data-ttu-id="ad108-117">Funkce je definována pro obecné typy, tj., kdykoli máme pole `'T[]` a predikát `'T -> Bool` můžeme filtrovat prvky.</span><span class="sxs-lookup"><span data-stu-id="ad108-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>