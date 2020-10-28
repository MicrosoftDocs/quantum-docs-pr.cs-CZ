---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Prokládaný funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 8405cabca17f2dd7c2680833bfab5c3768fcf752
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705960"
---
# <a name="interleaved-function"></a><span data-ttu-id="76194-102">Prokládaný funkce</span><span class="sxs-lookup"><span data-stu-id="76194-102">Interleaved function</span></span>

<span data-ttu-id="76194-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="76194-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="76194-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="76194-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="76194-105">Ponechá dvě pole (téměř) stejné velikosti.</span><span class="sxs-lookup"><span data-stu-id="76194-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="76194-106">Popis</span><span class="sxs-lookup"><span data-stu-id="76194-106">Description</span></span>

<span data-ttu-id="76194-107">Tato funkce vrací prokládání dvou polí počínaje prvním prvkem z prvního pole, poté prvním prvkem z druhého pole a tak dále.</span><span class="sxs-lookup"><span data-stu-id="76194-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="76194-108">První pole musí být buď stejné délky jako druhá, nebo může mít jeden další prvek.</span><span class="sxs-lookup"><span data-stu-id="76194-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="76194-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="76194-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="76194-110">First: t []</span><span class="sxs-lookup"><span data-stu-id="76194-110">first : 'T[]</span></span>

<span data-ttu-id="76194-111">První pole, které má být prokládaný.</span><span class="sxs-lookup"><span data-stu-id="76194-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="76194-112">sekundy: t []</span><span class="sxs-lookup"><span data-stu-id="76194-112">second : 'T[]</span></span>

<span data-ttu-id="76194-113">Druhé pole, které se má pronechávat.</span><span class="sxs-lookup"><span data-stu-id="76194-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="76194-114">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="76194-114">Output : 'T[]</span></span>

<span data-ttu-id="76194-115">Prokládané pole</span><span class="sxs-lookup"><span data-stu-id="76194-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="76194-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="76194-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="76194-117">'S</span><span class="sxs-lookup"><span data-stu-id="76194-117">'T</span></span>

<span data-ttu-id="76194-118">Typ každého prvku `first` a `second` .</span><span class="sxs-lookup"><span data-stu-id="76194-118">The type of each element of `first` and `second`.</span></span>