---
uid: Microsoft.Quantum.Arrays.All
title: All – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 17e61ea161b90fe089b7df7c10188d604d72dcfa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842898"
---
# <a name="all-function"></a><span data-ttu-id="9041b-102">All – funkce</span><span class="sxs-lookup"><span data-stu-id="9041b-102">All function</span></span>

<span data-ttu-id="9041b-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9041b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9041b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9041b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9041b-105">Předané pole a predikát, který je definován pro prvky pole a kontroluje, zda všechny prvky pole odpovídají predikátu.</span><span class="sxs-lookup"><span data-stu-id="9041b-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="9041b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="9041b-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="9041b-107">predikát: t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9041b-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9041b-108">Funkce z `'T` `Bool` , která se používá ke kontrole prvků.</span><span class="sxs-lookup"><span data-stu-id="9041b-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="9041b-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="9041b-109">array : 'T[]</span></span>

<span data-ttu-id="9041b-110">Pole prvků nad `'T` .</span><span class="sxs-lookup"><span data-stu-id="9041b-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="9041b-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9041b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9041b-112">`Bool`Hodnota funkce a predikátu použité pro všechny elementy.</span><span class="sxs-lookup"><span data-stu-id="9041b-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9041b-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="9041b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9041b-114">'S</span><span class="sxs-lookup"><span data-stu-id="9041b-114">'T</span></span>

<span data-ttu-id="9041b-115">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="9041b-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="9041b-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="9041b-116">Example</span></span>

<span data-ttu-id="9041b-117">Následující kód kontroluje, zda jsou všechny prvky pole nenulové:</span><span class="sxs-lookup"><span data-stu-id="9041b-117">The following code checks whether all elements of the array are non-zero:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function AllDemo() : Unit {
    let predicate = NotEqualI(_, 0);
    let isNonZero = All(predicate, [2, 3, 4, 5, 6, 0]);
    Message($"{isNonZero}");
}
```

## <a name="remarks"></a><span data-ttu-id="9041b-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="9041b-118">Remarks</span></span>

<span data-ttu-id="9041b-119">Funkce je definována pro obecné typy, tj., kdykoli máme pole `'T[]` a funkci, `predicate: 'T -> Bool` můžeme vytvořit `Bool` hodnotu, která označuje, zda všechny prvky vyhoví `predicate` .</span><span class="sxs-lookup"><span data-stu-id="9041b-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>