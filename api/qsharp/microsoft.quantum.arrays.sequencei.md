---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Sequence – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3cf09e48cce1aeb1aac837465ee3a5e06adf5169
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851010"
---
# <a name="sequencei-function"></a><span data-ttu-id="67647-102">Sequence – funkce</span><span class="sxs-lookup"><span data-stu-id="67647-102">SequenceI function</span></span>

<span data-ttu-id="67647-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="67647-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="67647-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="67647-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="67647-105">Získá pole celých čísel v daném intervalu.</span><span class="sxs-lookup"><span data-stu-id="67647-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="67647-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="67647-106">Input</span></span>

### <a name="from--int"></a><span data-ttu-id="67647-107">od: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="67647-107">from : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="67647-108">Celkový počáteční index intervalu.</span><span class="sxs-lookup"><span data-stu-id="67647-108">An inclusive start index of the interval.</span></span>


### <a name="to--int"></a><span data-ttu-id="67647-109">do: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="67647-109">to : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="67647-110">Celkový index v intervalu, který není menší než `from` .</span><span class="sxs-lookup"><span data-stu-id="67647-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--int"></a><span data-ttu-id="67647-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="67647-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="67647-112">Pole obsahující sekvenci čísel `from` , `from + 1` ,..., `to` .</span><span class="sxs-lookup"><span data-stu-id="67647-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="example"></a><span data-ttu-id="67647-113">Příklad</span><span class="sxs-lookup"><span data-stu-id="67647-113">Example</span></span>

```qsharp
let arr1 = SequenceI(0, 3); // [0, 1, 2, 3]
let arr2 = SequenceI(23, 29); // [23, 24, 25, 26, 27, 28, 29]
let arr3 = SequenceI(-5, -2); // [-5, -4, -3, -2]

let numbers = SequenceI(0, _); // function to create sequence from 0 to `to`
let naturals = SequenceI(1, _); // function to create sequence from 1 to `to`
```