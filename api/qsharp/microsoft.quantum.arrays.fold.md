---
uid: Microsoft.Quantum.Arrays.Fold
title: Funkce skládání
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: 47c23dd657391d80fe473d98f2036d8ddf1dbb0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706001"
---
# <a name="fold-function"></a><span data-ttu-id="06897-102">Funkce skládání</span><span class="sxs-lookup"><span data-stu-id="06897-102">Fold function</span></span>

<span data-ttu-id="06897-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="06897-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="06897-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="06897-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="06897-105">Opakuje funkci `f` prostřednictvím pole `array` a vrátí `f(f(f(initialState, array[0]), array[1]), ...)` .</span><span class="sxs-lookup"><span data-stu-id="06897-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="06897-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="06897-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="06897-107">Složka: (' State, t)-> ' State</span><span class="sxs-lookup"><span data-stu-id="06897-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="06897-108">Funkce, která má být přeložena v poli.</span><span class="sxs-lookup"><span data-stu-id="06897-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="06897-109">stav: stav</span><span class="sxs-lookup"><span data-stu-id="06897-109">state : 'State</span></span>

<span data-ttu-id="06897-110">Počáteční stav složky.</span><span class="sxs-lookup"><span data-stu-id="06897-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="06897-111">Array: t []</span><span class="sxs-lookup"><span data-stu-id="06897-111">array : 'T[]</span></span>

<span data-ttu-id="06897-112">Pole hodnot, které se mají přeloží</span><span class="sxs-lookup"><span data-stu-id="06897-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="06897-113">Výstup: "State"</span><span class="sxs-lookup"><span data-stu-id="06897-113">Output : 'State</span></span>

<span data-ttu-id="06897-114">Konečný stav vrácený složkou po provedení iterace u všech prvků `array` .</span><span class="sxs-lookup"><span data-stu-id="06897-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="06897-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="06897-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="06897-116">Stav</span><span class="sxs-lookup"><span data-stu-id="06897-116">'State</span></span>

<span data-ttu-id="06897-117">Typ stavu, na kterém `folder` funkce pracuje, tj., přijímá jako první argument a vrací.</span><span class="sxs-lookup"><span data-stu-id="06897-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="06897-118">'S</span><span class="sxs-lookup"><span data-stu-id="06897-118">'T</span></span>

<span data-ttu-id="06897-119">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="06897-119">The type of `array` elements.</span></span>