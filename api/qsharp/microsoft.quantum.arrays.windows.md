---
uid: Microsoft.Quantum.Arrays.Windows
title: Funkce Windows
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 6071d1c3e5981855c57abd0e741b1de0201c30a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705696"
---
# <a name="windows-function"></a><span data-ttu-id="c78af-102">Funkce Windows</span><span class="sxs-lookup"><span data-stu-id="c78af-102">Windows function</span></span>

<span data-ttu-id="c78af-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c78af-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c78af-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c78af-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c78af-105">Vrátí všechna po sobě následující podpole délky `size` .</span><span class="sxs-lookup"><span data-stu-id="c78af-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="c78af-106">Popis</span><span class="sxs-lookup"><span data-stu-id="c78af-106">Description</span></span>

<span data-ttu-id="c78af-107">Tato funkce vrací všechna `n - size + 1` podpole délky `size` v pořadí, kde `n` je délka `arr` .</span><span class="sxs-lookup"><span data-stu-id="c78af-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="c78af-108">První podpole jsou až do `arr[0..size - 1], arr[1..size], arr[2..size + 1]` posledního podpole `arr[n - size..n - 1]` .</span><span class="sxs-lookup"><span data-stu-id="c78af-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="c78af-109">Pokud `size <= 0` `size > n` je nebo, vrátí se prázdné pole.</span><span class="sxs-lookup"><span data-stu-id="c78af-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="c78af-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="c78af-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="c78af-111">Velikost: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c78af-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c78af-112">Délka podpole.</span><span class="sxs-lookup"><span data-stu-id="c78af-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="c78af-113">Array: t []</span><span class="sxs-lookup"><span data-stu-id="c78af-113">array : 'T[]</span></span>

<span data-ttu-id="c78af-114">Pole prvků.</span><span class="sxs-lookup"><span data-stu-id="c78af-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="c78af-115">Výstup: t [] []</span><span class="sxs-lookup"><span data-stu-id="c78af-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c78af-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c78af-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c78af-117">'S</span><span class="sxs-lookup"><span data-stu-id="c78af-117">'T</span></span>

<span data-ttu-id="c78af-118">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="c78af-118">The type of `array` elements.</span></span>