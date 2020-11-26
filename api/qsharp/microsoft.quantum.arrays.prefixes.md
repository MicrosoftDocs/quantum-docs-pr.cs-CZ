---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Funkce prefixs
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 3501c11437534b1623bffba272a4517487e5634a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220380"
---
# <a name="prefixes-function"></a><span data-ttu-id="65a9c-102">Funkce prefixs</span><span class="sxs-lookup"><span data-stu-id="65a9c-102">Prefixes function</span></span>

<span data-ttu-id="65a9c-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="65a9c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="65a9c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="65a9c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="65a9c-105">Předanému poli vrátí všechny jeho předpony.</span><span class="sxs-lookup"><span data-stu-id="65a9c-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="65a9c-106">Popis</span><span class="sxs-lookup"><span data-stu-id="65a9c-106">Description</span></span>

<span data-ttu-id="65a9c-107">Vrátí pole všech předpon počínaje polem, které má pouze první prvek do kompletního pole.</span><span class="sxs-lookup"><span data-stu-id="65a9c-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="65a9c-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="65a9c-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="65a9c-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="65a9c-109">array : 'T[]</span></span>

<span data-ttu-id="65a9c-110">Pole prvků.</span><span class="sxs-lookup"><span data-stu-id="65a9c-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="65a9c-111">Výstup: t [] []</span><span class="sxs-lookup"><span data-stu-id="65a9c-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="65a9c-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="65a9c-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="65a9c-113">'S</span><span class="sxs-lookup"><span data-stu-id="65a9c-113">'T</span></span>

<span data-ttu-id="65a9c-114">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="65a9c-114">The type of `array` elements.</span></span>