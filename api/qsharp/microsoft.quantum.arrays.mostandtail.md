---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 392efb20e4aaba80a77664444bb415d8bc9b0930
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220565"
---
# <a name="mostandtail-function"></a><span data-ttu-id="b570d-102">MostAndTail – funkce</span><span class="sxs-lookup"><span data-stu-id="b570d-102">MostAndTail function</span></span>

<span data-ttu-id="b570d-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b570d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b570d-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b570d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b570d-105">Vrátí řazenou kolekci členů všech kromě jednoho a posledního elementu pole.</span><span class="sxs-lookup"><span data-stu-id="b570d-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="b570d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="b570d-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="b570d-107">pole: ' A []</span><span class="sxs-lookup"><span data-stu-id="b570d-107">array : 'A[]</span></span>

<span data-ttu-id="b570d-108">Pole s alespoň jedním prvkem.</span><span class="sxs-lookup"><span data-stu-id="b570d-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="b570d-109">Výstup: (' A [], ' A)</span><span class="sxs-lookup"><span data-stu-id="b570d-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="b570d-110">Řazená kolekce členů všech s výjimkou jednoho a posledního elementu pole.</span><span class="sxs-lookup"><span data-stu-id="b570d-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b570d-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b570d-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="b570d-112">A</span><span class="sxs-lookup"><span data-stu-id="b570d-112">'A</span></span>

<span data-ttu-id="b570d-113">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="b570d-113">The type of the array elements.</span></span>