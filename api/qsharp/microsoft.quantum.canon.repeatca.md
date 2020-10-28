---
uid: Microsoft.Quantum.Canon.RepeatCA
title: Operace RepeatCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: b68c3aa4298fffa76f7c43ac4c6d27cdf3b72fbf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698888"
---
# <a name="repeatca-operation"></a><span data-ttu-id="bd462-102">Operace RepeatCA</span><span class="sxs-lookup"><span data-stu-id="bd462-102">RepeatCA operation</span></span>

<span data-ttu-id="bd462-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bd462-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bd462-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bd462-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bd462-105">Opakuje zadaný počet opakování operace.</span><span class="sxs-lookup"><span data-stu-id="bd462-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="bd462-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="bd462-106">Input</span></span>

### <a name="op--tinput--unit-adj--ctl"></a><span data-ttu-id="bd462-107">op: TInput => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="bd462-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="bd462-108">Operace, která se má volat opakovaně</span><span class="sxs-lookup"><span data-stu-id="bd462-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="bd462-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bd462-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bd462-110">Počet pokusů o volání `op` .</span><span class="sxs-lookup"><span data-stu-id="bd462-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="bd462-111">vstup: ' TInput</span><span class="sxs-lookup"><span data-stu-id="bd462-111">input : 'TInput</span></span>

<span data-ttu-id="bd462-112">Vstup, který má být předán `op` .</span><span class="sxs-lookup"><span data-stu-id="bd462-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bd462-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bd462-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bd462-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="bd462-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="bd462-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="bd462-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="bd462-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="bd462-116">See Also</span></span>

- [<span data-ttu-id="bd462-117">Microsoft. Forms. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="bd462-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="bd462-118">Microsoft. v. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="bd462-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="bd462-119">Microsoft. prodoby. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="bd462-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="bd462-120">Microsoft. proRepeatC. Canon.</span><span class="sxs-lookup"><span data-stu-id="bd462-120">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)