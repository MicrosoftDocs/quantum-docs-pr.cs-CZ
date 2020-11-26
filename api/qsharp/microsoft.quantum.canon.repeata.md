---
uid: Microsoft.Quantum.Canon.RepeatA
title: Operace opakování
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 5f418f67d7265d4cb39b3636906c74d33d80f472
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205553"
---
# <a name="repeata-operation"></a><span data-ttu-id="94da5-102">Operace opakování</span><span class="sxs-lookup"><span data-stu-id="94da5-102">RepeatA operation</span></span>

<span data-ttu-id="94da5-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="94da5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="94da5-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="94da5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="94da5-105">Opakuje zadaný počet opakování operace.</span><span class="sxs-lookup"><span data-stu-id="94da5-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="94da5-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="94da5-106">Input</span></span>

### <a name="op--tinput--unit--is-adj"></a><span data-ttu-id="94da5-107">op: TInput => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="94da5-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="94da5-108">Operace, která se má volat opakovaně</span><span class="sxs-lookup"><span data-stu-id="94da5-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="94da5-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="94da5-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="94da5-110">Počet pokusů o volání `op` .</span><span class="sxs-lookup"><span data-stu-id="94da5-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="94da5-111">vstup: ' TInput</span><span class="sxs-lookup"><span data-stu-id="94da5-111">input : 'TInput</span></span>

<span data-ttu-id="94da5-112">Vstup, který má být předán `op` .</span><span class="sxs-lookup"><span data-stu-id="94da5-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="94da5-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="94da5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="94da5-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="94da5-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="94da5-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="94da5-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="94da5-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="94da5-116">See Also</span></span>

- [<span data-ttu-id="94da5-117">Microsoft. Forms. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="94da5-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="94da5-118">Microsoft. v. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="94da5-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="94da5-119">Microsoft. proRepeatC. Canon.</span><span class="sxs-lookup"><span data-stu-id="94da5-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="94da5-120">Microsoft. proRepeatCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="94da5-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)