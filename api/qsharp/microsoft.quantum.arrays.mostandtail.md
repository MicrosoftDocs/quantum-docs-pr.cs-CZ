---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: fd5569f1b71ac2fdf2b5c08ba7dde172e3a6744e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845589"
---
# <a name="mostandtail-function"></a><span data-ttu-id="a0037-102">MostAndTail – funkce</span><span class="sxs-lookup"><span data-stu-id="a0037-102">MostAndTail function</span></span>

<span data-ttu-id="a0037-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a0037-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a0037-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a0037-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a0037-105">Vrátí řazenou kolekci členů všech kromě jednoho a posledního elementu pole.</span><span class="sxs-lookup"><span data-stu-id="a0037-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="a0037-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="a0037-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="a0037-107">pole: ' A []</span><span class="sxs-lookup"><span data-stu-id="a0037-107">array : 'A[]</span></span>

<span data-ttu-id="a0037-108">Pole s alespoň jedním prvkem.</span><span class="sxs-lookup"><span data-stu-id="a0037-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="a0037-109">Výstup: (' A [], ' A)</span><span class="sxs-lookup"><span data-stu-id="a0037-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="a0037-110">Řazená kolekce členů všech s výjimkou jednoho a posledního elementu pole.</span><span class="sxs-lookup"><span data-stu-id="a0037-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a0037-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a0037-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="a0037-112">A</span><span class="sxs-lookup"><span data-stu-id="a0037-112">'A</span></span>

<span data-ttu-id="a0037-113">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="a0037-113">The type of the array elements.</span></span>