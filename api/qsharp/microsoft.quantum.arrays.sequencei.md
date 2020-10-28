---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Sequence – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705793"
---
# <a name="sequencei-function"></a><span data-ttu-id="d3c28-102">Sequence – funkce</span><span class="sxs-lookup"><span data-stu-id="d3c28-102">SequenceI function</span></span>

<span data-ttu-id="d3c28-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d3c28-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d3c28-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d3c28-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d3c28-105">Získá pole celých čísel v daném intervalu.</span><span class="sxs-lookup"><span data-stu-id="d3c28-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="d3c28-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="d3c28-106">Input</span></span>

### <a name="from--int"></a><span data-ttu-id="d3c28-107">od: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d3c28-107">from : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d3c28-108">Celkový počáteční index intervalu.</span><span class="sxs-lookup"><span data-stu-id="d3c28-108">An inclusive start index of the interval.</span></span>


### <a name="to--int"></a><span data-ttu-id="d3c28-109">do: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d3c28-109">to : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d3c28-110">Celkový index v intervalu, který není menší než `from` .</span><span class="sxs-lookup"><span data-stu-id="d3c28-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--int"></a><span data-ttu-id="d3c28-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d3c28-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="d3c28-112">Pole obsahující sekvenci čísel `from` , `from + 1` ,..., `to` .</span><span class="sxs-lookup"><span data-stu-id="d3c28-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>