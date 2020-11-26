---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: ffb934d06f6be06cbc35a523c90d2c54e0a51353
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210025"
---
# <a name="cumulativefolded-function"></a><span data-ttu-id="c3dd2-102">CumulativeFolded – funkce</span><span class="sxs-lookup"><span data-stu-id="c3dd2-102">CumulativeFolded function</span></span>

<span data-ttu-id="c3dd2-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c3dd2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c3dd2-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c3dd2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c3dd2-105">Kombinuje namapovaná a přeložení na jednu funkci</span><span class="sxs-lookup"><span data-stu-id="c3dd2-105">Combines Mapped and Fold into a single function</span></span>

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a><span data-ttu-id="c3dd2-106">Popis</span><span class="sxs-lookup"><span data-stu-id="c3dd2-106">Description</span></span>

<span data-ttu-id="c3dd2-107">Tato funkce provede iteraci `fn` funkce prostřednictvím pole, počínaje počátečním stavem `state` a vrátí všechny mezilehlé hodnoty, včetně počátečního stavu.</span><span class="sxs-lookup"><span data-stu-id="c3dd2-107">This function iterates the `fn` function through the array, starting from an initial state `state` and returns all intermediate values, not including the inital state.</span></span>

## <a name="input"></a><span data-ttu-id="c3dd2-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="c3dd2-108">Input</span></span>

### <a name="fn--statet---state"></a><span data-ttu-id="c3dd2-109">FN: (' State, t)-> ' State</span><span class="sxs-lookup"><span data-stu-id="c3dd2-109">fn : ('State,'T) -> 'State</span></span>

<span data-ttu-id="c3dd2-110">Funkce, která se má v poli přeloží</span><span class="sxs-lookup"><span data-stu-id="c3dd2-110">A function to be folded over the array</span></span>


### <a name="state--state"></a><span data-ttu-id="c3dd2-111">stav: stav</span><span class="sxs-lookup"><span data-stu-id="c3dd2-111">state : 'State</span></span>

<span data-ttu-id="c3dd2-112">Počáteční stav, který se má přeloží</span><span class="sxs-lookup"><span data-stu-id="c3dd2-112">The initial state to be folded</span></span>


### <a name="array--t"></a><span data-ttu-id="c3dd2-113">Array: t []</span><span class="sxs-lookup"><span data-stu-id="c3dd2-113">array : 'T[]</span></span>

<span data-ttu-id="c3dd2-114">Pole hodnot, které se mají přeloží</span><span class="sxs-lookup"><span data-stu-id="c3dd2-114">An array of values to be folded over</span></span>



## <a name="output--state"></a><span data-ttu-id="c3dd2-115">Výstup: State []</span><span class="sxs-lookup"><span data-stu-id="c3dd2-115">Output : 'State[]</span></span>

<span data-ttu-id="c3dd2-116">Všechny přechodné stavy, včetně konečného stavu, ale ne počátečního stavu.</span><span class="sxs-lookup"><span data-stu-id="c3dd2-116">All intermediate states, including the final state, but not the initial state.</span></span>
<span data-ttu-id="c3dd2-117">Délka výstupního pole má stejnou délku jako `array` .</span><span class="sxs-lookup"><span data-stu-id="c3dd2-117">The length of the output array is of the same length as `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c3dd2-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c3dd2-118">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="c3dd2-119">Stav</span><span class="sxs-lookup"><span data-stu-id="c3dd2-119">'State</span></span>

<span data-ttu-id="c3dd2-120">Typ stavů, na kterých `fn` funkce funguje, tj., přijímá jako první vstup a vrátí.</span><span class="sxs-lookup"><span data-stu-id="c3dd2-120">The type of states that the `fn` function operates on, i.e., accepts as its first input and returns.</span></span>
### <a name="t"></a><span data-ttu-id="c3dd2-121">'S</span><span class="sxs-lookup"><span data-stu-id="c3dd2-121">'T</span></span>

<span data-ttu-id="c3dd2-122">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="c3dd2-122">The type of `array` elements.</span></span>