---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: c929054b96ee499db896cacf0e3ae4da6f6c4b98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705912"
---
# <a name="lookupfunction-function"></a><span data-ttu-id="2b8d0-102">LookupFunction – funkce</span><span class="sxs-lookup"><span data-stu-id="2b8d0-102">LookupFunction function</span></span>

<span data-ttu-id="2b8d0-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2b8d0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2b8d0-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2b8d0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2b8d0-105">Předanému poli vrátí funkci, která vrátí prvky daného pole.</span><span class="sxs-lookup"><span data-stu-id="2b8d0-105">Given an array, returns a function which returns elements of that array.</span></span>

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a><span data-ttu-id="2b8d0-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2b8d0-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="2b8d0-107">Array: t []</span><span class="sxs-lookup"><span data-stu-id="2b8d0-107">array : 'T[]</span></span>

<span data-ttu-id="2b8d0-108">Pole, které má být reprezentováno jako vyhledávací funkce.</span><span class="sxs-lookup"><span data-stu-id="2b8d0-108">The array to be represented as a lookup function.</span></span>



## <a name="output--int---t"></a><span data-ttu-id="2b8d0-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int) -> 't</span><span class="sxs-lookup"><span data-stu-id="2b8d0-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="2b8d0-110">Funkce `f` , například `f(idx) == f[idx]` .</span><span class="sxs-lookup"><span data-stu-id="2b8d0-110">A function `f` such that `f(idx) == f[idx]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2b8d0-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="2b8d0-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2b8d0-112">'S</span><span class="sxs-lookup"><span data-stu-id="2b8d0-112">'T</span></span>

<span data-ttu-id="2b8d0-113">Typ prvků pole reprezentovaných jako vyhledávací funkce.</span><span class="sxs-lookup"><span data-stu-id="2b8d0-113">The type of the elements of the array being represented as a lookup function.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b8d0-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2b8d0-114">Remarks</span></span>

<span data-ttu-id="2b8d0-115">Tato funkce je hlavně užitečná pro spolupráci s funkcemi a operacemi, které `Int -> 'T` jako argumenty přijímají funkce.</span><span class="sxs-lookup"><span data-stu-id="2b8d0-115">This function is mainly useful for interoperating with functions and operations that take `Int -> 'T` functions as their arguments.</span></span> <span data-ttu-id="2b8d0-116">To je běžné, například v knihovně reprezentace generátoru, kde jsou funkce použity pro zamezení nutnosti zaznamenat celé pole v paměti.</span><span class="sxs-lookup"><span data-stu-id="2b8d0-116">This is common, for instance, in the generator representation library, where functions are used to avoid the need to record an entire array in memory.</span></span>