---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 1144e00227df1cd7d96bc76b118b0b556adbaa96
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221075"
---
# <a name="headandrest-function"></a><span data-ttu-id="bd91f-102">HeadAndRest – funkce</span><span class="sxs-lookup"><span data-stu-id="bd91f-102">HeadAndRest function</span></span>

<span data-ttu-id="bd91f-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bd91f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bd91f-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd91f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd91f-105">Vrátí řazenou kolekci členů prvního a všech zbývajících prvků pole.</span><span class="sxs-lookup"><span data-stu-id="bd91f-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="bd91f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="bd91f-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="bd91f-107">pole: ' A []</span><span class="sxs-lookup"><span data-stu-id="bd91f-107">array : 'A[]</span></span>

<span data-ttu-id="bd91f-108">Pole s alespoň jedním prvkem.</span><span class="sxs-lookup"><span data-stu-id="bd91f-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="bd91f-109">Výstup: (' A, ' A [])</span><span class="sxs-lookup"><span data-stu-id="bd91f-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="bd91f-110">Řazená kolekce členů prvního a všech zbývajících prvků pole.</span><span class="sxs-lookup"><span data-stu-id="bd91f-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bd91f-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="bd91f-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="bd91f-112">A</span><span class="sxs-lookup"><span data-stu-id="bd91f-112">'A</span></span>

<span data-ttu-id="bd91f-113">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="bd91f-113">The type of the array elements.</span></span>