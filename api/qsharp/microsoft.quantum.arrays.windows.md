---
uid: Microsoft.Quantum.Arrays.Windows
title: Funkce Windows
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 8f32a23aa4379744b84c3b8d9c8f565e61c3c64e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219885"
---
# <a name="windows-function"></a><span data-ttu-id="b7c61-102">Funkce Windows</span><span class="sxs-lookup"><span data-stu-id="b7c61-102">Windows function</span></span>

<span data-ttu-id="b7c61-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b7c61-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b7c61-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b7c61-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b7c61-105">Vrátí všechna po sobě následující podpole délky `size` .</span><span class="sxs-lookup"><span data-stu-id="b7c61-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="b7c61-106">Popis</span><span class="sxs-lookup"><span data-stu-id="b7c61-106">Description</span></span>

<span data-ttu-id="b7c61-107">Tato funkce vrací všechna `n - size + 1` podpole délky `size` v pořadí, kde `n` je délka `arr` .</span><span class="sxs-lookup"><span data-stu-id="b7c61-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="b7c61-108">První podpole jsou až do `arr[0..size - 1], arr[1..size], arr[2..size + 1]` posledního podpole `arr[n - size..n - 1]` .</span><span class="sxs-lookup"><span data-stu-id="b7c61-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="b7c61-109">Pokud `size <= 0` `size > n` je nebo, vrátí se prázdné pole.</span><span class="sxs-lookup"><span data-stu-id="b7c61-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="b7c61-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="b7c61-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="b7c61-111">Velikost: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b7c61-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b7c61-112">Délka podpole.</span><span class="sxs-lookup"><span data-stu-id="b7c61-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="b7c61-113">Array: t []</span><span class="sxs-lookup"><span data-stu-id="b7c61-113">array : 'T[]</span></span>

<span data-ttu-id="b7c61-114">Pole prvků.</span><span class="sxs-lookup"><span data-stu-id="b7c61-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="b7c61-115">Výstup: t [] []</span><span class="sxs-lookup"><span data-stu-id="b7c61-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b7c61-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b7c61-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b7c61-117">'S</span><span class="sxs-lookup"><span data-stu-id="b7c61-117">'T</span></span>

<span data-ttu-id="b7c61-118">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="b7c61-118">The type of `array` elements.</span></span>