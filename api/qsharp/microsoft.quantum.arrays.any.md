---
uid: Microsoft.Quantum.Arrays.Any
title: Libovolná funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: a05f9531168bf2b32977665d38cc00f3c8e64879
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846268"
---
# <a name="any-function"></a><span data-ttu-id="df026-102">Libovolná funkce</span><span class="sxs-lookup"><span data-stu-id="df026-102">Any function</span></span>

<span data-ttu-id="df026-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="df026-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="df026-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="df026-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="df026-105">V případě pole a predikátu, který je definován pro prvky pole, zkontroluje, zda alespoň jeden prvek pole splňuje predikát.</span><span class="sxs-lookup"><span data-stu-id="df026-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="df026-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="df026-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="df026-107">predikát: t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="df026-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="df026-108">Funkce z `'T` `Bool` , která se používá ke kontrole prvků.</span><span class="sxs-lookup"><span data-stu-id="df026-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="df026-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="df026-109">array : 'T[]</span></span>

<span data-ttu-id="df026-110">Pole prvků nad `'T` .</span><span class="sxs-lookup"><span data-stu-id="df026-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="df026-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="df026-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="df026-112">`Bool`Hodnota nebo funkce predikátu použité pro všechny elementy.</span><span class="sxs-lookup"><span data-stu-id="df026-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="df026-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="df026-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="df026-114">'S</span><span class="sxs-lookup"><span data-stu-id="df026-114">'T</span></span>

<span data-ttu-id="df026-115">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="df026-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="df026-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="df026-116">Example</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function IsThreePresent() : Bool {
    let arrayOfInts = [1, 2, 3, 4, 5];
    let is3Present = IsNumberPresentInArray(3, arrayOfInts);
    return is3Present;
}

function IsNumberPresentInArray(n : Int, array : Int[]) : Bool {
    return Any(EqualI(_, n), array);
}
```

## <a name="remarks"></a><span data-ttu-id="df026-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="df026-117">Remarks</span></span>

<span data-ttu-id="df026-118">Funkce je definována pro obecné typy, tj., kdykoli máme pole `'T[]` a funkci, `predicate: 'T -> Bool` můžeme vytvořit `Bool` hodnotu, která označuje, zda určitý prvek splňuje požadavky `predicate` .</span><span class="sxs-lookup"><span data-stu-id="df026-118">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>