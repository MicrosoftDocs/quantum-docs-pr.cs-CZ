---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Funkce prefixs
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 1576e57e9dc64a605eb65cb841640e72a3b126ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705824"
---
# <a name="prefixes-function"></a><span data-ttu-id="326e4-102">Funkce prefixs</span><span class="sxs-lookup"><span data-stu-id="326e4-102">Prefixes function</span></span>

<span data-ttu-id="326e4-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="326e4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="326e4-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="326e4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="326e4-105">Předanému poli vrátí všechny jeho předpony.</span><span class="sxs-lookup"><span data-stu-id="326e4-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="326e4-106">Popis</span><span class="sxs-lookup"><span data-stu-id="326e4-106">Description</span></span>

<span data-ttu-id="326e4-107">Vrátí pole všech předpon počínaje polem, které má pouze první prvek do kompletního pole.</span><span class="sxs-lookup"><span data-stu-id="326e4-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="326e4-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="326e4-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="326e4-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="326e4-109">array : 'T[]</span></span>

<span data-ttu-id="326e4-110">Pole prvků.</span><span class="sxs-lookup"><span data-stu-id="326e4-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="326e4-111">Výstup: t [] []</span><span class="sxs-lookup"><span data-stu-id="326e4-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="326e4-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="326e4-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="326e4-113">'S</span><span class="sxs-lookup"><span data-stu-id="326e4-113">'T</span></span>

<span data-ttu-id="326e4-114">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="326e4-114">The type of `array` elements.</span></span>