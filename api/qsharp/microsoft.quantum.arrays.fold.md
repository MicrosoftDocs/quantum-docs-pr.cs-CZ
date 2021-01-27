---
uid: Microsoft.Quantum.Arrays.Fold
title: Funkce skládání
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: d12e070058178ce2cbdd70cade5bc16607a55d5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848610"
---
# <a name="fold-function"></a><span data-ttu-id="50e64-102">Funkce skládání</span><span class="sxs-lookup"><span data-stu-id="50e64-102">Fold function</span></span>

<span data-ttu-id="50e64-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="50e64-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="50e64-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="50e64-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="50e64-105">Opakuje funkci `f` prostřednictvím pole `array` a vrátí `f(f(f(initialState, array[0]), array[1]), ...)` .</span><span class="sxs-lookup"><span data-stu-id="50e64-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="50e64-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="50e64-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="50e64-107">Složka: (' State, t)-> ' State</span><span class="sxs-lookup"><span data-stu-id="50e64-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="50e64-108">Funkce, která má být přeložena v poli.</span><span class="sxs-lookup"><span data-stu-id="50e64-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="50e64-109">stav: stav</span><span class="sxs-lookup"><span data-stu-id="50e64-109">state : 'State</span></span>

<span data-ttu-id="50e64-110">Počáteční stav složky.</span><span class="sxs-lookup"><span data-stu-id="50e64-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="50e64-111">Array: t []</span><span class="sxs-lookup"><span data-stu-id="50e64-111">array : 'T[]</span></span>

<span data-ttu-id="50e64-112">Pole hodnot, které se mají přeloží</span><span class="sxs-lookup"><span data-stu-id="50e64-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="50e64-113">Výstup: "State"</span><span class="sxs-lookup"><span data-stu-id="50e64-113">Output : 'State</span></span>

<span data-ttu-id="50e64-114">Konečný stav vrácený složkou po provedení iterace u všech prvků `array` .</span><span class="sxs-lookup"><span data-stu-id="50e64-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="50e64-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="50e64-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="50e64-116">Stav</span><span class="sxs-lookup"><span data-stu-id="50e64-116">'State</span></span>

<span data-ttu-id="50e64-117">Typ stavu, na kterém `folder` funkce pracuje, tj., přijímá jako první argument a vrací.</span><span class="sxs-lookup"><span data-stu-id="50e64-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="50e64-118">'S</span><span class="sxs-lookup"><span data-stu-id="50e64-118">'T</span></span>

<span data-ttu-id="50e64-119">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="50e64-119">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="50e64-120">Příklad</span><span class="sxs-lookup"><span data-stu-id="50e64-120">Example</span></span>

```qsharp
function Plus(a : Double, b : Double) {
    return a + b;
}
function Sum(xs : Double[]) {
    return Fold(Plus, 0.0, xs);
}
```