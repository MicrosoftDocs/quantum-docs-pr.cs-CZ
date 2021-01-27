---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Prokládaný funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848118"
---
# <a name="interleaved-function"></a><span data-ttu-id="93489-102">Prokládaný funkce</span><span class="sxs-lookup"><span data-stu-id="93489-102">Interleaved function</span></span>

<span data-ttu-id="93489-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="93489-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="93489-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="93489-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="93489-105">Ponechá dvě pole (téměř) stejné velikosti.</span><span class="sxs-lookup"><span data-stu-id="93489-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="93489-106">Popis</span><span class="sxs-lookup"><span data-stu-id="93489-106">Description</span></span>

<span data-ttu-id="93489-107">Tato funkce vrací prokládání dvou polí počínaje prvním prvkem z prvního pole, poté prvním prvkem z druhého pole a tak dále.</span><span class="sxs-lookup"><span data-stu-id="93489-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="93489-108">První pole musí být buď stejné délky jako druhá, nebo může mít jeden další prvek.</span><span class="sxs-lookup"><span data-stu-id="93489-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="93489-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="93489-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="93489-110">First: t []</span><span class="sxs-lookup"><span data-stu-id="93489-110">first : 'T[]</span></span>

<span data-ttu-id="93489-111">První pole, které má být prokládaný.</span><span class="sxs-lookup"><span data-stu-id="93489-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="93489-112">sekundy: t []</span><span class="sxs-lookup"><span data-stu-id="93489-112">second : 'T[]</span></span>

<span data-ttu-id="93489-113">Druhé pole, které se má pronechávat.</span><span class="sxs-lookup"><span data-stu-id="93489-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="93489-114">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="93489-114">Output : 'T[]</span></span>

<span data-ttu-id="93489-115">Prokládané pole</span><span class="sxs-lookup"><span data-stu-id="93489-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="93489-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="93489-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="93489-117">'S</span><span class="sxs-lookup"><span data-stu-id="93489-117">'T</span></span>

<span data-ttu-id="93489-118">Typ každého prvku `first` a `second` .</span><span class="sxs-lookup"><span data-stu-id="93489-118">The type of each element of `first` and `second`.</span></span>

## <a name="example"></a><span data-ttu-id="93489-119">Příklad</span><span class="sxs-lookup"><span data-stu-id="93489-119">Example</span></span>

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```