---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Dělená funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: bce46262e3ef64a43e578098d81c5dd39225915e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220497"
---
# <a name="partitioned-function"></a><span data-ttu-id="29a5e-102">Dělená funkce</span><span class="sxs-lookup"><span data-stu-id="29a5e-102">Partitioned function</span></span>

<span data-ttu-id="29a5e-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="29a5e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="29a5e-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="29a5e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="29a5e-105">Rozdělí pole na více částí.</span><span class="sxs-lookup"><span data-stu-id="29a5e-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="29a5e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="29a5e-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="29a5e-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="29a5e-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="29a5e-108">Počet prvků v každé části pole</span><span class="sxs-lookup"><span data-stu-id="29a5e-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="29a5e-109">Šipka: t []</span><span class="sxs-lookup"><span data-stu-id="29a5e-109">arr : 'T[]</span></span>

<span data-ttu-id="29a5e-110">Vstupní pole, které se má rozdělit</span><span class="sxs-lookup"><span data-stu-id="29a5e-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="29a5e-111">Výstup: t [] []</span><span class="sxs-lookup"><span data-stu-id="29a5e-111">Output : 'T[][]</span></span>

<span data-ttu-id="29a5e-112">Více polí, kde první pole je první `nElements[0]` z `arr` a druhé pole je další `nElements[1]` z `arr` atd. Poslední pole bude obsahovat všechny zbývající prvky.</span><span class="sxs-lookup"><span data-stu-id="29a5e-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="29a5e-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="29a5e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="29a5e-114">'S</span><span class="sxs-lookup"><span data-stu-id="29a5e-114">'T</span></span>

