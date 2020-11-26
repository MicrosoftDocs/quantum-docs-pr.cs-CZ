---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Sequence – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3e5c7f64825f09d82792d3e46fe3f53f5814510b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220259"
---
# <a name="sequencel-function"></a><span data-ttu-id="ed10f-102">Sequence – funkce</span><span class="sxs-lookup"><span data-stu-id="ed10f-102">SequenceL function</span></span>

<span data-ttu-id="ed10f-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ed10f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ed10f-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ed10f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ed10f-105">Získá pole celých čísel v daném intervalu.</span><span class="sxs-lookup"><span data-stu-id="ed10f-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="ed10f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ed10f-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="ed10f-107">od: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ed10f-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ed10f-108">Celkový počáteční index intervalu.</span><span class="sxs-lookup"><span data-stu-id="ed10f-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="ed10f-109">na: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ed10f-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ed10f-110">Celkový index v intervalu, který není menší než `from` .</span><span class="sxs-lookup"><span data-stu-id="ed10f-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="ed10f-111">Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="ed10f-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="ed10f-112">Pole obsahující sekvenci čísel `from` , `from + 1` ,..., `to` .</span><span class="sxs-lookup"><span data-stu-id="ed10f-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ed10f-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ed10f-113">Remarks</span></span>

<span data-ttu-id="ed10f-114">Rozdíl mezi `from` a se `to` musí vejít do `Int` hodnoty.</span><span class="sxs-lookup"><span data-stu-id="ed10f-114">The difference between `from` and `to` must fit into an `Int` value.</span></span>