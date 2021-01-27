---
uid: Microsoft.Quantum.Arrays.Chunks
title: Funkce bloků dat
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: 977594839a7d2fe09de8138d32a4a50e8a752390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842881"
---
# <a name="chunks-function"></a><span data-ttu-id="50c34-102">Funkce bloků dat</span><span class="sxs-lookup"><span data-stu-id="50c34-102">Chunks function</span></span>

<span data-ttu-id="50c34-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="50c34-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="50c34-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="50c34-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="50c34-105">Rozdělí pole na více částí stejné délky.</span><span class="sxs-lookup"><span data-stu-id="50c34-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="50c34-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="50c34-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="50c34-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="50c34-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="50c34-108">Délka každého bloku.</span><span class="sxs-lookup"><span data-stu-id="50c34-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="50c34-109">Šipka: t []</span><span class="sxs-lookup"><span data-stu-id="50c34-109">arr : 'T[]</span></span>

<span data-ttu-id="50c34-110">Pole, které má být rozděleno.</span><span class="sxs-lookup"><span data-stu-id="50c34-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="50c34-111">Výstup: t [] []</span><span class="sxs-lookup"><span data-stu-id="50c34-111">Output : 'T[][]</span></span>

<span data-ttu-id="50c34-112">Pole obsahující všechny bloky původního pole.</span><span class="sxs-lookup"><span data-stu-id="50c34-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="50c34-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="50c34-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="50c34-114">'S</span><span class="sxs-lookup"><span data-stu-id="50c34-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="50c34-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="50c34-115">Remarks</span></span>

<span data-ttu-id="50c34-116">Všimněte si, že poslední element výstupu může být kratší než, `nElements` Pokud není `Length(arr)` dělitelem `nElements` .</span><span class="sxs-lookup"><span data-stu-id="50c34-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>