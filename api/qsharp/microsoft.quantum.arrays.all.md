---
uid: Microsoft.Quantum.Arrays.All
title: All – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: a7c83e38c3c101b712215eb664486fe29863a52b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221687"
---
# <a name="all-function"></a><span data-ttu-id="8ad29-102">All – funkce</span><span class="sxs-lookup"><span data-stu-id="8ad29-102">All function</span></span>

<span data-ttu-id="8ad29-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8ad29-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8ad29-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ad29-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8ad29-105">Předané pole a predikát, který je definován pro prvky pole a kontroluje, zda všechny prvky pole odpovídají predikátu.</span><span class="sxs-lookup"><span data-stu-id="8ad29-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="8ad29-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="8ad29-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="8ad29-107">predikát: t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8ad29-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8ad29-108">Funkce z `'T` `Bool` , která se používá ke kontrole prvků.</span><span class="sxs-lookup"><span data-stu-id="8ad29-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="8ad29-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="8ad29-109">array : 'T[]</span></span>

<span data-ttu-id="8ad29-110">Pole prvků nad `'T` .</span><span class="sxs-lookup"><span data-stu-id="8ad29-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="8ad29-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8ad29-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8ad29-112">`Bool`Hodnota funkce a predikátu použité pro všechny elementy.</span><span class="sxs-lookup"><span data-stu-id="8ad29-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8ad29-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8ad29-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8ad29-114">'S</span><span class="sxs-lookup"><span data-stu-id="8ad29-114">'T</span></span>

<span data-ttu-id="8ad29-115">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="8ad29-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="8ad29-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="8ad29-116">Remarks</span></span>

<span data-ttu-id="8ad29-117">Funkce je definována pro obecné typy, tj., kdykoli máme pole `'T[]` a funkci, `predicate: 'T -> Bool` můžeme vytvořit `Bool` hodnotu, která označuje, zda všechny prvky vyhoví `predicate` .</span><span class="sxs-lookup"><span data-stu-id="8ad29-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>