---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: c082e0a917343c18e5f511f065b2e78f1e217ecc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848546"
---
# <a name="headandrest-function"></a><span data-ttu-id="24515-102">HeadAndRest – funkce</span><span class="sxs-lookup"><span data-stu-id="24515-102">HeadAndRest function</span></span>

<span data-ttu-id="24515-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="24515-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="24515-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="24515-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="24515-105">Vrátí řazenou kolekci členů prvního a všech zbývajících prvků pole.</span><span class="sxs-lookup"><span data-stu-id="24515-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="24515-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="24515-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="24515-107">pole: ' A []</span><span class="sxs-lookup"><span data-stu-id="24515-107">array : 'A[]</span></span>

<span data-ttu-id="24515-108">Pole s alespoň jedním prvkem.</span><span class="sxs-lookup"><span data-stu-id="24515-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="24515-109">Výstup: (' A, ' A [])</span><span class="sxs-lookup"><span data-stu-id="24515-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="24515-110">Řazená kolekce členů prvního a všech zbývajících prvků pole.</span><span class="sxs-lookup"><span data-stu-id="24515-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="24515-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="24515-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="24515-112">A</span><span class="sxs-lookup"><span data-stu-id="24515-112">'A</span></span>

<span data-ttu-id="24515-113">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="24515-113">The type of the array elements.</span></span>