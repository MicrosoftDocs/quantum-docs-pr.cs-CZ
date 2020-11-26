---
uid: Microsoft.Quantum.Arrays.Fold
title: Funkce skládání
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: a42f9a832c18bd612c1ae416187f3f2513eed54d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221160"
---
# <a name="fold-function"></a><span data-ttu-id="6755e-102">Funkce skládání</span><span class="sxs-lookup"><span data-stu-id="6755e-102">Fold function</span></span>

<span data-ttu-id="6755e-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6755e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6755e-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6755e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6755e-105">Opakuje funkci `f` prostřednictvím pole `array` a vrátí `f(f(f(initialState, array[0]), array[1]), ...)` .</span><span class="sxs-lookup"><span data-stu-id="6755e-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="6755e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="6755e-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="6755e-107">Složka: (' State, t)-> ' State</span><span class="sxs-lookup"><span data-stu-id="6755e-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="6755e-108">Funkce, která má být přeložena v poli.</span><span class="sxs-lookup"><span data-stu-id="6755e-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="6755e-109">stav: stav</span><span class="sxs-lookup"><span data-stu-id="6755e-109">state : 'State</span></span>

<span data-ttu-id="6755e-110">Počáteční stav složky.</span><span class="sxs-lookup"><span data-stu-id="6755e-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="6755e-111">Array: t []</span><span class="sxs-lookup"><span data-stu-id="6755e-111">array : 'T[]</span></span>

<span data-ttu-id="6755e-112">Pole hodnot, které se mají přeloží</span><span class="sxs-lookup"><span data-stu-id="6755e-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="6755e-113">Výstup: "State"</span><span class="sxs-lookup"><span data-stu-id="6755e-113">Output : 'State</span></span>

<span data-ttu-id="6755e-114">Konečný stav vrácený složkou po provedení iterace u všech prvků `array` .</span><span class="sxs-lookup"><span data-stu-id="6755e-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6755e-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="6755e-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="6755e-116">Stav</span><span class="sxs-lookup"><span data-stu-id="6755e-116">'State</span></span>

<span data-ttu-id="6755e-117">Typ stavu, na kterém `folder` funkce pracuje, tj., přijímá jako první argument a vrací.</span><span class="sxs-lookup"><span data-stu-id="6755e-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="6755e-118">'S</span><span class="sxs-lookup"><span data-stu-id="6755e-118">'T</span></span>

<span data-ttu-id="6755e-119">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="6755e-119">The type of `array` elements.</span></span>