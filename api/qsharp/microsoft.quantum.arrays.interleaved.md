---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Prokládaný funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 1ff5999cc19f47e3dcae601b960446923b613d90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220956"
---
# <a name="interleaved-function"></a><span data-ttu-id="86032-102">Prokládaný funkce</span><span class="sxs-lookup"><span data-stu-id="86032-102">Interleaved function</span></span>

<span data-ttu-id="86032-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="86032-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="86032-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="86032-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="86032-105">Ponechá dvě pole (téměř) stejné velikosti.</span><span class="sxs-lookup"><span data-stu-id="86032-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="86032-106">Popis</span><span class="sxs-lookup"><span data-stu-id="86032-106">Description</span></span>

<span data-ttu-id="86032-107">Tato funkce vrací prokládání dvou polí počínaje prvním prvkem z prvního pole, poté prvním prvkem z druhého pole a tak dále.</span><span class="sxs-lookup"><span data-stu-id="86032-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="86032-108">První pole musí být buď stejné délky jako druhá, nebo může mít jeden další prvek.</span><span class="sxs-lookup"><span data-stu-id="86032-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="86032-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="86032-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="86032-110">First: t []</span><span class="sxs-lookup"><span data-stu-id="86032-110">first : 'T[]</span></span>

<span data-ttu-id="86032-111">První pole, které má být prokládaný.</span><span class="sxs-lookup"><span data-stu-id="86032-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="86032-112">sekundy: t []</span><span class="sxs-lookup"><span data-stu-id="86032-112">second : 'T[]</span></span>

<span data-ttu-id="86032-113">Druhé pole, které se má pronechávat.</span><span class="sxs-lookup"><span data-stu-id="86032-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="86032-114">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="86032-114">Output : 'T[]</span></span>

<span data-ttu-id="86032-115">Prokládané pole</span><span class="sxs-lookup"><span data-stu-id="86032-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="86032-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="86032-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="86032-117">'S</span><span class="sxs-lookup"><span data-stu-id="86032-117">'T</span></span>

<span data-ttu-id="86032-118">Typ každého prvku `first` a `second` .</span><span class="sxs-lookup"><span data-stu-id="86032-118">The type of each element of `first` and `second`.</span></span>