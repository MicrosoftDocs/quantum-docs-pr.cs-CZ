---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: a09c2779c8f06d8f6b7b0902366f3cefbbca4525
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706128"
---
# <a name="cumulativefolded-function"></a><span data-ttu-id="b3c59-102">CumulativeFolded – funkce</span><span class="sxs-lookup"><span data-stu-id="b3c59-102">CumulativeFolded function</span></span>

<span data-ttu-id="b3c59-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b3c59-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b3c59-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b3c59-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b3c59-105">Kombinuje namapovaná a přeložení na jednu funkci</span><span class="sxs-lookup"><span data-stu-id="b3c59-105">Combines Mapped and Fold into a single function</span></span>

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a><span data-ttu-id="b3c59-106">Popis</span><span class="sxs-lookup"><span data-stu-id="b3c59-106">Description</span></span>

<span data-ttu-id="b3c59-107">Tato funkce provede iteraci `fn` funkce prostřednictvím pole, počínaje počátečním stavem `state` a vrátí všechny mezilehlé hodnoty, včetně počátečního stavu.</span><span class="sxs-lookup"><span data-stu-id="b3c59-107">This function iterates the `fn` function through the array, starting from an initial state `state` and returns all intermediate values, not including the inital state.</span></span>

## <a name="input"></a><span data-ttu-id="b3c59-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="b3c59-108">Input</span></span>

### <a name="fn--statet---state"></a><span data-ttu-id="b3c59-109">FN: (' State, t)-> ' State</span><span class="sxs-lookup"><span data-stu-id="b3c59-109">fn : ('State,'T) -> 'State</span></span>

<span data-ttu-id="b3c59-110">Funkce, která se má v poli přeloží</span><span class="sxs-lookup"><span data-stu-id="b3c59-110">A function to be folded over the array</span></span>


### <a name="state--state"></a><span data-ttu-id="b3c59-111">stav: stav</span><span class="sxs-lookup"><span data-stu-id="b3c59-111">state : 'State</span></span>

<span data-ttu-id="b3c59-112">Počáteční stav, který se má přeloží</span><span class="sxs-lookup"><span data-stu-id="b3c59-112">The initial state to be folded</span></span>


### <a name="array--t"></a><span data-ttu-id="b3c59-113">Array: t []</span><span class="sxs-lookup"><span data-stu-id="b3c59-113">array : 'T[]</span></span>

<span data-ttu-id="b3c59-114">Pole hodnot, které se mají přeloží</span><span class="sxs-lookup"><span data-stu-id="b3c59-114">An array of values to be folded over</span></span>



## <a name="output--state"></a><span data-ttu-id="b3c59-115">Výstup: State []</span><span class="sxs-lookup"><span data-stu-id="b3c59-115">Output : 'State[]</span></span>

<span data-ttu-id="b3c59-116">Všechny přechodné stavy, včetně konečného stavu, ale ne počátečního stavu.</span><span class="sxs-lookup"><span data-stu-id="b3c59-116">All intermediate states, including the final state, but not the initial state.</span></span>
<span data-ttu-id="b3c59-117">Délka výstupního pole má stejnou délku jako `array` .</span><span class="sxs-lookup"><span data-stu-id="b3c59-117">The length of the output array is of the same length as `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b3c59-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b3c59-118">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="b3c59-119">Stav</span><span class="sxs-lookup"><span data-stu-id="b3c59-119">'State</span></span>

<span data-ttu-id="b3c59-120">Typ stavů, na kterých `fn` funkce funguje, tj., přijímá jako první vstup a vrátí.</span><span class="sxs-lookup"><span data-stu-id="b3c59-120">The type of states that the `fn` function operates on, i.e., accepts as its first input and returns.</span></span>
### <a name="t"></a><span data-ttu-id="b3c59-121">'S</span><span class="sxs-lookup"><span data-stu-id="b3c59-121">'T</span></span>

<span data-ttu-id="b3c59-122">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="b3c59-122">The type of `array` elements.</span></span>