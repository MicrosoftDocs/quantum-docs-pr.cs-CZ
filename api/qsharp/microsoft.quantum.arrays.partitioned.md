---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Dělená funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: 43d99a0e33a813e4af23a3890ace808e91c1049c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845547"
---
# <a name="partitioned-function"></a><span data-ttu-id="f9e0d-102">Dělená funkce</span><span class="sxs-lookup"><span data-stu-id="f9e0d-102">Partitioned function</span></span>

<span data-ttu-id="f9e0d-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f9e0d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f9e0d-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f9e0d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f9e0d-105">Rozdělí pole na více částí.</span><span class="sxs-lookup"><span data-stu-id="f9e0d-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="f9e0d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f9e0d-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="f9e0d-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f9e0d-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f9e0d-108">Počet prvků v každé části pole</span><span class="sxs-lookup"><span data-stu-id="f9e0d-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="f9e0d-109">Šipka: t []</span><span class="sxs-lookup"><span data-stu-id="f9e0d-109">arr : 'T[]</span></span>

<span data-ttu-id="f9e0d-110">Vstupní pole, které se má rozdělit</span><span class="sxs-lookup"><span data-stu-id="f9e0d-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="f9e0d-111">Výstup: t [] []</span><span class="sxs-lookup"><span data-stu-id="f9e0d-111">Output : 'T[][]</span></span>

<span data-ttu-id="f9e0d-112">Více polí, kde první pole je první `nElements[0]` z `arr` a druhé pole je další `nElements[1]` z `arr` atd. Poslední pole bude obsahovat všechny zbývající prvky.</span><span class="sxs-lookup"><span data-stu-id="f9e0d-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f9e0d-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f9e0d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f9e0d-114">'S</span><span class="sxs-lookup"><span data-stu-id="f9e0d-114">'T</span></span>



## <a name="example"></a><span data-ttu-id="f9e0d-115">Příklad</span><span class="sxs-lookup"><span data-stu-id="f9e0d-115">Example</span></span>

```qsharp
// The following returns [[1, 5], [3], [7]];
let split = Partitioned([2,1], [1,5,3,7]);
```