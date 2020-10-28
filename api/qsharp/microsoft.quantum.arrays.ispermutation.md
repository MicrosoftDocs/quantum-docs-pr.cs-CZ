---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Funkce ' permutace '
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 361bb21bedc725c25a1f3dfc811e9cfda4cb45ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705936"
---
# <a name="ispermutation-function"></a><span data-ttu-id="41213-102">Funkce ' permutace '</span><span class="sxs-lookup"><span data-stu-id="41213-102">IsPermutation function</span></span>

<span data-ttu-id="41213-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="41213-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="41213-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="41213-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="41213-105">Vrátí výstupy true, pokud dané pole představuje permutaci.</span><span class="sxs-lookup"><span data-stu-id="41213-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="41213-106">Popis</span><span class="sxs-lookup"><span data-stu-id="41213-106">Description</span></span>

<span data-ttu-id="41213-107">Vzhledem k poli `array` délky `n` vrátí hodnotu true pouze v případě, že se každé celé číslo od `0` do `n - 1` stejného zobrazení nachází v `array` , což `array` může být interpretováno jako permutace u `n` elementů.</span><span class="sxs-lookup"><span data-stu-id="41213-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="41213-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="41213-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="41213-109">permuation: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="41213-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="41213-110">Pole, které může nebo nemusí představovat permutaci.</span><span class="sxs-lookup"><span data-stu-id="41213-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="41213-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="41213-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="remarks"></a><span data-ttu-id="41213-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="41213-112">Remarks</span></span>

<span data-ttu-id="41213-113">Pole s nulovou délkou je triviální permutace.</span><span class="sxs-lookup"><span data-stu-id="41213-113">An array of length zero is trivially a permutation.</span></span>