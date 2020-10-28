---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 8786250cf2f78ce2e9ff8baddc856d0bc07cb9a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705857"
---
# <a name="mostandtail-function"></a><span data-ttu-id="cbb87-102">MostAndTail – funkce</span><span class="sxs-lookup"><span data-stu-id="cbb87-102">MostAndTail function</span></span>

<span data-ttu-id="cbb87-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="cbb87-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="cbb87-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cbb87-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cbb87-105">Vrátí řazenou kolekci členů všech kromě jednoho a posledního elementu pole.</span><span class="sxs-lookup"><span data-stu-id="cbb87-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="cbb87-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="cbb87-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="cbb87-107">pole: ' A []</span><span class="sxs-lookup"><span data-stu-id="cbb87-107">array : 'A[]</span></span>

<span data-ttu-id="cbb87-108">Pole s alespoň jedním prvkem.</span><span class="sxs-lookup"><span data-stu-id="cbb87-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="cbb87-109">Výstup: (' A [], ' A)</span><span class="sxs-lookup"><span data-stu-id="cbb87-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="cbb87-110">Řazená kolekce členů všech s výjimkou jednoho a posledního elementu pole.</span><span class="sxs-lookup"><span data-stu-id="cbb87-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cbb87-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="cbb87-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="cbb87-112">A</span><span class="sxs-lookup"><span data-stu-id="cbb87-112">'A</span></span>

<span data-ttu-id="cbb87-113">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="cbb87-113">The type of the array elements.</span></span>