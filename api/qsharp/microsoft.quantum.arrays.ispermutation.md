---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Funkce ' permutace '
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 144f683818b5d75de5b075328365d3e994de29d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220922"
---
# <a name="ispermutation-function"></a><span data-ttu-id="2400c-102">Funkce ' permutace '</span><span class="sxs-lookup"><span data-stu-id="2400c-102">IsPermutation function</span></span>

<span data-ttu-id="2400c-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2400c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2400c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2400c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2400c-105">Vrátí výstupy true, pokud dané pole představuje permutaci.</span><span class="sxs-lookup"><span data-stu-id="2400c-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="2400c-106">Popis</span><span class="sxs-lookup"><span data-stu-id="2400c-106">Description</span></span>

<span data-ttu-id="2400c-107">Vzhledem k poli `array` délky `n` vrátí hodnotu true pouze v případě, že se každé celé číslo od `0` do `n - 1` stejného zobrazení nachází v `array` , což `array` může být interpretováno jako permutace u `n` elementů.</span><span class="sxs-lookup"><span data-stu-id="2400c-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="2400c-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="2400c-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="2400c-109">permuation: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2400c-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2400c-110">Pole, které může nebo nemusí představovat permutaci.</span><span class="sxs-lookup"><span data-stu-id="2400c-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2400c-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2400c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="remarks"></a><span data-ttu-id="2400c-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2400c-112">Remarks</span></span>

<span data-ttu-id="2400c-113">Pole s nulovou délkou je triviální permutace.</span><span class="sxs-lookup"><span data-stu-id="2400c-113">An array of length zero is trivially a permutation.</span></span>