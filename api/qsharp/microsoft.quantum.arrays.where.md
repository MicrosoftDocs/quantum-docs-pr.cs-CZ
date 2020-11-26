---
uid: Microsoft.Quantum.Arrays.Where
title: WHERE – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 97598aa25d2d085aaab94f3d60ee64db9e2b89d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219919"
---
# <a name="where-function"></a><span data-ttu-id="7f8cb-102">WHERE – funkce</span><span class="sxs-lookup"><span data-stu-id="7f8cb-102">Where function</span></span>

<span data-ttu-id="7f8cb-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7f8cb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7f8cb-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7f8cb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7f8cb-105">V případě predikátu a pole vrátí indexy tohoto pole, kde má predikát hodnotu true.</span><span class="sxs-lookup"><span data-stu-id="7f8cb-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="7f8cb-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="7f8cb-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="7f8cb-107">predikát: t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7f8cb-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7f8cb-108">Funkce z `'T` na logickou hodnotu, která slouží k filtrování prvků.</span><span class="sxs-lookup"><span data-stu-id="7f8cb-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="7f8cb-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="7f8cb-109">array : 'T[]</span></span>

<span data-ttu-id="7f8cb-110">Pole prvků nad `'T` .</span><span class="sxs-lookup"><span data-stu-id="7f8cb-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="7f8cb-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7f8cb-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7f8cb-112">Pole indexů, kde `predicate` je true.</span><span class="sxs-lookup"><span data-stu-id="7f8cb-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7f8cb-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="7f8cb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7f8cb-114">'S</span><span class="sxs-lookup"><span data-stu-id="7f8cb-114">'T</span></span>

<span data-ttu-id="7f8cb-115">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="7f8cb-115">The type of `array` elements.</span></span>