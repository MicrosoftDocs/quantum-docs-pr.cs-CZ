---
uid: Microsoft.Quantum.Arrays.Windows
title: Funkce Windows
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: adfea2b9a2f6c22446817538d29586284dba723e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842195"
---
# <a name="windows-function"></a><span data-ttu-id="6e084-102">Funkce Windows</span><span class="sxs-lookup"><span data-stu-id="6e084-102">Windows function</span></span>

<span data-ttu-id="6e084-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6e084-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6e084-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6e084-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6e084-105">Vrátí všechna po sobě následující podpole délky `size` .</span><span class="sxs-lookup"><span data-stu-id="6e084-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="6e084-106">Popis</span><span class="sxs-lookup"><span data-stu-id="6e084-106">Description</span></span>

<span data-ttu-id="6e084-107">Tato funkce vrací všechna `n - size + 1` podpole délky `size` v pořadí, kde `n` je délka `arr` .</span><span class="sxs-lookup"><span data-stu-id="6e084-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="6e084-108">První podpole jsou až do `arr[0..size - 1], arr[1..size], arr[2..size + 1]` posledního podpole `arr[n - size..n - 1]` .</span><span class="sxs-lookup"><span data-stu-id="6e084-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="6e084-109">Pokud `size <= 0` `size > n` je nebo, vrátí se prázdné pole.</span><span class="sxs-lookup"><span data-stu-id="6e084-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="6e084-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="6e084-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="6e084-111">Velikost: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6e084-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6e084-112">Délka podpole.</span><span class="sxs-lookup"><span data-stu-id="6e084-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="6e084-113">Array: t []</span><span class="sxs-lookup"><span data-stu-id="6e084-113">array : 'T[]</span></span>

<span data-ttu-id="6e084-114">Pole prvků.</span><span class="sxs-lookup"><span data-stu-id="6e084-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="6e084-115">Výstup: t [] []</span><span class="sxs-lookup"><span data-stu-id="6e084-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6e084-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="6e084-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6e084-117">'S</span><span class="sxs-lookup"><span data-stu-id="6e084-117">'T</span></span>

<span data-ttu-id="6e084-118">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="6e084-118">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="6e084-119">Příklad</span><span class="sxs-lookup"><span data-stu-id="6e084-119">Example</span></span>

```qsharp
// same as [[1, 2, 3], [2, 3, 4], [3, 4, 5]]
let windows = Windows(3, [1, 2, 3, 4, 5]);
```