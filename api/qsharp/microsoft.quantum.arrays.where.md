---
uid: Microsoft.Quantum.Arrays.Where
title: WHERE – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 1c9fa0463ed49788d12502257d735b965565d1ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705697"
---
# <a name="where-function"></a><span data-ttu-id="56d36-102">WHERE – funkce</span><span class="sxs-lookup"><span data-stu-id="56d36-102">Where function</span></span>

<span data-ttu-id="56d36-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="56d36-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="56d36-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="56d36-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="56d36-105">V případě predikátu a pole vrátí indexy tohoto pole, kde má predikát hodnotu true.</span><span class="sxs-lookup"><span data-stu-id="56d36-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="56d36-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="56d36-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="56d36-107">predikát: t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="56d36-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="56d36-108">Funkce z `'T` na logickou hodnotu, která slouží k filtrování prvků.</span><span class="sxs-lookup"><span data-stu-id="56d36-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="56d36-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="56d36-109">array : 'T[]</span></span>

<span data-ttu-id="56d36-110">Pole prvků nad `'T` .</span><span class="sxs-lookup"><span data-stu-id="56d36-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="56d36-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="56d36-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="56d36-112">Pole indexů, kde `predicate` je true.</span><span class="sxs-lookup"><span data-stu-id="56d36-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="56d36-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="56d36-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="56d36-114">'S</span><span class="sxs-lookup"><span data-stu-id="56d36-114">'T</span></span>

<span data-ttu-id="56d36-115">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="56d36-115">The type of `array` elements.</span></span>