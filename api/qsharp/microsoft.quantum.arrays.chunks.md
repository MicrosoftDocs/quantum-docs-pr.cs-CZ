---
uid: Microsoft.Quantum.Arrays.Chunks
title: Funkce bloků dat
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: b323fdab1b207c72a4f46d5ca4cb368ecf0df818
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221602"
---
# <a name="chunks-function"></a><span data-ttu-id="ca545-102">Funkce bloků dat</span><span class="sxs-lookup"><span data-stu-id="ca545-102">Chunks function</span></span>

<span data-ttu-id="ca545-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ca545-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ca545-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ca545-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ca545-105">Rozdělí pole na více částí stejné délky.</span><span class="sxs-lookup"><span data-stu-id="ca545-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="ca545-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ca545-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="ca545-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ca545-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ca545-108">Délka každého bloku.</span><span class="sxs-lookup"><span data-stu-id="ca545-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="ca545-109">Šipka: t []</span><span class="sxs-lookup"><span data-stu-id="ca545-109">arr : 'T[]</span></span>

<span data-ttu-id="ca545-110">Pole, které má být rozděleno.</span><span class="sxs-lookup"><span data-stu-id="ca545-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="ca545-111">Výstup: t [] []</span><span class="sxs-lookup"><span data-stu-id="ca545-111">Output : 'T[][]</span></span>

<span data-ttu-id="ca545-112">Pole obsahující všechny bloky původního pole.</span><span class="sxs-lookup"><span data-stu-id="ca545-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ca545-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ca545-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ca545-114">'S</span><span class="sxs-lookup"><span data-stu-id="ca545-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="ca545-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ca545-115">Remarks</span></span>

<span data-ttu-id="ca545-116">Všimněte si, že poslední element výstupu může být kratší než, `nElements` Pokud není `Length(arr)` dělitelem `nElements` .</span><span class="sxs-lookup"><span data-stu-id="ca545-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>