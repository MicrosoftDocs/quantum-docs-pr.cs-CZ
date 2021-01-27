---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: 95cd5233a09a1234bba4de9fe870b9d93c0f86a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846250"
---
# <a name="cumulativefolded-function"></a><span data-ttu-id="6a425-102">CumulativeFolded – funkce</span><span class="sxs-lookup"><span data-stu-id="6a425-102">CumulativeFolded function</span></span>

<span data-ttu-id="6a425-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6a425-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6a425-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6a425-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6a425-105">Kombinuje namapovaná a přeložení na jednu funkci</span><span class="sxs-lookup"><span data-stu-id="6a425-105">Combines Mapped and Fold into a single function</span></span>

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a><span data-ttu-id="6a425-106">Popis</span><span class="sxs-lookup"><span data-stu-id="6a425-106">Description</span></span>

<span data-ttu-id="6a425-107">Tato funkce provede iteraci `fn` funkce prostřednictvím pole, počínaje počátečním stavem `state` a vrátí všechny mezilehlé hodnoty, včetně počátečního stavu.</span><span class="sxs-lookup"><span data-stu-id="6a425-107">This function iterates the `fn` function through the array, starting from an initial state `state` and returns all intermediate values, not including the inital state.</span></span>

## <a name="input"></a><span data-ttu-id="6a425-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="6a425-108">Input</span></span>

### <a name="fn--statet---state"></a><span data-ttu-id="6a425-109">FN: (' State, t)-> ' State</span><span class="sxs-lookup"><span data-stu-id="6a425-109">fn : ('State,'T) -> 'State</span></span>

<span data-ttu-id="6a425-110">Funkce, která se má v poli přeloží</span><span class="sxs-lookup"><span data-stu-id="6a425-110">A function to be folded over the array</span></span>


### <a name="state--state"></a><span data-ttu-id="6a425-111">stav: stav</span><span class="sxs-lookup"><span data-stu-id="6a425-111">state : 'State</span></span>

<span data-ttu-id="6a425-112">Počáteční stav, který se má přeloží</span><span class="sxs-lookup"><span data-stu-id="6a425-112">The initial state to be folded</span></span>


### <a name="array--t"></a><span data-ttu-id="6a425-113">Array: t []</span><span class="sxs-lookup"><span data-stu-id="6a425-113">array : 'T[]</span></span>

<span data-ttu-id="6a425-114">Pole hodnot, které se mají přeloží</span><span class="sxs-lookup"><span data-stu-id="6a425-114">An array of values to be folded over</span></span>



## <a name="output--state"></a><span data-ttu-id="6a425-115">Výstup: State []</span><span class="sxs-lookup"><span data-stu-id="6a425-115">Output : 'State[]</span></span>

<span data-ttu-id="6a425-116">Všechny přechodné stavy, včetně konečného stavu, ale ne počátečního stavu.</span><span class="sxs-lookup"><span data-stu-id="6a425-116">All intermediate states, including the final state, but not the initial state.</span></span>
<span data-ttu-id="6a425-117">Délka výstupního pole má stejnou délku jako `array` .</span><span class="sxs-lookup"><span data-stu-id="6a425-117">The length of the output array is of the same length as `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6a425-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="6a425-118">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="6a425-119">Stav</span><span class="sxs-lookup"><span data-stu-id="6a425-119">'State</span></span>

<span data-ttu-id="6a425-120">Typ stavů, na kterých `fn` funkce funguje, tj., přijímá jako první vstup a vrátí.</span><span class="sxs-lookup"><span data-stu-id="6a425-120">The type of states that the `fn` function operates on, i.e., accepts as its first input and returns.</span></span>
### <a name="t"></a><span data-ttu-id="6a425-121">'S</span><span class="sxs-lookup"><span data-stu-id="6a425-121">'T</span></span>

<span data-ttu-id="6a425-122">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="6a425-122">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="6a425-123">Příklad</span><span class="sxs-lookup"><span data-stu-id="6a425-123">Example</span></span>

```qsharp
// same as sums = [1, 3, 6, 10, 15]
let sums = CumulativeFolded(PlusI, 0, SequenceI(1, 5));
```