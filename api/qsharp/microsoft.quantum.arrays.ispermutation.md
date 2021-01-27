---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Funkce ' permutace '
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848095"
---
# <a name="ispermutation-function"></a><span data-ttu-id="c722a-102">Funkce ' permutace '</span><span class="sxs-lookup"><span data-stu-id="c722a-102">IsPermutation function</span></span>

<span data-ttu-id="c722a-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c722a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c722a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c722a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c722a-105">Vrátí výstupy true, pokud dané pole představuje permutaci.</span><span class="sxs-lookup"><span data-stu-id="c722a-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="c722a-106">Popis</span><span class="sxs-lookup"><span data-stu-id="c722a-106">Description</span></span>

<span data-ttu-id="c722a-107">Vzhledem k poli `array` délky `n` vrátí hodnotu true pouze v případě, že se každé celé číslo od `0` do `n - 1` stejného zobrazení nachází v `array` , což `array` může být interpretováno jako permutace u `n` elementů.</span><span class="sxs-lookup"><span data-stu-id="c722a-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="c722a-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="c722a-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="c722a-109">permuation: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c722a-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c722a-110">Pole, které může nebo nemusí představovat permutaci.</span><span class="sxs-lookup"><span data-stu-id="c722a-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c722a-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c722a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="example"></a><span data-ttu-id="c722a-112">Příklad</span><span class="sxs-lookup"><span data-stu-id="c722a-112">Example</span></span>

<span data-ttu-id="c722a-113">Následující kód Q # vytiskne zprávu "všechna Diagnostika byla úspěšně dokončena":</span><span class="sxs-lookup"><span data-stu-id="c722a-113">The following Q# code prints the message "All diagnostics completed successfully":</span></span>

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a><span data-ttu-id="c722a-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c722a-114">Remarks</span></span>

<span data-ttu-id="c722a-115">Pole s nulovou délkou je triviální permutace.</span><span class="sxs-lookup"><span data-stu-id="c722a-115">An array of length zero is trivially a permutation.</span></span>