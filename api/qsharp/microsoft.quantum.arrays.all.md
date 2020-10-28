---
uid: Microsoft.Quantum.Arrays.All
title: All – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 345c3fb92babd4ae2e54803b6c3b79b3313ef417
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706184"
---
# <a name="all-function"></a><span data-ttu-id="361ff-102">All – funkce</span><span class="sxs-lookup"><span data-stu-id="361ff-102">All function</span></span>

<span data-ttu-id="361ff-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="361ff-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="361ff-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="361ff-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="361ff-105">Předané pole a predikát, který je definován pro prvky pole a kontroluje, zda všechny prvky pole odpovídají predikátu.</span><span class="sxs-lookup"><span data-stu-id="361ff-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="361ff-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="361ff-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="361ff-107">predikát: t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="361ff-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="361ff-108">Funkce z `'T` `Bool` , která se používá ke kontrole prvků.</span><span class="sxs-lookup"><span data-stu-id="361ff-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="361ff-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="361ff-109">array : 'T[]</span></span>

<span data-ttu-id="361ff-110">Pole prvků nad `'T` .</span><span class="sxs-lookup"><span data-stu-id="361ff-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="361ff-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="361ff-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="361ff-112">`Bool`Hodnota funkce a predikátu použité pro všechny elementy.</span><span class="sxs-lookup"><span data-stu-id="361ff-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="361ff-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="361ff-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="361ff-114">'S</span><span class="sxs-lookup"><span data-stu-id="361ff-114">'T</span></span>

<span data-ttu-id="361ff-115">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="361ff-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="361ff-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="361ff-116">Remarks</span></span>

<span data-ttu-id="361ff-117">Funkce je definována pro obecné typy, tj., kdykoli máme pole `'T[]` a funkci, `predicate: 'T -> Bool` můžeme vytvořit `Bool` hodnotu, která označuje, zda všechny prvky vyhoví `predicate` .</span><span class="sxs-lookup"><span data-stu-id="361ff-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>