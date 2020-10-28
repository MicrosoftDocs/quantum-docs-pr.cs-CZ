---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Sequence – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705784"
---
# <a name="sequencel-function"></a><span data-ttu-id="e2f53-102">Sequence – funkce</span><span class="sxs-lookup"><span data-stu-id="e2f53-102">SequenceL function</span></span>

<span data-ttu-id="e2f53-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e2f53-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e2f53-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e2f53-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e2f53-105">Získá pole celých čísel v daném intervalu.</span><span class="sxs-lookup"><span data-stu-id="e2f53-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="e2f53-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e2f53-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="e2f53-107">od: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e2f53-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e2f53-108">Celkový počáteční index intervalu.</span><span class="sxs-lookup"><span data-stu-id="e2f53-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="e2f53-109">na: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e2f53-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e2f53-110">Celkový index v intervalu, který není menší než `from` .</span><span class="sxs-lookup"><span data-stu-id="e2f53-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="e2f53-111">Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="e2f53-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="e2f53-112">Pole obsahující sekvenci čísel `from` , `from + 1` ,..., `to` .</span><span class="sxs-lookup"><span data-stu-id="e2f53-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e2f53-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e2f53-113">Remarks</span></span>

<span data-ttu-id="e2f53-114">Rozdíl mezi `from` a se `to` musí vejít do `Int` hodnoty.</span><span class="sxs-lookup"><span data-stu-id="e2f53-114">The difference between `from` and `to` must fit into an `Int` value.</span></span>